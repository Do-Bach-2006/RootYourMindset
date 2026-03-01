---
title: "Lab log 0: Giới thiệu về malware"
date: 2026-03-01T11:30:16.522Z
tags: ["Malware","Trojans","Ransomware","Adware","Viruses","Worms","WannaCry","ILOVEYOU","Chernobyl","EternalBlue","Phishing","Cybercrime","AntivirusSoftware","Heuristic","SignatureDetection"]
keywords: ["Malware","Trojans","Ransomware","Adware","Viruses","Worms","WannaCry","ILOVEYOU","Chernobyl","EternalBlue","Phishing","Cybercrime","AntivirusSoftware","Heuristic","SignatureDetection"]
cover:
  image: "https://picsum.photos/seed/775335/1200/630"
  caption: "Một bức ảnh cho cuộc phiêu lưu mới"
  relative: false
  hiddenInList: false
  hiddenInSingle: false
draft: false
---

# Lab log 0: Giới thiệu về malware

## Malware

Bạn thấy máy tính, điện thoại của mình chạy chậm, có dấu hiệu giật lag ? Bạn thấy hiện tượng quảng cáo tự xuất hiện hay trình duyệt của bạn tự động mở vào một cái cái trang mà bạn không biết ? Rất có thể, máy của bạn đã bị nhiễm mã độc  !

Mã độc, hay còn gọi là malware, là các phần mềm được tạo ra với mục đích xấu như đánh cắp thông tin, phá hủy dữ liệu hoặc chiếm quyền điều khiển thiết bị của bạn.

Malware thì được phân ra làm rất nhiều loại, được gọi là họ, tùy vào những đặc tính hoặc biểu hiện của chúng khi tấn công. Phổ biến có thể kể đến như 

- Trojan
    
    Cái tên Trojan bắt nguồn từ câu chuyện “con ngựa thành Troia” trong thần thoại Hy Lạp, được kể lại trong sử thi Iliad. Loại malware này ngụy trang dưới danh một phần mềm bình thường, vô hại vào ban đầu để đánh lừa người dùng. Một khi đã len lỏi vào hệ thống, nó có thể “lật mặt” và thực hiện các hành vi độc hại như đánh cắp dữ liệu hoặc cài thêm mã độc khác ( sneaky beaky like ) 
    
- Ransomware
    
    Là loại malware chuyên mã hóa dữ liệu của nạn nhân rồi yêu cầu trả tiền chuộc để lấy lại quyền truy cập
    
    Khi được chạy, chúng sẽ mã hóa tất cả các tài liệu, tập tin mà chương trình có thể chạm tới với chìa khóa được chứa trên server của hacker. Sau đó, chúng yêu cầu bạn phải trả một số tiền trước một khoảng thời gian nào đó để có thể lấy lại được các tài liệu cá nhân của bạn.
    
- Adware
    Là những loại malware hiển thị quảng cáo, pop up, tự động chuyển trang,… Mục đích là để cho người dùng bấm nhầm, dẫn đến các nguồn khác độc hại hơn hoặc đơn giản là kiếm tiền và sự chú ý của người dùng.
    
- Virus, Worm
    
    Là loại malware lây lan. Khi một máy bị nhiễm virus, nó sẽ lây cho các tệp tin trong máy, và các tệp tin ấy khi được chuyển đi nơi khác, mở lên và trở thành một nguồn lây khác cho máy khác. Không giống virus, worm nguy hiểm hơn khi nó không cần tới sự kích hoạt của người dùng( mở file, copy file sang máy khác ) nhưng vẫn có thể tự động nhân bản và lây nhiễm qua đường internet tới các máy khác. 
    

Tất nhiên, đây chỉ là các cái đặc trưng của loại malware, nhưng điều đáng sợ nhất, đó chính một phần mềm độc hại có thể có nhiều đặc tính cùng một lúc. Ví dụ, hacker có thể sử dụng một con trojan để đưa adware vào máy của bạn, đồng thời cũng cho phép nó spyware lên thông tin cá nhân của bạn. Và đây, là khi trò thú vị bắt đầu . 

## Một vài thiệt hại mà malware đã gây ra

