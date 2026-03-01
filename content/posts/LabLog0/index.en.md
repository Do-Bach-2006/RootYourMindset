---
title: "cover:"
date: 2026-03-01T10:50:34.653Z
tags: ["malware","cybersecurity","infosec","wannacry","iloveyouworm","cihvirus","ransomware","trojan","techhistory","antivirus","virus","worm","cyberattack"]
keywords: ["malware","cybersecurity","infosec","wannacry","iloveyouworm","cihvirus","ransomware","trojan","techhistory","antivirus","virus","worm","cyberattack"]
cover:
  image: "https://picsum.photos/seed/423625/1200/630"
  caption: "A picture for a brand new adventure"
  relative: false
  hiddenInList: false
  hiddenInSingle: false
draft: false
---

cover:
  caption: A photo for a new adventure
  hiddenInList: false
  hiddenInSingle: false
  image: https://picsum.photos/seed/550113/1200/630
  relative: false
date: 2026-03-01 10:11:44.302000+00:00
draft: false
keywords:
- malware
- cybersecurity
- infosec
- wannacry
- iloveyouworm
- cihvirus
- ransomware
- trojan
- techhistory
- antivirus
tags:
- malware
- cybersecurity
- infosec
- wannacry
- iloveyouworm
- cihvirus
- ransomware
- trojan
- techhistory
- antivirus
title: 'Lab log 0: Introduction to Malware'
---

# Lab log 0: Introduction to Malware

## Malware...

Is your computer or phone running slowly? Are there signs of lag? Do you see ads popping up or your browser automatically opening pages you don't recognize? Most likely, your machine has been infected with malicious code!

Malware, short for "malicious software," is software created for harmful purposes such as stealing information, destroying data, or gaining control of your device. Malware is classified into several types based on its characteristics and behavior. Common types include:

- **Trojans**: Named after the "Trojan Horse" from Greek mythology, this malware disguises itself as harmless, legitimate software to deceive users. Once inside the system, it reveals its true nature, performing malicious actions like stealing data or installing other malware (sneaky beaky like).

- **Ransomware**: This malware encrypts a victim's data and demands a ransom for the decryption key. It encrypts documents and files using a key stored on the attacker's server, then demands payment before you can regain access to your personal files.

- **Adware**: This type of malware displays intrusive ads, pop-ups, or redirects your browser. The goal is to trick users into clicking links—leading to more malicious sites—or simply to generate revenue through forced exposure.

- **Viruses and Worms**: These are types of self-spreading malware. A virus infects files on a machine, and those files spread the infection when transferred and opened elsewhere. Unlike viruses, worms are more dangerous because they do not require user interaction (like opening a file) to replicate and spread automatically across the internet.

Of course, these are just categories; the most dangerous malware can possess multiple properties at once. For example, a hacker might use a Trojan to install Adware while simultaneously using Spyware to steal personal information. This is where the real trouble begins.

## Notable Damage Caused by Malware

### WannaCry?
![WannaCry Ransomware Screen](Pasted%20image%2020260228221809.png)

Discovered on May 12, 2017, WannaCry is a high-profile example of a ransomware-worm. It exploited the "EternalBlue" vulnerability to propagate itself across networks automatically.

Once it reaches a victim's computer (via phishing, network transmission, or user negligence), it encrypts common files like .docx, photos, and databases using AES-128 encryption, with the decryption key protected by RSA-2048. To unlock the files, victims were asked to pay between $300 and $600. It affected over 300,000 computers in 150 countries, with total damage estimates ranging from hundreds of millions to $4 billion. 

It was eventually slowed down a few hours later by researcher Marcus Hutchins, who registered a "killswitch" domain. The malware, programmed to check for this domain to detect if it was in a sandbox environment, shut down once the domain became active. Hutchins was later arrested by the FBI for his alleged involvement in developing the Kronos banking Trojan—life is full of twists and turns!

### ILOVEYOU
![ILOVEYOU Worm Email](Pasted%20image%2020260228221707.png)

Discovered on May 4, 2000, this worm originated in the Philippines and spread primarily via email. ILOVEYOU sent users a message with an attachment titled "LOVE-LETTER-FOR-YOU.TXT.vbs." If a single user on a network opened the attachment, the machine became infected and automatically sent the worm to everyone in the user's Outlook address book. The malware also performed other tasks, such as ensuring it ran every time the machine restarted and downloading additional Trojans to steal passwords.

It affected more than 50 million computers, causing $5.5 billion to $8.7 billion in damages and costing another $10–$15 billion to clean up. Interestingly, the creator, Onel De Guzman, was never arrested because the Philippines had no laws against cybercrime at that time.

### Chernobyl (CIH)
![CIH Virus Alert](Pasted%20image%2020260228221512.png)

First appearing in June 1998, CIH (also known as the "Space Filler" virus) infected Portable Executable (PE) files—the standard format for Windows executables. The virus overwrote unused sections of the PE file with malicious code, allowing the file to remain functional while bypassing contemporary antivirus software.

CIH was particularly destructive because it could "nuke" hardware by overwriting the system BIOS. This rendered the computer unbootable, making a simple Windows reinstallation impossible without reflashing the BIOS chip. It infected about 60 million computers, causing roughly $250 million in damage. It was named "Chernobyl" because it was programmed to trigger its payload on April 26, the anniversary of the Chernobyl nuclear disaster.

---

As we can see, malware causes massive damage to systems and personal property. It is only natural to worry if your computer behaves strangely. However, keep in mind that performance issues can sometimes be caused by simple things like dust buildup or software errors. In the next section, I will explain how antivirus software detects malware using two key methods: **Heuristics** and **Signature-based detection**!