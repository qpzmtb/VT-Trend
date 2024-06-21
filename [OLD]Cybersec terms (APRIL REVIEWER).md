# Security+ (Plus)


**Botnet**:
(short for “robot network”) is a network of computers infected by malware that are under the control of a malicious actors, known as the “bot-herder.”
Each individual machine under the control of the bot-herder is known as a bot. From one central point, the malicious actors can command every computer on its botnet to carry out cyberattacks.


**DGA (Domain Generation Algorithm)**:
Is a technique used by malicious actors to generate a large number of domain names that can be used to host malicious content. 
DGAs power the delivery of malware, generating hundreds of unique, random domains during cyberattacks. 
By Using DGA, malicious actors can evade detection and to ensure that their malicious content is not blocked by security measures.


**DNS sinkhole**:
"sinkhole" in cybersecurity refers to a mechanism or method used to redirect malicious traffic or communications to a controlled and monitored environment, often operated by security researchers or organizations.


**SSRF (Server-Side Request Forgery)**:
is a vulnerability where attackers manipulate requests on the server-side of a web application to carry out attacks. Attackers can access internal server resources or send requests to external services.


**UTM (Unified threat management)**:
UTM is a product that integrates multiple different security functions into one hardware.
It includes antivirus, content filtering, email and web filtering, anti-spam, and more.


**Fire Wall**:
Is a product that monitors and filters incoming and outgoing network traffic based on an organization’s previously established security policies.


**WAF (Web Application Fire Wall)**:
Is a product that protects web applications by filtering and monitoring HTTP traffic between a web application and internet.


**Proxy Server**:
Is an intermediary server that retrieves data from an Internet source (such as a webpage) on behalf of a user.


**SIEM (Security Information and Event Management)**:
Is a software solution that aggregates data from multiple systems and analyze that data to catch abnormal behavior or potential cyberattacks.


**EDR (Endpoint Detection and Response)**:
Is the software designed to automatically protect an end user from known or suspected Cyber threats.
__________________________________________________________________________________________
**CIA Triad principles: 3 most fundamental factors of information security.**
1. Confidentiality
2. Integrity
3. Availability

**1.Confidentiality**:
Ensures that information is accessible only to authorized users.
Protected from unauthorized access by password protection or encryption.

**Attacks threatening Confidentiality and countermeasures**
- Phishing (employee training)
- Eavesdropping (including MITM) (encryption)
- Malware (Spyware, Keylogger etc.) (IPS, UTM, EDR etc.)


**2.Integrity**:
Guarantees that information is accurate and has not been tampered.
Data is protected against alteration.

**Attacks threatening Integrity and countermeasures**
- SQL Injection Attack (WAF (Web Application Firewall), secure coding)
- Cross Site Scripting Attack (XSS) (WAF, secure coding)
- Man-in-the-Middle Attack (MITM) (⇔ digital signatures, hash functions, encryption)


**3.Availability**:
Ensures that authorized users have access to information and systems when needed.
System downtime has to be minimized.

**Attacks threatening Availability and countermeasures**
- DoS/DDoS Attack (Denial of Service/Distributed Denial of Service)
- (WAF, hardware redundancy, backups etc..)
- Ransomware (patching (security update))
__________________________________________________________________________________________
**Ransomware**:
Is a type of malware that holds a victim's data or device hostage, threatening to keep it locked or worse unless the victim pays a ransom to the attacker.
A type of malware that encrypts all data and files on device and demand ransom to decrypts them.


**Topic: LockBit**
- Ransomware (double extortion ransomware)
- malware
- encrypt all the files and data
- extort ransom for decrypting data
- extort ransom otherwise they expose these stolen data


**Next Generation Ransomware:**  
**Double Extortion Ransomware:** 
- extortion 1: if the victim pay ransom, they won’t decrypt the files
- extortion 2: if the victim pay ransom, they will disclose the files they stole


**LockBit**
- Ransomware (expecially, double extortion ransomware)
1. extort ransom for decrypting data
2. extort ransom otherwise they expose these stolen data (even DDoS attack)
- RaaS (Ransomware-as-a-Service) Model
- more than 2,000 victims, more than $120 million ransom
- Developers are still unknown

