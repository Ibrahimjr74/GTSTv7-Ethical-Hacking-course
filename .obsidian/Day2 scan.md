## Topics
- What is Scanning?
- Why do we scan?
- Network Scanning
- Nmap
- Host detection
- Port Detection
- OS detection
- Banner Grabbing
- NSE
- Firewall Evasion Techniques
## Scanning and Enumeration
 - It is the second phase of hacking that we gain more information and how yo do a measurement on certain system .
 - it refers to the package oof techniques or procedures used to identify hosts, ports, and various services within system.
 The difference between Reconnaissance and Scanning

- Reconnaissance: [[Day1_info.md]]Focuses on broad, high-level information about the target. It may include:
- Organizational structure and employee details (social engineering possibilities).
- Publicly available IP addresses and domain names.
- Technology stack (e.g., web servers, frameworks).
- Potential entry points from open sources (e.g., website vulnerabilities, exposed subdomains).
- Scanning: Focuses on technical, low-level details about the target’s systems, such as:
- Open ports and services.
- Operating system and service versions.
- Network topology.
- Specific vulnerabilities in the systems and services.

- There are Many kinds of scanning methods and tools for different purpose.
    

- For Network mainly: NMAP,netdiscovery
- For Subdomain: Sublist3r,subfinder,amass
- For website:**Nuclei , Nessus, Acunetix.

## NMAP - Network mapper

- Nmap is A network scanning and exploring tool used by network and security experts.
    used to Scan Networks, Ports, OS .
### Live system discovery
means checking up running hosts(client/server) on networks.
ping swap works by sending echo request and echo reply and uses ICMP packets for checking purpose
**It sends Echo request and waits for response if there is Echo reply then that system is up!**
let's see first what is HOP means
 - A hop _occurs when a packet is passed from one network segment to the next_. Data packets pass through routers as they travel between source and destination
### TTL : time to leave
- determines how ling a packet should exist in the network before being discarded
- Decrementing TTL : Each time the packet passes through a router (a hop) the TTL value is decreased
- TTL Expiration: if the TTL reaches 0, the packet is discarded,  and an ICMP "Time Exceeded" Message is sent back to the sender. 

**Nmap ping sweep
nmap can perform ping sweep too

```
nmap sn IP

```

-sn  = no port scan

***How do we know the user of our networks or all host on a networks
```
nmap -sn NetworkAddress-255
```
but it will not  work for Virtual machines networks

## what is port?


- port is like gate way to application or specific and physical serving as a communication end point , with  unique number which is used by the Transport layer protocols
- There are many port numbers types of port like  for wind - windows 
     for human - door
- There exist 65,536
- 1 - 1024 reserved well known
- HTTP(80) unsecured web supports
- TTTPS(443) secured web port
- FTP(21) File transfer port
### Port status
- Open ports : these are any open ports that can accept any request
- closed ports: these are ports not accept any requests
- Filtered ports:**These are ports which nmap is not sure of being open or closed.**
### Open port discovery

- On some system ports can be open for some purpose 
- Example: 
- anywhere when you access websites there is web port open(80,443,8080 mostly), 
- If you are getting some shell activity there is port 22 open
- The Main problem/Vulnerability is there Might be some ports open without intention or Opened once and forgot closing, this leads to attack
- We can use nmap to check which port is open/closed
- And this is called port discovery
- Syntax:
- nmap IP    =>    only the 1000 ports
- nmap -p port 1,port2,port3 IP     =>    only    port 1,2,3
- nmap -p- IP     =>  All the 65K port


**Doing ping sweep is way of Active Recon. Doing so we can caught by the security teams , SOC analysts when we try to do pings plus some organizations block our ICMP request => eventually by making all hosts down but it is normally up.
 #### But Hackers Have an idea ....
 The command `nmap -Pn IP` is a network scanning command using the Nmap tool. Here's a breakdown of its components:

