# Guide:
-	Always use **Virus Total** and **Fortiguard**.
-	If the **Action** is **Blocked**, **Dropped** or **Deny**, most likely the **Impact level is 1**.
-	If both **Source IP** and **Destination IP** are **Public**, then it is **Inbound Traffic Direction**, most likely you will need to check the location of the Public IP’s Aswell, using VirusTotal.
-	If **Action** is **Detected**, always check if the **Message** and the **Service** matches. 
Example:
If the Message is about Router attack and the Service is HTTP or HTTPS (Web server), it means the Service will not get affected since the attack is not for the Web server, impact level will probably be 1, and if the Message and Service matched, most likely the Impact level is 2.
-	If the Action is **Alert**, the possibility of **Impact level is 2**.
-	If the Traffic destination is Outbound, you can use **“Since the Outbound traffic seems to be communicating”** and if it is Inbound traffic always use **“Since the Destination is Web server (only if the Service is HTTP/HTTPS)”**
 <br>
 <br>
 <br>
 <br>
 <br>
<pre>
<code>
Sample1 Fortigate

alertContents_totalCount: 1
Detecting device name: 
LogType: UTM
LogSubType: Virus
EventType: Infected
Occurrence Date: 2024-02-28 10:42:33 +0900(JST)
SourceIP: 192.168.28.127
DestinationIP: 192.249.121.105
SourcePort: 52417
DestinationPort: 443
Protocol: TCP
Source IP after NAT translation:
Destination IP after NAT translation:
Destination Port after NAT translation:
Application:
Action: blocked
Message: File is infected
HashValue: 935c5af73b9feaa8165e737b60b0b6912b2d35ee7e39f8f9a1df551804123c32
URLCategory:
FileName: Trust.php
Malware Detection Name: J5/RefC.G!tr


ANSWER:
Sample1 Fortigate

alertContents_totalCount: 1
SourceIP: 192.168.28.127 → Private IP Address
DestinationIP: 192.249.121.105 → Public IP Address. No malicious Information Malware
Detection Name: J5/RefC.G!tr → Malware Classified as a Trojan horse
Action: blocked
HashValue: 935c5af73b9feaa8165e737b60b0b6912b2d35ee7e39f8f9a1df551804123c32
→ No information is founded
FileName: Trust.php → No information related to the detection name was obtained.

Vendor Site Link: https://www.fortiguard.com/encyclopedia/virus/8186550

Traffic Direction: Outbound Traffic
Impact Level: 1
Analyst Comment:
Detects files determined to be malware. No malicious information about hash values or
file names. File is blocked and also this is one time detection.
Judging from the above, no impact is expected.
</pre> 
</code>
<br>
<br>
<pre>
<code>
  Sample2 fortigate

alertContents_totalCount: 1
Detecting device name:
LogType: UTM
LogSubType: ips
EventType: signature
Occurrence Date: 2024-02-28 10:42:33 +0900(JST)
SourceIP: 10.204.131.100
DestinationIP: 44.238.188.166
SourcePort: 52417
DestinationPort: 80
Protocol: TCP
Source IP after NAT translation:
Destination IP after NAT translation:
Destination Port after NAT translation:
Application:
Action: dropped
Message: apache: Apache.Log4j.Error.Log.Remote.Code.Execution,
HashValue: 
Service: HTTP
HostName: prod.telemetry.ros.rockstargames.com
URLPath: /gta5/11/gameservices/Telemetry.asmx/SubmitRealTime


ANSWER:
Sample2 Analysis

alertContents_totalCount: 1
SourceIP: 10.204.131.100 → Private IP Address
DestinationIP: 44.238.188.166 → Public IP Address. No malicious Information 
Message: apache:Apache.Log4j.Error.Log.Remote.Code.Execution, 
Action: dropped
HostName: prod.telemetry.ros.rockstargames.com → No malicious information
URLPath: /gta5/11/gameservices /Telemetry.asmx/SubmitRealTime
→ No malicious information

Vendor Site Link: https://www.fortiguard.com/encyclopedia/ips /51006 
Referenced website: https://raxis.com/blog/log4j-exploit /


