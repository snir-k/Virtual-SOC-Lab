View my Linkedin profile:
https://www.linkedin.com/in/Snir-Kanias/

Assessment Lab-SOC Environment Of Snir Kanias 2020

This lab is simulating a SOC environment almost like in the real environment, 
with more control and ability to we creative with my Attack Vectors and Detect Methods Scenarios.
After every Attack, I've made research by tools like: Wireshark & ELK Stack - Kibana.
The results saved in folders by name of the tools.

I've choose to use Virtualbox platform. I've installed and configured my SOC Lab as follow:

Pfsence 2.4.5	Interfaces: WAN, SERVERS, LAN. Package of Snort was installed also.

Hosts:
Kali 2019 | ip Address: 10.10.0.5 | Net Mask: 255.255.255.0 Prefix: 24
Default Gateway: 10.10.0.1 | DNS Server: 10.10.1.1, 8.8.8.8

Windows 7 | ip Address: 10.10.0.4 | Net Mask: 255.255.255.0 Prefix: 24
Default Gateway: 10.10.0.1 | DNS Server: 10.10.1.1, 8.8.8.8

Windows 7 | ip Address: 10.10.0.3 | Net Mask: 255.255.255.0 Prefix: 24
WinSer.Domain | Default Gateway: 10.10.0.1 | DNS Server: 10.10.1.1, 8.8.8.8

Windows Server 2012R2 | ip Address: 10.10.1.100 | Net Mask: 255.255.255.0 Prefix: 24
Default Gateway: 10.10.0.1 | DNS Server: 10.10.1.1, 8.8.8.8

ELK | ip Address: 10.10.1.6 | Net Mask: 255.255.255.0 Prefix: 24
Default Gateway: 10.10.0.1 | DNS Server: 10.10.1.1, 8.8.8.8

pfsence
No Need for User name Or Password.

ELK Server
User Name: eliot | Password: emperor

Windows Server 2012 (Change Keyboard Language to EN)
User Name: Administrator | Password: aA123456

Windows 7 Bob WinServer Domain
User Name: bob | Password: Q1A2Z3!

Windows 7 eliot user
User Name: eliot | Password: kingartur

Kali Linux
User Name: kali | Password: kingartur


I've choose 3 scenarios in my project:

Attack Vector 1
LLMNR Attack: Between Kali Linux and Windows 7.
The user of Windows 7 received a phishing mail with a link in it from the security department. The orders were to click on the link which led him to download a malicious file, and save it in Download Folder. It will update his PC automatically, but he must leave his PC for 20 minutes.

Tools: Responder, ‘John The Ripper’
Scenario: The Attacker uses Kali VM with the Responder tool to get the NTLM Hash of the Windows 7 user.


Attack Vector 2
Mimikatz Attack: Between Kali Linux and Windows 7 via Shell prompt in the Terminal of Kali Linux.
Target: Run Mimikatz in Windows 7 user PC Remotely from Shell in Kali Linux.
Tools: Mimikatz, Metasploit2
Scenario: The Attacker uses Kali VM with the Metasploit2 tool, run an exploit to create a network flow session between his PC and the victim PC on Windows 7 machine.
The victim is open a mail and click the link to download a "Security Update" that he must download according to the administrator instructions.


Attack Vector 3
Pass The Hash: Between Kali Linux and Windows Server 2012 R2 via Shell prompt in the Terminal of Kali Linux.
The attacker attack a user in the server domai with pass the hash to get the NTLM Hash. Now he makes privilege Escalation and trying to access windows server 2012 to gain Admin password and control the Full Network. 

Target: Run msfconsole (metasploit) from Kali Linux terminal and use payload to get shell on Windows server 2012 R2. Migrating process lsaas.exe into process powershell.exe. enter the c:\users folder and running the command  'hashdump'. Copy the Hash of the  Administrator into text file. Save it the folder containing rockyou.txt file, and run John The Ripper to crack the Hash and reveal the clear password.  

Tools: Metasploit, John The Ripper,
Scenario: The Attacker uses Kali VM to attack Windows Server 2012 R2 with Pass The Hash. His goal to get the hash of the administrator and convert it to a clear text password.

The Attack Vectors results can be download here:
https://mega.nz/file/xYt2DJ4b#35e9X0B03S99lCNNLzVaop-cGfHRUjfcJkg4dWl7dis

Password for the zip file: soclab2020