- **nmap**: This is the name of the network scanning tool, Nmap.
- **-Pn**: This option tells Nmap to skip the "ping scan" phase, which is typically used to determine if a host is alive before scanning its open ports. By skipping this phase, Nmap can potentially scan faster, but it may also scan hosts that are not actually active.
- **IP**: This is the IP address of the host you want to scan. Replace "IP" with the actual IP address you want to target.

So, in essence, `nmap -Pn IP` will scan the open ports of the specified IP address without first checking if the host is alive using a ping scan. This can be useful in certain scenarios, but it's important to be aware that it may also scan hosts that are not actually active.

#### Red team Perspective
Port scanning is sending of TCP request for that specific port try to connect
#### Blue team Perspective
**Every Port Connecting Trials are Recorded in the network packets you send**

The command `nc -nv IP port` is used to test network connectivity to a specific host and port. Here's a breakdown of its components:

- **nc**: This is the name of the netcat tool, a versatile network utility.
- **-n**: This option tells netcat to skip DNS resolution, meaning it will use the IP address directly instead of trying to resolve it to a hostname.
- **-v**: This option enables verbose output, which will provide more information about the connection attempt.
- **IP**: This is the IP address of the host you want to connect to.
- **port**: This is the port number you want to connect to on the specified host.

So, in essence, `nc -nv IP port` will attempt to connect to the specified IP address and port. If successful, it will display a message indicating a successful connection. If unsuccessful, it will provide information about the error that occurred. This command is often used to quickly check if a server is listening on a particular port.

## Scanning Methods

Nmap scans network in different modes

1. TCP connect (TCP scan)
    to be reliable it must establish connection in which 3 way HANDSHAKE -> SYN-> 
    <-SYN-ACN ,ACN->
```
    nmap -sT IP
```
2. TCP SYN (Stealth scan)

- This is TCP scan but here we dont send the last ACK flag.
- But we send the RESET flag.
- Syntax:
```
    sudo nmap -sS IP
```
3. UDP scan
    - This is a method to scan if any service/port is using UDP
```
    sudo nmap -sU IP
```

4. Xmas scan
- Here, The 1st thing to send is FIN/PSH/URG instead of SYN.
- If there is response like RST flag Then the system is close
- If there is no response the system is open.
- Syntax:
```
sudo nmap -sX IP
```

### Operating System Detection
**- Nmap have a feature to detect the operating system of the host. 
- Syntax:
- sudo nmap -O IP => OS detection only
sudo nmap -A IP     => OS detection including version

## Banner Grabbing

is a technique used in network security to gather information about a system or service by analyzing the banner messages it sends. A banner is a text message that is displayed when a connection is established to a service. It often contains information about the service, the version number, and sometimes even the operating system or software used.

**Why is Banner Grabbing Important?**

1. **Vulnerability Identification:** Many vulnerabilities are specific to particular versions of software. By identifying the version of a service, attackers can research known vulnerabilities and exploit them.
2. **System Identification:** Banner grabbing can help to identify the type of system or device you're connecting to. This can provide valuable information about its capabilities and potential vulnerabilities.
3. **Service Discovery:** Banner grabbing can be used to discover which services are running on a system and on what ports. This information can be used for further reconnaissance or potential attacks.
## Scan Speeds

- When nmap do its scan, it have a time waiting, after sending 1 packets to a host.
- There are 5 time waitings.

- The nmap time template is -T<0-5>
- Insane -T5 waits only 0.3 to respond
- Aggressive -T4 T5 waits only 1.25 to respond
- Normal -T3 This is a default nmap timing
- Polite -T2  Slower often recommended for risky projects tests
- Sneaky -T1 " "                              "  "
-
    
    
## Nmap Scripting Engine (NSE)

The Nmap Scripting Engine (NSE) is a powerful feature of Nmap that allows you to extend its capabilities by running scripts against targets. These scripts can perform a wide range of tasks, including:

- **Vulnerability scanning:** Identifying known vulnerabilities in target systems.
- **Service fingerprinting:** Gathering detailed information about running services.
- **Port scanning:** Scanning specific ports or ranges of ports.
- **Protocol analysis:** Examining network traffic to identify anomalies or security issues.
- **Custom tasks:** Performing any other network-related task that can be automated with scripting.

**How NSE Works:**

1. **Script Selection:** You specify the script(s) you want to run using the `--script` option in Nmap.
2. **Script Execution:** Nmap executes the scripts against each target.
3. **Output:** The scripts generate output, which is typically displayed in the Nmap output.

**Key Features of NSE:**

- **Large Script Library:** Nmap comes with a vast library of pre-written scripts covering a wide range of security and network tasks.
- **Custom Script Development:** You can write your own scripts using Lua, a popular scripting language.
- **Script Categories:** Scripts are organized into categories (e.g., "vulners", "discovery", "ports") for easy management.
- **Script Arguments:** Many scripts accept arguments to customize their behavior.

**Example Usage:**

To scan a target for known vulnerabilities using NSE scripts, you can use the following command:

Bash

```
nmap --script vulners <target>
```

- Some known scripts.
- --script banner  
- =>   grabbing some details
- --script broadcast  
-   reveals broadcast information
- --script vuln  
-   test if the ports are vulnerable.
Nmap m Out puts can be saved

- the “-oG|-oX|-oN”
- -oG -> For Greppable formats
- -oX -> for xml formats
- -oN -> for Normal Saving Format

**Verbose** in the Linux system refers to a mode of operation that provides detailed output or information. It's often used to help with debugging or troubleshooting issues, as it can reveal more specific details about what's happening behind the scenes.

**Here are some common examples of verbose output in Linux:**

- **Command-line tools:** Many command-line tools have a verbose mode that can be activated using a specific flag or option. For example, `ls -l` lists files in long format, but `ls -al` lists files in long format with all hidden files included.
- **System logs:** System logs can be configured to record events at different levels of detail. A more verbose log level will capture more information, including error messages, warnings, and informational messages.
- **Debugging tools:** Debugging tools like GDB (GNU Debugger) can be used to step through code line by line and inspect variables. In verbose mode, these tools can provide more details about the execution of the program.


## Nmap Firewall Evasion
- Firewall Evasion Techniques Using Nmap is a subnet of network security exploration aimed at bypassing or circumventing fire wall protection
- IDS(Intrusion Detection System) installed on server and monitors the Traffic of Network flow or system for signs of malicious behavior, policy violations, or other un authorized activities.


1.Decoy Scan
- Nmap employs decoy IP addresses to obscure of scan , complicating the identification of the actual of actual scanner.
- we can specify multiple decoy IP addresses using the -D option within the Nmap command.
- nmap -D decoy1, decoy2, decoy3 .... [Target IP]
- You Can Make Nmap to add some random IPs
- Nmap -D RND:5 … [Target IP]
- This makes it Hard for the sysadmin to block our real ip
2.Fragment Packet
- Fragmented requests refer to the technique of sending packets in smaller fragments rather than as whole packets. 
- This is done to evade detection by firewalls, intrusion detection systems (IDS), or intrusion prevention systems (IPS) that rely on analyzing entire packets to detect malicious activity.
- To Perform this:
- nmap -f -p21 [Target IP]
3.**MAC Address Spoofing**
- This approach is by regenerating a fake MAC Address in order not to be blocked 
- **nmap -spoof-mac Apple/MAC_ADDRESS -Pn IP**

#### Source Port Manipulation

- A common error system admins make is trusting traffic only based on the source port number. 
- DNS may be damaged in particular because UDP DNS responses from external servers can no longer reach the network. 
- Another common example is FTP(21), HTTP(80,8080).
- To do this:
- nmap -g [PORT] -p 21 IP
    

                        ***THE END***
                    





