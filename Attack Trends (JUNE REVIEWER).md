### 👉 Guessing Attack:
- Guess possible password.
- People tend to use simple(easy to memorize) password in nature ex: “123456”, “password”, “admin”.
- This attack generally uses OSINT technique.
_________
### 👉 OSINT (Open Source Intelligence):
- Technique used to gather valuable information that is publicly accessible (data source is generally the Internet).
- In password cracking context, SNS (Social Network Service/Site) is the most beneficial data source ex: Instagram, FaceBook, X, TikTok, LnkedIn.
- People tend to use password based on their personal information.
_________
### 👉 Dictionary Attack:
- Hackers attempt to crack passwords with using this list.
- It is a word list of generic terms and names (like the name of a specific person, countries, rivers and mountains, fruits and vegetables etc..).

**COUNTERMEASURE**: 
- use strong and unguessable password.
_________
### 👉 Password List Attack:
- Hackers attempt to crack passwords with using this List.
- it is the list of the passwords leaked from many compromised companies.
- they are shared in hackers’ community in the dark web and updated frequently.
- If you use the same passwords for several services, that means your accounts are vulnerable to this Attack (people tend to share the same password with several services, because it is easy to remember).

**COUNTERMEASURE**: 
* use unique passwords for each service
* Even though you use a strong password, once one of the web services you are using is compromised, hackerscan have access to your accounts on other web services.
_________
### 👉 Brute Force Attack:
- Try different passwords with the same userID.
- Try all combination of characters to crack password.
- PROS: if there’s enough time, you can crack the password for sure.
- CONS: it takes too much time, requires high computer specs.

**COUNTERMEASURE 1**: 
* Use strong password.
* At least 12 characters long (14 or more is recommended).
* A combination of uppercase letters, lowercase letters, numbers, symbols.
* Use unguessable password.

**COUNTERMEASURE 2**: 
* Use Account Lockout

### 👉 Account Lockout
- Lockout the account for a while if the number of login failure exceeds threshold.
- Threshold Example: 10 failures in one minute.
- it is not a perfect way, because hackers can bypass Lockout by trying to brute force VERY SLOWLY, or using Reverse Brute Force Attack method.

**Bypass User Account Lockout**:
* If the Lockout is 10x of login failure in 1 min, you can keep the failures 9x in 1 min.
* You can also uses Reverse Brute Force Attack.

### 👉 Reverse Brute Force Attack:
- Try same password with different userID.