**LockBit versions**
- LockBit 1.0 (2019): simple ransomware
- LockBit 2.0 (2020): adopt double extortion and RaaS model
- LockBit 3.0 (2021-): also known as “LockBit Black”
- more sophisticated attack/encryption/defense evasion methods
- sell the stolen data at auction
- more sophisticated affiliate system

Topic: LockBit:
**Operation Cronos**
- global operation (11 countries joined)
- Feb 20th 2024, 34 servers took down,
- 4 servers seized, 2 people arrested,
- source codes and 1,000 descriptions key seized

**Caesar cipher**:
In cryptography, a Caesar cipher, also known as Caesar's cipher, the shift cipher, Caesar's code, or Caesar shift, is one of the simplest and most widely known encryption techniques. 
It is a type of substitution cipher in which each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet.

**Worm**
- multiply by themselves (make their own copy on infected devices)
- initially infected through internet (downloaded from suspicious website), 
- phishing email (as attachment file)
- **Worm example:** Stuxnet

**Stuxnet**
-  a worm virus
-  in 2010, infected in Nuclear Power Plant in Iran
-  initially infected with USB memory stick
-  multiplied through internal network
-  change setting of uranium centrifuge through Siemens SCADA controller
-  caused serious physical damages on the power plant
-  through this incident, malware started to be seriously recognized as cyberweapon

**Keylogger**
-  monitor user’s keystroke and steal credential information
(id/password, banking information etc..)
-  send stolen info to their owner (hacker)

**Two types of Keyloggers:**
- Software Keylogger (can also collect chat message / website access log)
- Hardware Keylogger (USB type / Keyboard embedded type)

**Trojan (named after Trojan war (ancient Greek mythology))**
- downloaded as a legitimate/safe software, but malicious code is wrapped
inside (encrypted in general)
- act as backdoor and receive command from their owner(hacker) and execute another malicious code
**Trojan example:** Zeus (Zbot), Emotet

**ZeuS (Zbot)**
-  Banking Trojan
-  first observed in 2007
-  have combined features (Trojan, Keylogger, Infostealer)
-  initially infected through Internet (downloaded from malicious website), phishing email (as attachment file)

**Emotet**
-  first observed in 2014
-  started from Banking Trojan, and obtained a lot of features over time
-  have combined features (Trojan, Keylogger, Infostealer, Downloader)
-  initially infected through Internet (downloaded from malicious website),
phishing email (as attachment file)
-  the central control server was taken down in 2021 
(Operation Ladybird) and soon resumed activity

**RAT: Remote Access Trojan**
- combined features (Trojan, Backdoor, Downloader, Keylogger, Infostealer)
- after compromising system, hackers attempt to download RAT for further malicious activities

**Downloader**:
-  malware used to download another malware

**Downloader example:** Trickbot, Emotet

**Dropper**
-  infected in target devices impersonating harmless software
-  malicious code is hidden inside the source code (gerenally encrypted)
-  by using malicious code, dropper tries to download another malware

Difference between **Trojan** and **Dropper**
- Trojan: after infected, it works as backdoor
- Dropper: after infected, it tries to download another malware

**Backdoor**
-  door put on compromised system by hacker
-  backdoor enables hackers to intrude the system anytime even after system
administrator patched the vulnerability (after patching, backdoor remains)

**Webshell**
-  a type of backdoor
-  tiny program written in programming language (PHP, Java etc..)

**Bot / Botnet**
-  Bot: device infected by malware and the control of hacker
-  Botnet: devices controlled by bot malware
-  Botnet devices wait for commands from hacker
-  **C2 (Command and Control) Server**: server used by hacker to send command to Botnet devices
-  by using botnet devices, hackers attempt to make DDoS attack
Botnet malware example: mirai

**mirai**
-  Botnet malware
-  first observed in 2016
-  their main target was vulnerable IoT devices
-  infected with using default telnet credential of IoT devices
(default credential mostly used in IoT devices was admin/admin)
-  with using mirai botnet, hackers executed DDoS attack to many companies
(one of the biggest DDoS attack executed by malware botnet)
-  since its source code was released on hackers forum, a lot of subspecies have been generated

**Cryptominer**
-  use infected device’s computer resources illegally and mine virtual currency
-  don’t do any other harmful activity
-  downloaded by malicious HTTP request sent to vulnerable web application server