- Wanna cry
	![Pasted image 20260228221809](Pasted%20image%2020260228221809.png)


    Phát hiện vào 12/5/2017 Là một loại ransomware và worm tống tiền bằng crypto
    
    Khai thác lỗ hổng của EternalBlue để có thể tự lan truyền bản thân qua networks ( đặc tính của worm ) 
    
    Khi đã tới được máy của nạn nhân ( qua Phishing, lây truyền, sơ xuất của người dùng… ) chúng sẽ mã hóa các tệp tin thông dụng như docx, ảnh, DBs sử dụng loại mã hóa AES-128 cho mỗi file và RSA-2048 cho chìa khóa giải mã. Để mở khóa, nạn nhân cần phải trả cho các hacker khoảng 300 tới 600 đô.
    
    Ảnh hưởng tới hơn 300 000 máy tính, trên 150 quốc gia, ước tính từ hàng trăm triệu đến vài tỉ USD, có nguồn ước tính khoảng 4 tỉ đô
    
    Bị chặn một vài giờ sau đó bởi một nhà nghiên cứu Marcus Hutchins vì đã đăng ký tên miền killswitch, khiến cho con malware tưởng rằng nó đang trong môi trường sandbox và dừng hoạt động, làm giảm đáng kể thiệt hại.
    
    Về sau ông này cũng bị FBI bắt giữ vì liên quan đến việc phát triển một loại trojan ngân hàng khác. Đúng đời là bể dâu :)) (Kronos) 
    
- ILOVEYOU
	![](Pasted%20image%2020260228221707.png)

    Được phát hiện vào ngày 4/5/2000, là một loại worm bắt nguồn từ Philippines 
    
    Đây là loại malware được tấn công trên email. ILOVEYOU gửi cho người dùng một bức thư chứa tệp tin đính kèm là LOVE-LETTER-FOR-YOU.TXT.vbs . Chỉ cần một người dùng duy nhất trên mạng mở email mà ILOVEYOU được đính kèm thì sẽ bị lây nhiễm, và Khi một máy bị nhiễm, malware sẽ tự gửi đến tất cả các địa chỉ trong sổ địa chỉ của người dùng (outlook). Sau đó, con malware còn thực hiện nhiều tác vụ khác như tự động bật mỗi khi người dùng reset máy, tải các phần mềm trojan khác để đánh cắp thông tin, mật khẩu người dùng,… 
    
    Ảnh hưởng hơn 50 triệu máy tính, gây thiệt hại từ 5.5 tới 8.7 tỉ đô, và tốn 10-15 tỉ đô để dọn dẹp.
    
    Có một sự thật hài hước là Người tạo ra malware ấy Onel De Guzman không bị bắt vì thời ấy philipines không có luật cho khoảng tội phạm mạng.
    
     
    
- Chernobyl
	![](Pasted%20image%2020260228221512.png)
    
    Được mọi người chú ý vào khoảng tháng 6/1998, đây là một loại virus CIH (Space filler malware) lây nhiễm qua file PE.
    
    Kẻ tấn công ghi đè mã độc vào các khoảng đệm không sử dụng tới trong file PE ( portable execution, là các file thực thi trong hệ điều hành windows) ], khiến cho file vẫn hoạt động và qua mắt được phần mềm kiểm diệt virus thời bấy giờ  
    
    Đây là loại malware có thể nuke luôn phần cứng máy tính của bạn, ghi đè lên BIOS của hệ thống. Nghĩa là cài lại win cũng chả được nữa. Khiến cho việc giải cứu máy tính trở nên rất khó khăn. ( reflash lại bios,…)
    
    Lây nhiễm khoảng 60 triệu máy tính, gây thiệt hại khoảng 250 triệu đô vào thời bấy giờ.
    
    Nó là loại virus đầu tiên có thể tấn công tới phần cứng của máy tính và được lập trình để kích hoạt tấn công vào ngày 26 tháng 4 nên được đặt tên là Chernobyl, dựa theo thảm họa hạt nhân Chernobyl của loài người.
    

Vậy, ta có thể thấy. Malware gây thiệt hại rất lớn đến với máy tính và tài sản của bạn. Vì vậy, bạn hoàn toàn có lý do chính đáng để lo lắng cho việc máy bạn có những biểu hiện bất thường. 

Tuy nhiên, đôi khi do máy bạn có bụi hoặc lỗi phần mềm, thời gian nào đó chạy sai,… 

Vì vậy, ở phần sau, mình sẽ giải thích cách mà các phần mềm diệt virus phát hiện malware trên máy tính của bạn. Bật mí trước là hai từ khóa Hieuristic và Signature nhé !