![Time chat of crack your password](https://github.com/qpzmtb/VT-Trend/assets/173013469/8e8fb0a9-4d32-4651-8c85-3f6f0cf418d1)
_________
### 👉 Social Engineering Attack:
- A wide range of malicious activities accomplished through human interactions.
- “Social Engineering” is a generic term, so a lot of malicious activities through human interactions (phishing, piggybacking etc..) are categorized as this attack.
_________
### 👉 Shoulder Hacking:
- Look over the shoulder when the victim is typing password.
- COUNTERMEASURE: use privacy filter, lock screen before leaving seat.
_________
### 👉 Scavenging (Dumpster Diving):
- pick garbage can for password memo(sticky etc...).
- COUNTERMEASURE: shred password memo using shredder before throwing away.
_________
### 👉 Rainbow Table Attack (Offline Password Cracking):
- hackers steal password hash from the server, and crack password with using Rainbow Table.
_________
### 👉 Password Hash: 
- string generated from plaintext password with using specific algorithm (Hash Algorithm).
_________
### 👉 Hashing:
- Technique to calculate input string with specific algorithm(Hash Algorithm) to generate unique string.
- Each output value is totally unique for each input value.
- Length of output value is totally the same for each hash algorithm.

**there are many hash algorithms like**:
* MD5 : generate unique 128 bit (16 bytes) string
* SHA1 : generate unique 160 bit (20 bytes) string
* SHA256: generate unique 256 bit (32 bytes) string etc
* input string cannot be recovered from hashed string

![Hash chart](https://github.com/qpzmtb/VT-Trend/assets/173013469/d88071b3-3c88-4faf-9081-567814f10367)

### 👉 You can calculate hash values with:
- Linux commands: md5sum, sha1sum, sha256sum etc.

**Online tools example**:
1. Hash calculator:
https://www.pelock.com/products/hash-calculator
2. CyberChef (most common):
https://gchq.github.io/CyberChef/

### 👉 Hashing is used in situations like:
- Integrity check of files and communications (file integrity check example virtualbox download page).
- Authenticating users securely (Challenge-Response Authentication).
- Storing passwords securely Challenge-Response.

### 👉 Challenge-Response Authentication:
- Technique to authenticate user without transmitting the password over the internet.

**Authentication Flow**: 
* When a user requests to login, the authentication server generates a random string called “challenge” and sends it to the user, and the user combines their password with the challenge and calculates hash value, then the user sends back the calculated hash value to the server as “response”. When the server receives the response from the user, the server calculates in the same way as the user(combines Bob’s password with the challenge, and calculates hash value(response)), and then compares the response generated by the server with the one generated by the user. If the two values match, the user’s password is correct, and the server authenticates the user.

![image](https://github.com/qpzmtb/VT-Trend/assets/173013469/8c3e1893-af71-4c3d-a871-231161609412)

### 👉 Storing passwords securely:
- In general, authentication servers store only hashed passwords on their database and don’t store plain text passwords.
- By doing so, even though the hashed passwords are stolen, hackers are not able to recover the original plain text password.

### 👉 Strength of hash algorithm:
- Basically, plain text passwords cannot be recovered from hash values. This is the best reason why hashing is reliable for storing passwords securely.
- But, this doesn’t mean that all the hash algorithms are safe. As the time passed, the computing technologies have been improving drastically. So weak algorithms such as MD5, SHA1 are no longer feasible to use. Actually, MD5 and SHA1 are used in various situations even now, but we can’t
use them in storing passwords or in authentication flow.
________
### 👉 CRYPTREC Ciphers List:
- List of encryption/hash algorithms.
- Not only strong algorithms that should be used but also weak algorithms that should not be used are written in the list.
- Created and maintained by Japanese Government.
- By checking this list, people can decide which algorithm to choose to create secure systems.
- But hashing is not a perfect countermeasure, some hashed passwords are potentially vulnerable to Rainbow Table Attack.

### 👉 Rainbow Table:
- List of combination of password hash, original plain text password for each hash value, and hash algorithm used to generate the password hash.
- In general, rainbow tables are created by attackers using a lot of stolen passwords and these lists are shared in some black markets like the "Dark web".

**COUNTERMEASURE 1**: Use strong password

**COUNTERMEASURE 2**: Use Salt
________
### 👉 Salt:
- Random strings added to plain text password before hashing.
- Length: at least 128 bit (16 bytes).
- Salt is not a perfect way, because some servers are vulnerable to Pass-the-Hash Attack.
________
### 👉 Pass-the-Hash Attack (PtH):
- Hackers steal the password hash, and attempt to send them directly to the authentication server, and breach authentication (PtH is a type of replay attack).
- According to the best practice, authentication server have to accept only encrypted passwords, and deny to receive password hash (because the password hash sent by user might be the one stolen from the database).
- Some of the vulnerable servers don’t comply to the best practice, accept the stolen password hash, and authenticate malicious user as legitimate.

**COUNTERMEASURE 1**: Configure authentication server not to accept password hash.

**COUNTERMEASURE 2**: Use MFA.
________
### 👉 MFA (Multi-Factor Authentication):
- Authenticate users with multiple authentication factor.

**example**:
* Password + software authenticator (like Microsoft Authenticator).
* Password + OTP (One Time Password).
* Passwords could be cracked, so by using an additional authentication factor, we can strengthen the entire authentication process.
* But MFA is not a perfect countermeasure. Some of the MFA methods are vulnerable to MFA Fatigue Attack.
________
### 👉 MFA Fatigue Attack:
- Hackers send enormous numbers of MFA authentication request (generally, with push notification).
- At first users push Deny button, but the approval requests never ends (this is so annoying..), so at last they get tired and push Approve button and that’s how hackers bypass MFA.
- Premise: hackers must have done password cracking before executing this attack.
- COUNTERMEASURE: use strong password to prevent password cracking.
________
### 👉 About RockYou.txt:
- This is a password list and it contains 32,000,000 users’ passwords leaked from RockYou, Inc. (social application provider company) in 2009. The stolen passwords were various from easy guessable ones to complicated unguessable ones, and they were not hashed, so hackers were able to abuse them easily. RockYou.txt is not only used by hackers, but also used by ethical hackers and service developers.  With utilizing this password list, we can check the strength of the passwords stored on the database.
________
### 👉 Footprinting:
- The technique used for gathering information about computer systems and the entities they belong to.
- To get this information, a hacker might use various tools and technologies.
- This information is very useful to a hacker who is trying to crack a whole system.
- In computer security context, “Footprinting” generally refers to one of the pre-attack phases (in pre-attack phases, tasks are performed before doing the actual attacks).

### 👉 Commands and Tools used for Footprinting:
**nslookup**: 
* A network administration command-line tool for querying DNS (Domain Name System) to obtain the mapping between domain name and IP address.

**traceroute(tracert)**:
* A command-line tool. “traceroute” command can be used to map the network path to the destination host. You can get the IP addresses of the routers that will be traversed to reach the destination host.
* traceroute: for Linux, tracert: for Windows

**Nmap**:
* A port scanning tool.
_________
### 👉 Port Scanning:
- One of the actual techniques of footprinting.

**Port Scanning Tools**:
* Nmap (Network Mapper)
* Hping2, Hping3
_________
* Well-known Ports = System Ports : 0 - 1,023
* Registered Ports = User Ports : 1,024 - 49,151
* Dynamic Ports = Ephemeral Ports : 49,152 - 65,535
_________
### 👉 File Transfer: FTP (File Transfer Protocol)
- 20: Data Transfer Connection
- 21: Control Connection
_________
### 👉 Remote Access
- 23: Telnet (Teletype Network)
- 22: SSH (Secure SHell)
_________
### 👉 Send/Receive Email
**Send**:
* 25: SMTP (Simple Mail Transfer Protocol)

**Receive**:
* 110: POP3 (Post Office Protocol v3)
* 143: IMAP4 (Internet Message Access Protocol v4)
_________
### 👉 Special Usage:
- 465: SMTPS
- 587: SMTP Submission (OP25B: Outbound Port 25 Block)
- 993: IMAP4S
- 995: POP3S
_________
### 👉 DNS (Domain Name System): 53
_________
### 👉 Web
- 80 : HTTP (Hyper Text Transfer Protocol)
- 443: HTTPS (Hyper Text Transfer Protocol Secure)
_________
### 👉 Others
**123: NTP (Network Time Protocol)**
* you can adjust the time settings on the network devices in your network.

**161: SNMP (Simple Network Management Protocol)**
* You can manage all the network equipments in your network
* You can know the symptom of disorder and malfunction of the network devices

**389: LDAP (Light Directory Access Protocol)**
* You can manage all the network resources efficiently on a single server(LDAP Server)
network resources that can be managed: User Information(ID and Password), Network Device Information, etc..

**445: SMB (Server Message Block)**
* Network resources sharing protocol.