**Spyware**
-  monitor user activity in infected device and steal information
-  have combined features (Keylogger, Trojan)
-  infected by phishing email, downloading from suspicious websites

**Ransomware**
-  encrypt all the data and files and ask for money
Ransomware example: WannaCry, LockBit

**WannaCry (WannaCrypto)**
-  have combined features (Ransomware, Dropper)
-  first observed in 2017
-  infected in over 300,000 computers of over 150 countries
-  many important organizations (hospital, company, government) infected
-  use vulnerability of SMB protocol (MS17-010)
by using special exploit code (EternalBlue) leaked from NSA
- **SMB(Server Message Block)**: resource sharing protocol on Windows network
- **MS17-010**: vulnerability existing in SMB protocol implementation
- **EternalBlue**: exploit code for MS17-010 developed by NSA
- **NSA(National Security Agency)**: US national security agency

**Adware**
-  display advertisement / caution on desktop
-  do not do any malicious activity, but unwanted ads are so irritating

**Fake Antivirus Software**
-  impersonate legitimate antivirus software and display fake caution aiming to make victims to click button
-  by clicking button, another malware is downloaded
-  use method like phishing/social engineering to deceive victims

**Macro Virus**
-  malicious Microsoft Office file (Word, Excel etc..)
-  by malicious VBA code, another malware is downloaded for further attack

**Polymorphic (Mutation) Virus / Metamorphic Virus**
-  encrypt or change the entire of their malicious codes to avoid being detected by security products
-  they can avoid not only signature-based detection, but also behavior-based detection (to detect them, you have to use anomaly detection)
- **Signature-based**: detect malicious code pattern of malware
- **Behavior-based**: detect malicious behavior of malware
- **Anomaly**: detect abnormal behavior/event comparing with their normal state
(abnormal command execution, suspicious internet traffic, abnormally large amount of traffic etc..)
__________________________________________________________________________________________
**Types of Hackers**
- **Malicious Hackers (Black Hat)**:
break into systems illegally, and steal, alter and destroy company/people’s information
- **Ethical Hackers (White Hat)**:
legal hackers, fight against Black Hat hackers
- **Grey Hat Hackers**:
between black&white, gather vulnerability information and offer to fix it to the owners for money
- **Script Kiddies**:
inexperienced hackers, just use exploits created by talented hackers
- **Hacktivists**:
act for their political agenda (Anonymous)
- **State-Sponsored Hackers**:
highly skilled hackers employed by governments
__________________________________________________________________________________________
**Cyber Kill Chain (Hacking Phases)**
- **Reconnaissance**:
gather useful information for attack
- **Weaponization**:
create hacking tools(malware, exploit codes)
- **Delivery**:
deliver exploits into targets’ network/devices
- **Exploitation**:
exploit vulnerabilities with exploit tools
- **Installation**:
install malware/backdoors to maintain unauthorized access
- **Command & Control**:
establish communication channel b/w malware and attackers server
- **Actions on Objectives**:
system destruction, data exfiltration.. anything you can!
__________________________________________________________________________________________
**To Do List**
- **Recon & Port Scanning**:
detect active host devices, and detect open ports and softwares working on the hosts
- **Research Vulnerability info (Google Search)**:
know what the vulnerabilities are like, and how to exploit them
- **Attack**:
exploit vulnerabilities and intrude into the system
- **Do Anything you want !!**:
ex: system destruction, data exfiltration
__________________________________________________________________________________________
**Kali Linux**:
Linux OS designed for hackers
This is a specialized Linux operating system used primarily for digital forensics and penetration testing. It's like a Swiss Army knife for cybersecurity professionals, packed with tools that can test and probe computer systems to find vulnerabilities.

