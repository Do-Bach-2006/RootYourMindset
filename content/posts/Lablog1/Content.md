# Lab log 1: Làm sao mà máy tính có thể phát hiện ra mã độc ?
## Intro

Trước khi đi sâu hơn thì mình muốn đính chính rằng từ malware mà chúng ta dùng chung ở đây, là loại mã độc cho hệ điều hành windows! Nghĩa là file Portable Execution. Chúng có những đuôi file là .exe, .dll, .bin, …

Tuy nhiên, những nguyên lý ở dưới cũng có thể được hiểu chung cơ chế phát hiện với các loại malware cho linux, cho điện thoại android.

Có rất nhiều phương pháp để đánh giá xem một file có phải là malware hay không, nhưng chung quy lại, chúng sẽ được phân loại thành hai cách đó chính là phân tích tĩnh và phân tích động !

## Phân tích tĩnh ( Static analysis )

Là loại phân tích dễ nhất, chỉ nhìn và đánh giá vẻ bề ngoài. Từ đấy đã có thể kết luận rằng một file là độc hay là lành. Ví dụ như: nếu mang súng, vào ngân hàng, bịt mặt, thì ta có thể dự đoán người đó tính cướp ngân hàng. Ở đây cũng giống như vậy, nếu có header lạ, mà trong thân hàm lại gọi tới các lệnh đọc file và mã hóa file thì có khả năng cao con này là ransomware.

Có rất nhiều cách để trích xuất các đặc trưng của một file PE. Đầu tiên là signature của file. Là nội dung của file cho vào hàm băm ( hash function). Hay từ nội dung raw của file là các đoạn mã binary 1 và 0. Khi dịch ngược lại assembly, ta có một đống thông tin khác như header, section, import cũng như bytecode, opcode của file.

Ưu điểm của cách làm này:

- Nhanh gọn, lẹ, không cần suy nghĩ nhiều
- Tốn ít tài nguyên, chỉ cần một vài dòng code hay công cụ thì có thể cho ta biết các thông tin luôn

Nhược điểm của chúng

- Không thể đánh giá được hết việc làm của một file PE, không hiểu được bối cảnh.
- Hoàn toàn thất thủ trước các con malware có ngụy trang ( obsfucation ). Những con malware này encrypt đoạn malware độc lại để các công cụ phân tích tĩnh không phát hiễn ra, sau đó trong quá trình thực thi sẽ giải nén và chạy các đoạn mã độc đó.
![](Ways%20to%20static%20analysis%20a%20malware.png)
![](Informations%20that%20you%20can%20get%20from%20a%20PE%20file.png)
## Phân tích động ( dynamic analysis )

Là loại phương pháp phân tích có độ chính xác cao, nó quan sát, xem hành vi của con malware như thế nào. Giống như một cái camera quan sát, nó sẽ nhìn từng hành vi của file PE, từ đó đánh giá là malware hay là phần mềm bình thường.

Vậy thực hiện quan sát bằng cách nào? Có 2 cách, là môi trường ảo (sandbox) và thời gian thực realtime.

Sandbox là một môi trường như máy tính của người bình thường. Nó có file dữ liệu, có các ứng dung thông dụng như trình duyệt, office, cũng tắt windows defender để tải crack game, có các tương tác thường nhật như tìm một địa chỉ web, đọc báo, mở file tài liệu,… Có điều, toàn bộ những thứ ấy được chạy trong máy ảo. TẤT CẢ CHỈ ĐỂ ĐÁNH LẠC HƯỚNG. TẤT CẢ LÀ MỘT CÁI BẪY ! Khi malware được chạy, toàn bộ nội dung, tiến trình của nó sẽ bị ghi lại. Từ hành vi, trạng thái của nó, liên lạc tới đâu, thời điểm nào… đều được giám sát. Và khi xong việc, sandbox chỉ cần quay trờ lại snapshot ban đầu trước khi chạy malware, hoàn toàn lành lặn và an toàn giống như R của Ekko vậy. Và ta có một đống thông tin, đủ để kết luận một file là malware hay chưa !

Mặt khác, phân tích thời gian thực là một cơ chế được tích hợp vào các công cụ antivirus. Ngay bản thân cơ chế real time protection của windows defender cũng tích hợp cơ chế này. Về cơ bản, việc phân tích sẽ diễn ra trong suốt quá trình bạn sử dụng máy tính. Từ lưu lượng mạng của bạn, các tiến trình lạ ( trong bảng Task Manager ) hay là các API call của các tiến trình ấy,… Tất cả đều được ghi lại và nhanh chóng hành động khi gặp sự cố.

- Ưu điểm của phương pháp này:
    - Cho ta biết được một cái nhìn tổng quan hơn, kỹ càng hơn về việc một file có là malware hay không
    - Tăng tỷ lệ chính xác, kể cả khi con malware đã ngụy trang bằng các phương pháp obsfucation thì nó vẫn phát hiện được.
- Nhược điểm của phương pháp này:
    - Cực kỳ mất thời gian. Việc phân tích và phát hiện một file malware có thể tốn từ vài phút cho tới vài ngày, tháng, năm. Tùy theo lệnh của hacker điều khiển và điều kiện
    - Ngốn tài nguyên. Việc chạy các tiến trình giám sát trên máy tính thường khiến cho hiệu suất máy giảm ( mà đừng có tắt nó để máy chạy nhanh hơn nhé, top 10 Darwin award trong năm 2026 lớn đấy )
    - Một số con malware có cơ chế tự phát hiện sandbox và nó cứ hoạt động bình thường, hoặc từ chối chạy ( như ta đã thấy ở cuộc tấn công WannaCry, đọc ở LabLog0).

![](Diagram%20feature%20cuckoo%20machine%20workflow.png)
![](Windows%20defender%20real-time%20protection.png)
Và trong một vài trường hợp, các công cụ có thể kết hợp cà 2 phương pháp để có thể thu hoạch được độ chính xác cao nhất. Mô hình này được gọi là hybrid analysis.

Vậy là đủ cho bài viết hôm nay rồi. Bài viết tiếp theo, mình sẽ kể cho các bạn biết lịch sử và quá trình phát triển của công cụ antivirus. Để xem các phương pháp phát hiện mã độc của chúng ta từ trước tới giờ đã thay đổi và cải tiến như thế nào !