Traffic Direction: Outbound Traffic 
Impact Level: 1
Analyst Comment:
Detected attacks targeting vulnerabilities in Apache Log4j on outbound traffic.
From destination IP and URLPath, the destination seems like sites related to the game. Judging from the above, 
this alert is unlikely to be an attack. Traffic is dropped and no impact is expected.
</pre> 
</code>
<br>
<br>
<pre>
<code>
  Sample3 fortigate

alertContents_totalCount: 5
Detecting device name:
LogType: UTM
LogSubType: ips
EventType: signature
Occurrence Date: 2024-02-28 10:42:33 +0900(JST)
SourceIP: 10.193.148.100
DestinationIP: 76.223.0.112
SourcePort: 52417
DestinationPort: 80
Protocol: TCP
Source IP after NAT translation:
Destination IP after NAT translation:
Destination Port after NAT translation:
Application:
Action: dropped
Message: apache:backdoor:Mazben.Botnet,
HashValue: 
Service: HTTP
HostName: 
URLPath: 


ANSWER:
Sample3 Analysis

alertContents_totalCount: 5
SourceIP: 10.193.148.100 → Private IP Address
DestinationIP: 76.223.0.112 → Public IP Address. No malicious Information
Message: apache:backdoor: Mazben.Botnet,
Action: dropped

Vendor Site Link: https://www.fortiguard.com/encyclopedia/ips/29874

Traffic Direction: Outbound Traffic
Impact Level: 1 ~ 2 
Analyst Comment:
Level 1 Pattern
Detect outbound traffic seems like communicating with botnets.
There is no malicious information or information relates to C2 server founded from IP address.
Traffic is dropped and no continuous outbound traffic is confirmed.
From above information, currently determined that the behavior is not caused by malware.
Wait and see subsequent traffic.

Level 2 Pattern
Detect outbound traffic seems like communicating with botnets. continuous outbound traffic from the same source IP is happening. Sent a report to Customer.
</pre> 
</code>
<br>
<br>
<pre>
<code>
  Sample4 paloalto

alertContents_totalCount：3
Detecting device name: 
LogType: Threat
LogSubType: Spyware
EventType: Infected
Occurrence Date: 2024-02-28 10:42:33 +0900(JST)
SourceIP: 192.168.15.127
DestinationIP: 203.119.40.1
SourcePort: 53
DestinationPort: 56000
Protocol: udp
Source IP after NAT translation: 183.90.245.22
Destination IP after NAT translation: 203.119.40.1
Destination Port after NAT translation: 53
SourceUser:
DestinationUser:
Application: dns-base
Action: alert
ThreatName: DGA:rsffxfxtuy.co.jp(109000001)
URLorFileName: rsffxfxtuy.co.jp
URLCategory:


ANSWER:
Sample4 Analysis

alertContents_totalCount: 3
SourceIP: 192.168.15.127192.168.15.127 → Private IP Address
DestinationIP: 203.119.40.1 → Public IP Address
ThreatName: DGA:rsffxfxtuy.co.jp (109000001)
URLorFileName: rsffxfxtuy.co.jp Randomness in the domain.
Action: alert

Vendor site:
https://docs.paloaltonetworks.com/pan os /9 1/pan os admin/threat
prevention/ dns security/domain generation algorithm detection

Traffic Direction: Outbound Traffic
Impact Level: 2
Analyst Comment:
Detect DGA in outbound traffic.
The Domain consist from random strings and Traffic is passing through.
Sent a report to customer and verify this traffic is intended or not.
</pre> 
</code>
<br>
<br>
<pre>
<code>
  Sample5 Fortigate

AlertMessage: communication blockage occurred due to suspicious port numbers in outbound traffic.
alertContents_totalCount: 42
Detecting device name:
LogType: traffic
LogSubType: forward
EventType:
Occurrence Date: 2024-02-28 10:42:33 +0900(JST)
SourceIP: 10.193.216.100
DestinationIP: 20.38.116.72
SourcePort: 62465
DestinationPort: 445
Protocol: TCP
Source IP after NAT translation:
Destination IP after NAT translation:
Destination Port after NAT translation:
Application:
Action: deny
Message:
HashValue: 
Service: SMB
HostName: 
URLPath: 


