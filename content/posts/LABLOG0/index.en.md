---
title: "Lab log 0: Introduction to malware"
date: 2026-03-01T11:30:16.512Z
tags: ["Malware","Trojans","Ransomware","Adware","Viruses","Worms","WannaCry","ILOVEYOU","Chernobyl","EternalBlue","Phishing","Cybercrime","AntivirusSoftware","Heuristic","SignatureDetection"]
keywords: ["Malware","Trojans","Ransomware","Adware","Viruses","Worms","WannaCry","ILOVEYOU","Chernobyl","EternalBlue","Phishing","Cybercrime","AntivirusSoftware","Heuristic","SignatureDetection"]
cover:
  image: "https://picsum.photos/seed/65038/1200/630"
  caption: "A picture for a brand new adventure"
  relative: false
  hiddenInList: false
  hiddenInSingle: false
draft: false
---

# Lab log 0: Introduction to malware

## Malware...

Is your computer or phone running slowly, showing signs of lag? Are you seeing unexpected ads, or does your browser automatically open unfamiliar pages? If so, your device has most likely been infected with malware!

Malware is software designed for malicious purposes, such as stealing information, destroying data, or taking control of your device.

Malware is classified into many types, depending on their characteristics or how they manifest during an attack. Common types include:

- Trojans...
    
The name Trojan originates from the story of "the horse of Troy" in Greek mythology, as told in the Iliad. This type of malware initially disguises itself as normal, harmless software to deceive users. Once it infiltrates the system, it can "turn" and perform malicious actions, such as stealing data or installing other malicious code ( sneaky beaky like )
    
- Ransomware
    
It is malware that encrypts the victim's data and then demands a ransom to regain access.
    
When run, it will encrypt all accessible documents and files using a key stored on the hacker's server. Afterward, it demands a specific payment to restore access to your personal documents.
    
- Adware
Adware is a type of malware that displays unwanted ads, pop-ups, and automatically redirects pages. Its purpose is to trick users into mistakenly clicking, potentially leading to more malicious sources, or simply to generate revenue and capture user attention.
    
- Viruses, worms...
    
These are types of malware that spread. When a machine is infected with a virus, it will infect files on that machine. Subsequently, if those files are transferred elsewhere and opened, they become a source of infection for other machines. Unlike viruses, worms are more dangerous because they do not require user activation (e.g., opening files, copying files to another machine) but can still automatically replicate and infect other machines via the internet.
    

Of course, these are just characteristics of malware, but the scariest thing is that malware itself can possess multiple properties simultaneously. For example, hackers can use a Trojan to install adware on your computer while also allowing it to spy on your personal information. And this is when the fun begins.

## Some of the damage that malware has caused

Wanna cry?
![Pasted image 20260228221809](Pasted%20image%2020260228221809.png)


Discovered on May 12, 2017, WannaCry was a ransomware and worm attack that used cryptocurrency for extortion.
    
It exploited the EternalBlue vulnerability to propagate itself through networks (a worm characteristic).
    
Once it reaches a victim's computer (e.g., through phishing, transmission, or user negligence), it encrypts common files (e.g., .docx, photos, databases) using AES-128 encryption for each file and RSA-2048 for the decryption key. To unlock these files, victims were required to pay the hacker approximately 300 to 600 dollars.
    
It affected over 300,000 computers in 150 countries, causing an estimated hundreds of millions to billions of dollars in damage, with some sources estimating up to four billion dollars.
    
It was blocked a few hours later by researcher Marcus Hutchins, who registered the killswitch domain, causing the malware to assume it was in a sandbox environment and shut down, which greatly reduced the damage.
    
He was also later arrested by the FBI for involvement in developing another type of banking Trojan (Kronos). Life is a strawberry tank :))
    
- ILOVEYOU
[](Pasted%20image%2020260228221707.png)

Discovered on May 4, 2000, it was a worm originating in the Philippines.
    
This is a type of malware that spreads via emails. ILOVEYOU sends users a message with an attachment called LOVE-LETTER-FOR-YOU.TXT.vbs. If a single user on the network opened the email with the ILOVEYOU attachment, their machine would become infected. Subsequently, the malware would automatically send copies of itself to all addresses in the infected user's Outlook address book. The malware then performs many other tasks, such as automatically activating every time the user restarts the machine and downloading other Trojans to steal information and user passwords,
    
It affected more than 50 million computers, caused $5.5 billion to $8.7 billion in damage, and cost $10 - 15 billion to clean up.
    
A notable fact is that the creator of the malware, Onel De Guzman, wasn't arrested because the Philippines did not have cybercrime laws at the time.
    
     
    
- Chernobyl...
[](Pasted%20image%2020260228221512.png)
    
It came to public attention in June 1998 as a CIH (space-filler malware) virus that infected PE files.
    
The attacker overwrites unused spaces in the PE file (Portable Executable, the executable file format in the Windows operating system), allowing the file to remain active and bypass the antivirus software of the time.
    
This is a type of malware that can severely damage your computer's hardware by overwriting the system's BIOS. This means reinstalling Windows is no longer possible, making it very difficult to recover your computer (e.g., reflash BIOS).
    
It infected about 60 million computers, causing about 250 million dollars in damage at the time.
    
It was the first virus capable of attacking computer hardware and was programmed to trigger an attack on April 26, hence it was named Chernobyl, after the Chernobyl nuclear disaster.
    

As we can see, malware can cause immense damage to your computer and personal property. Therefore, you have good reason to be concerned if your computer exhibits any abnormalities.

However, sometimes abnormalities might simply be due to dust accumulation or a software error, causing your machine to run incorrectly.

So, in the next section, I will explain how antivirus software detects malware on your computer. First, I will introduce two key concepts: Heuristic and Signature (offline)!