**Metasploitable2**:
Linux Server OS designed for Hacking demo
__________________________________________________________________________________________
**Recon & Port Scanning**
1st Phase
- **Ping Sweep**
scan the entire network/subnet and detect reachable host (# nmap -sn -PE 192.168.56.0/24)

2nd Phase
Port Scanning
- **TCP Scan (connect scan)**:
scan with connection (log remains) (# nmap -sT 192.168.56.5)

- **Syn Scan (stealth scan)**:
scan without connection (log NOT remains) (# nmap -sS 192.168.56.5)

- **Software Version Scan**
detect software versions on each port (# nmap -sV 192.168.56.5)

- **OS scan**:
detect OS (Windows, Linux, Mac etc..) (# nmap -O 192.168.56.5)
__________________________________________________________________________________________
**Metasploit Framework Commands**
- **msfconsole**:
activate metasploit framework

- **search**:
search exploits/payloads
- **use**:
select exploits
- **show info**:
refer to exploits information
- **show options**:
refer to current settings of the selected exploits
- **set**:
add settings to the selected exploits
- **exploit**:
run the selected exploits
__________________________________________________________________________________________
**Type of Backdoors (bind shell vs reverse shell)**
- **bind shell**:
connection created from hacker to victim

- **reverse shell**:
connection created from victim to hacker
__________________________________________________________________________________________
**Search Vulnerability Information**
- **Google Search is like a treasurebox!**
major useful information source: CVE info, vendor web page, PoC(Exploit Codes available on GitHub), sec researchers’ blog, ChatGPT etc..
__________________________________________________________________________________________
**Targeted Attack**
- a type of cyber attacks
- hackers specifically aimed at a particular individual, company, or organization. 
- unlike broad attacks that target many(like script kiddies), targeted attack is like a sniper aiming at a specific target.
- attackers usually gathers information about their target in advance to increase their chances of success spending a lot of time.


**Port Scanning**
- A technique used to identify open doors or weak points in a computer or a network. Imagine your computer like a house with many doors (ports). 
- A port scan is like someone checking each door to see if it's locked or not. If they find an unlocked door (open port), they might use it to gain unauthorized access.

**Famous tools:**
- **Nmap**    https://nmap.org/
- **Hping3**  https://linux.die.net/man/8/hping3

**Anonymization Software**
- tools used to hide someone's identity when they are using the internet. 
- it's like wearing a mask and a cloak in a digital world so no one can recognize you or track your activities even though you plan to hack some company or kill someone. (technically, so many layers of encryption by so many routers enables this technology. Reference)
- with using this tool, you can reach a lot of illegal websites and contents easily

**Famous tool:**
- **Tor Browser (TOR = The Onion Router)** https://www.torproject.org/download/
It enables you to access illegal websites and contents generally hidden from us and no one can reach publicly without the tool

**Underground Forums**
- illegal forums located on dark web 
- people frequently discussing and trading illegal information or services, like hacking tips or stolen data. It's a shady, secretive part of the internet where bad guys might hang out to do their business away from the eyes of the law.

**Dark Web**
- one of the categories of www web pages
- no one can reach without anonymizing tool
- there are a lot of illegal contents on these pages (ex: illegally stolen info like credit card/passport, malware/exploit source codes, underground forums, services doing anything on behalf of you like cyber attack/killing someone etc..)

  **There are 3 types of web pages:**
- **Surface Web**: the web pages that everyone can access
- **Deep Web**: the web pages protected by passwords, and limited people who know the credential can access (ex: MyPage for each customer on EC sites)
- **Dark Web**: Reference: Silk Road(film)

**Free USB Memory**
- old-fashioned way of hacking
- attackers drop USB memory stick on the street on purpose, expecting someone(office staff in the target company) picking it up, bringing back to their office, and plugging into their own computer.
- there is malicious software inside the USB, so once the officer plug it, the malware activate and compromise the system and gain control.
- with using that compromised computer, hackers start to explore the target company’s internal network.

**Social Engineering attack**
- not a technical method

  **Social Engineering methods:**
- **Piggybacking / Tailgating**: break into office building following employees who have their own staff identity card.
- **Dumpster Diving / Scavenging**: check trash bins for sensitive information(like a piece of paper on which passwords and any kinds of credentials written on it)
- **Phishing**: sending emails and making phone calls to employees by impersonating someone like their boss and their client. 
On that email or phone call, attackers use fascinating topics like as a bait/lure to make them open malicious attached file(commonly malware), and obey attackers’ order.

**Zero-Day Attack**
- attack that happens on the same day a vulnerability in software is discovered
- hackers are always look for these zero-day vulnerabilities to exploit them before the software makers fix it.

 **Famous method to find zero-day vulnerability**: 
- **Reverse Engineering**: analyze software’s source codes for unknown vulnerability
- to find zero-day vulnerability, pretty high level and wide range of skills and knowledge on programming, software, web application, and are required.