ANSWER:
  Sample5 Analysis

AlertMessage: communication blockage occurred due to suspicious port numbers in outbound traffic.
alertContents_totalCount： 42
SourceIP: 10.193.148.10010.193.148.100 → Private IP Address
DestinationIP: 20.38.116.72 → Public IP Address. No malicious Information
DestinationPort:445 → Well known port. Default port number for SMB (Server Message Block)
Action: deny

Traffic Direction: Outbound Traffic
Impact Level: 1
Analyst Comment:
Detection of outbound communication on suspicious port numbers. The port being used is typically associated with SMB communication. There is no malicious information at the destination, and it is being denied, so we will observe the situation.
</pre> 
</code>
<br>
<br>
<pre>
<code>
  Sample6 Fortigate

AlertMessage: Attempting communication to IP addresses utilized as sinkholes.
alertContents_totalCount: 1
Detecting device name:
LogType: traffic
LogSubType: forward
EventType:
Occurrence Date: 2024-02-28 10:42:33 +0900(JST)
SourceIP: 172.16.50.11
DestinationIP: 38.102.150.29
SourcePort: 32769
DestinationPort: 53
Protocol: UDP
Source IP after NAT translation: 219.127.93.162
Destination IP after NAT translation:
Destination Port after NAT translation:
Application:
Action: sinkhole
Message:
HashValue: 
Service: DNS
HostName: 
URLPath: 


ANSWER:
  Sample6 Fortigate

AlertMessage: Attempting communication to IP addresses utilized as sinkholes.
alertContents_totalCount：1
SourceIP: 172.16.50.11172.16.50.11 → Private IP Address
DestinationIP: 38.102.150.29 → Public IP Address. This IP has been designated as a sinkhole due to past malicious activity associated with it.
Action: sinkhole

Traffic Direction: Outbound Traffic
Impact Level: 2
Analyst Comment:
Detection of outbound communication to the sinkhole designated IP.
Report is issued due to suspicion of malware infection.
</pre> 
</code>
<br>
<br>
<pre>
<code>
  Sample7 Fortigate

customername: Androbotics (Japan)
alertContents_totalCount: 1
Detecting device name:
LogType: UTM
LogSubType: ips
EventType: signature
Occurrence Date: 2024-02-28 10:42:33 +0900(JST)
SourceIP: 141.113.218.209
DestinationIP: 183.90.245.22
SourcePort: 52417
DestinationPort: 80
Protocol: TCP
Source IP after NAT translation:
Destination IP after NAT translation:
Destination Port after NAT translation:
Application:
Action: detected
Message: web_app3: JetBrains.TeamCity.BaseController.Authentication.Bypass,
HashValue: 
Service: HTTP
HostName: www.androbo.co.jp
URLPath: /hax?jsp=/app/rest/server;jsp


ANSWER:
Sample7 Fortigate

customername: Androbotics (Japan)
SourceIP: 141.113.218.209 → Public IP. Germany IP Address.
DestinationIP: 183.90.245.22 → Public IP. Japan IP Address. Seems to be webserver.
Message: web_app3: JetBrains.TeamCity.BaseController.Authentication.Bypass,
→ Authentication Bypass vulnerability in JetBrains TeamCity.
(Intrusion Prevention | FortiGuard)
Action: detected
URLPath: hax?jsp =/app/ server;jsp → Seems like exploit code for this vulnerability
JetBrains.TeamCity
→ TeamCity is server software provided by JetBrains for continuous integration (CI) and continuous delivery (CD). It is used by developers as a tool to automate the building, testing, and deployment of software efficiently.

Traffic Direction: Inbound Traffic
Impact Level: 2
Analyst Comment:
Detection of an attack targeting vulnerabilities in JetBrains' TeamCity.
The destination appears to be a web server.
Posing a potential impact, need to send a report to customer.
</pre> 
</code>
<br>
<br>
<pre>
<code>
  Sample8 Fortigate

