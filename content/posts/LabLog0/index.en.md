---
title: "Lab log 0: Introduction to malware"
date: 2026-03-01T12:24:56.944Z
tags: ["Malware","Cybersecurity","ComputerSecurity","Trojans","Ransomware","Adware","Viruses","Worms","WannaCry","ILOVEYOU","ChernobylVirus","DataProtection","Antivirus"]
keywords: ["Malware","Cybersecurity","ComputerSecurity","Trojans","Ransomware","Adware","Viruses","Worms","WannaCry","ILOVEYOU","ChernobylVirus","DataProtection","Antivirus"]
cover:
  image: "https://picsum.photos/seed/209561/1200/630"
  caption: "A picture for a brand new adventure"
  relative: false
  hiddenInList: false
  hiddenInSingle: false
draft: false
---

# Lab log 0: Introduction to malware

## Malware...

Is your computer or phone running slowly, showing signs of lag? Do you see unexpected ads or your browser automatically opening unfamiliar pages? If so, your device has most likely been infected with malware!

Malware, or malicious software, is designed for harmful purposes like stealing information, destroying data, or gaining control of your device.

Malware is categorized into many types, depending on their characteristics or how they manifest during an attack. Common types include:

- Trojans...
    
The name Trojan originates from the story of “the horse of Troy” in Greek mythology, as told in the Iliad. This type of malware initially disguises itself as legitimate, harmless software to deceive users. Once it infiltrates the system, it can “turn over” (reveal its true nature) and perform malicious actions such as stealing data or installing other malicious code (sneaky beaky like)
    
- Ransomware
    
This is malware that encrypts a victim's data and then demands a ransom for access to be restored.
    
When executed, it encrypts all documents and files it can access, using a key stored on the hacker's server. It then demands an advance payment to decrypt your personal documents.
    
- Adware
These types of malware display unwanted ads, pop-ups, and trigger automatic page redirects. Their purpose is to trick users into clicking, potentially leading to more malicious downloads, or simply to generate revenue and capture user attention.
    
- Viruses, worms...
    
These are types of malware known for their ability to spread. When a machine is infected with a virus, it infects files on that machine. If those infected files are transferred and opened elsewhere, they can become a source of infection for another machine. Unlike viruses, worms are often more dangerous as they do not require user activation (e.g., opening or copying files) but can still automatically replicate and infect other machines via the internet.
    

Of course, these are just some characteristics of malware; what's truly alarming is that malware can exhibit multiple properties simultaneously. For example, hackers can use a Trojan to install adware on your computer, while also enabling it to spy on your personal information. And this is when the fun begins.

## Some of the damage that malware has caused

Wanna cry?
![Wanacry...](Pasted%20image%2020260228221809.png)


Discovered on May 12, 2017, WannaCry was a crypto-ransomware and worm extortion attack.
    
It exploited the EternalBlue vulnerability to propagate itself through networks (a worm characteristic).
    
Once it reached a victim's computer (through phishing, other forms of transmission, or user negligence), it encrypted common files such as .docx, photos, and databases using AES-128 for individual files and RSA-2048 for the decryption key. To unlock their data, victims were required to pay the hackers approximately $300 to $600.
    
It affected over 300,000 computers in 150 countries, causing damage estimated at hundreds of millions, possibly billions of dollars, with some sources placing the total at four billion dollars.
    
It was blocked a few hours later by researcher Marcus Hutchins, who registered a kill switch domain, causing the malware to believe it was in a sandbox environment and shut itself down, greatly reducing damage.
    
He was later arrested by the FBI for involvement in developing another type of banking Trojan. Life can be full of twists and turns. :)) (Kronos)
    
- ILOVEYOU
![Content of I love you email](Pasted%20image%2020260228221707.png)

Discovered on May 4, 2000, it was a worm originating in the Philippines.
    
This type of malware spread via emails. ILOVEYOU sent users a message with an attachment named LOVE-LETTER-FOR-YOU.TXT.vbs. If a single user on a network opened the email with the ILOVEYOU attachment, their machine would be infected. Once infected, the malware would automatically send itself to all addresses in the user's Outlook address book. The malware then performed many other tasks, such as automatically restarting every time the user rebooted the machine, and downloading other Trojans to steal information and user passwords.
    
It affected more than 50 million computers, causing $5.5 billion to $8.7 billion in damage, and costing an estimated $10-$15 billion to clean up.
    
A notable fact is that the creator of the malware, Onel De Guzman, was not arrested because the Philippines lacked laws for cybercrime at the time.
    
     
    
- Chernobyl...
![CIH infected bios](Pasted%20image%2020260228221512.png)
    
It came to public attention in June 1998 as the CIH (Chernobyl, or Space-filler) virus, which infected PE (Portable Executable) files.
    
The attacker overwrote malicious code into unused spaces within PE files (Portable Executable, a common executable file format in the Windows operating system), allowing the file to remain active and bypass the antivirus software of the time.
    
This type of malware could severely damage a computer's hardware by overwriting the system's BIOS. This meant reinstalling Windows was no longer possible, making recovery extremely difficult (often requiring a BIOS reflash).
    
It infected approximately 60 million computers, causing an estimated $250 million in damage at the time.
    
It was the first virus known to attack computer hardware and was programmed to trigger its destructive payload on April 26, consequently being named Chernobyl after the nuclear disaster.
    

As we can see, malware can cause immense damage to your computer and property. Therefore, you have good reason to be concerned if your computer exhibits any abnormalities.

However, sometimes these issues are caused by dust buildup in the machine or a software error causing it to malfunction.

So, in the next section, I will explain how antivirus software detects malware on your computer. I will first introduce two key concepts: Heuristic and Signature offline detection!
