### 👉 Guessing Attack:
- Guess possible password.
- People tend to use simple(easy to memorize) password in nature ex: “123456”, “password”, “admin”.
- Guessing Attack generally uses OSINT technique.
_________
### 👉 OSINT (Open Source Intelligence):
- Technique used to gather valuable information that is publicly accessible (data source is generally the Internet).
- In password cracking context, SNS (Social Network Service/Site) is the most beneficial data source ex: Instagram, FaceBook, X, TikTok, LnkedIn.
- People tend to use password based on their personal information.
_________
### 👉 Dictionary Attack:
- Hackers attempt to crack passwords with using Dictionary.
- “Dictionary” is a word list of generic terms and names (like the name of a specific person, countries, rivers and mountains, fruits and vegetables etc..).

**COUNTERMEASURE**: 
- use strong and unguessable password.
_________
### 👉 Password List Attack:
- Hackers attempt to crack passwords with using Password List.
- “Password List” is the list of the passwords leaked from many compromised companies.
- Password Lists are shared in hackers’ community in the dark web and updated frequently.
- If you use the same passwords for several services, that means your accounts are vulnerable to Password List Attack (people tend to share the same password with several services, because it is easy to remember).

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
- Account Lockout is not a perfect way, because hackers can bypass Lockout by trying to brute force VERY SLOWLY, or using Reverse Brute Force Attack method.

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
- Password Hash: string generated from plaintext password with using specific algorithm (Hash Algorithm).
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
_________