customername: Androbotics (Japan)
alertContents_totalCount: 1
Detecting device name:
LogType: UTM
LogSubType: ips
EventType: signature
Occurrence Date: 2024-02-28 10:42:33 +0900(JST)
SourceIP: 141.113.218.209
DestinationIP: 183.90.245.22
SourcePort: 41555
DestinationPort: 80
Protocol: TCP
Source IP after NAT translation:
Destination IP after NAT translation:
Destination Port after NAT translation:
Application:
Action: detected
Message: applications3: Cisco.RV340.Router.Arbitrary.File.Upload,
HashValue: 
Service: HTTP
HostName: 183.90.245.22
URLPath: /api/operations/ciscosb-file:form-file-upload


ANSWER:
Sample8 Fortigate

customername: Androbotics (Japan) 
SourceIP: 141.113.218.209 → Public IP. Germany IP Address.
DestinationIP: 183.90.245.22 → Public IP. Japan IP Address. Seems to be webserver.
Message: Message: applications3: Cisco.RV340.Router.Arbitrary.File.Upload,
→ Arbitrary File Upload Vulnerability in Cisco RV340 Routers. 
(Intrusion Prevention | FortiGuard)
Action: detected
URLPath: /api/operations/ciscosb-file:form-file-upload
→Seems like exploit code for this vulnerability 
Cisco.RV340.Router
→Cisco RV340 Router is a business-oriented router provided by Cisco Systems.
Router: A router is a network device that forwards data packets across different segments of a network.
Web server: server software that responds to HTTP requests from clients and serves web content, such as web pages or web application content.
→ Routers and web servers are different entities, vulnerabilities in routers do not affect web servers.

Traffic Direction: Inbound Traffic 
Impact Level: 1
Analyst Comment:
Detection of an attack targeting vulnerabilities in Cisco RV340 Router. The destination appears to be a web server. Since vulnerabilities in routers do not affect web servers, we determine that there is no impact.
</pre> 
</code>
<br>
<br>
<pre>
<code>
  Sample9 Fortigate

customername: Androbotics (Japan)
alertContents_totalCount: 1
Detecting device name:
LogType: UTM
LogSubType: ips
EventType: signature
Occurrence Date: 2024-02-28 10:42:33 +0900(JST)
SourceIP: 141.113.212.106
DestinationIP: 183.90.245.22
SourcePort: 46020
DestinationPort:443
Protocol: TCP
Source IP after NAT translation:
Destination IP after NAT translation:
Destination Port after NAT translation:
Application:
Action: detected
Message: applications3: Ivanti.Connect.Secure.SAML.SSRF,
HashValue: 
Service: HTTPS
HostName: www.androbo.co.jp
URLPath: /dana-ws/saml20.ws


ANSWER:
  Sample9 Analysis

customername: Androbotics (Japan)
SourceIP: 141.113.212.106
→ Public IP. Germany IP Address.
DestinationIP: 183.90.245.22
→ Public IP. Japan IP Address. Seems to be webserver.
Message: applications3: Ivanti.Connect.Secure.SAML.SSRF,
→Server-Side Request Forgery Vulnerability in Ivanti Connect Secure.
(Intrusion Prevention | FortiGuard)
Action: detected
URLPath: /dana-ws/saml20.ws
→ Seems like exploit code for this vulnerability
Ivanti.Connect.Secure
→ "Ivanti Connect Secure" is a secure remote access solution provided by Ivanti. 
It is software designed to allow remote workers and external users to securely access a company's network.
It offers VPN (Virtual Private Network) functionality to enhance security by encrypting data transmission. Additionally, it provides 
authentication features such as Single Sign-On (SSO) and Multi-Factor Authentication (MFA).

Traffic Direction: Inbound Traffic
Impact Level: 2
Analyst Comment:
Detection of an attack targeting vulnerabilities in Ivanti Connect Secure.
The destination appears to be a web server.
While it is rare for remote access solutions to be directly installed on web servers, it is not impossible. 
Need to send a report to customer.
</pre> 
</code>
<br>
<br>
<pre>
<code>
  Sample10 Fortigate

customername: Androbotics (Japan)
alertContents_totalCount: 1
Detecting device name:
LogType: UTM
LogSubType: ips
EventType: signature
Occurrence Date: 2024-03-27 10:42:33 +0900(JST)
SourceIP: 141.113.218.209
DestinationIP: 183.90.245.22
SourcePort: 16878
DestinationPort: 443
Protocol: TCP
Source IP after NAT translation:
Destination IP after NAT translation:
Destination Port after NAT translation:
Application:
Action: detected
Message: application3: Honeywell.PM43.Username.Command.Injection,
HashValue: 
Service: HTTPS
HostName: www.androbo.co.jp
URLPath: /loadfile.lp?pageid=Configure


ANSWER:
Sample10 Analysis

customername: Androbotics (Japan)
SourceIP: 141.113.218.209
→ Public IP. Germany IP Address.
DestinationIP: 183.90.245.22
→ Public IP. Japan IP Address. Seems to be webserver.
Message: application3: Honeywell.PM43.Username.Command.Injection,
→ Command Injection vulnerability in Honeywell PM43 Printers.
(Intrusion Prevention | FortiGuard)
Action: detected
URLPath: /loadfile.lp?pageid=Configure
→ Seems like exploit code for this vulnerability
Printers: Devices used for printing, focusing on the functionality of printing data.
Web server: Server software that responds to HTTP requests from clients and serves web content, such as web pages or web application 
content.
→ Printers and web servers are different entities, vulnerabilities in Printers do not affect web servers.

Traffic Direction: Inbound Traffic
Impact Level: 1
Analyst Comment:
Detection of an attack targeting vulnerabilities in Honeywell PM43 Printers.
The destination appears to be a web server.
Since vulnerabilities in printers do not affect web servers, we determine that there is no impact.
</pre> 
</code>
<br>
<br>
<pre>
<code>
  Sample11 Fortigate

customername: Androbotics (Japan)
alertContents_totalCount: 1
Detecting device name:
LogType: UTM
LogSubType: ips
EventType: signature
Occurrence Date: 2024-03-27 10:42:33 +0900(JST)
SourceIP: 109.248.103.181
DestinationIP: 183.90.245.22
SourcePort: 39968
DestinationPort: 80
Protocol: TCP
Source IP after NAT translation:
Destination IP after NAT translation:
Destination Port after NAT translation:
Application:
Action: detected
Message: misc: Oracle.Business.Intelligence.XML.Publisher.XXE,
HashValue: 
Service: HTTP
HostName: www.androbo.co.jp
URLPath: /xmlpserver/ReportTemplateService.xls


ANSWER:
Sample12 Analysis

customername: Androbotics (Japan)
SourceIP: 109.248.103.181
→ Public IP. Russian federation IP.
DestinationIP: 183.90.245.22
→ Public IP. Japan IP Address. Seems to be webserver.
Message: misc: Oracle.Business.Intelligence.XML.Publisher.XXE,
→External Entity Injection Vulnerability in Oracle Business Intelligence Publisher.
(Intrusion Prevention | FortiGuard)
Action: detected
URLPath: /xmlpserver/ReportTemplateService.xls
→ Seems like exploit code for this vulnerability
※You can see PoC in this website (Oracle Business Intelligence / XML Publisher 11.1.1.9.0 / 12.2.1.3.0 / 12.2.1.4.0 - XML External Entity 
Injection - Windows webapps Exploit (exploit-db.com))
What is PoC: Proof of Concept refers to a demonstration or evidence used to confirm the existence of a specific security issue or 
vulnerability.
Oracle.Business.Intelligence
→ Oracle BI is server-side software for business intelligence and analytics, performing data processing, analysis, and visualization.

Traffic Direction: Inbound Traffic
Impact Level: 2
Analyst Comment:
Detection of an attack targeting vulnerabilities in Oracle.Business.Intelligence.
The destination appears to be a web server.
Oracle BI is server-installable and executable software. Therefore, it is determined that it may have an impact on the target.
Need to send a report to customer.
</code>
</pre>
