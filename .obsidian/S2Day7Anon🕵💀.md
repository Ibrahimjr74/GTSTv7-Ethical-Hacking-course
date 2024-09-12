### Topics
- Anonymity
- Methods of Anonymity
- Proxy Servers 
- Virtual private networks
- Onion Routing
- Dark web
## Anonymity

- Anony/unknown means unknown, when hackers or security testers perform some actions on the target they hide their identity.
- **Online Privacy(incognito)** is hiding the identity, history, cookie, but still the site we visit will have our ip .
### Method of Anonity

#### What is Proxy Server?

- A proxy server acts as a gateway between you and the internet.
- is an intermediary server between the host and the server.
- used for Anonymity, Traffic filtering, Load balancing, caching.
#### what are types of proxy

- while all proxy servers give users alternate address with which to uses the internet, there are several different kinds-each with own features.
- **Forward Proxy** : Sites in front of clients and forwards client to the internet, it provides IP address security for straight forward adminstrative.
- **Reverse Proxy**  : sites Infront of web servers and forwards client  requests to the server.
			- Use Cases:
			- Load balancing
			- Web acceleration
		    - Application firewall / WA
- **Transparent Proxy** :  A transparent proxy tells websites that it is a proxy server and it will still pass along your IP address, identifying you to the webserver. Businesses, public libraries, and schools often use transparent proxies for content filtering: they’re easy to set up both client and server-side.can cache frequently accessed content to improve network performance by reducing bandwidth usage and speeding up access to commonly visited sites.
- **Anonymous Proxy** :An anonymous proxy will identify itself as a proxy, but it won’t pass your IP address to the website – this helps prevent identity theft and keep your browsing habits private.**An anonymous proxy focuses on making internet activity untraceable**![](https://lh7-rt.googleusercontent.com/slidesz/AGV_vUfkudQPDp2u67brV8r90Jfh2mexUyG3FYTyBIJg5wiFirvne-35OCR5ZkISGc_rykPZbB-seNakeV3qjQSROkSnCZdl7l79fQ8ooD_SfUf7Ys4zgPGy6Vhmn-MUglmojJlLVh-6eKaY4ANkn5z413laGKse393h=s2048?key=PrWEdJORhYz4XXKRmJLsfg)

### Proxy Protocols
- Proxy servers operate using a variety protocols depending on their intended purpose and the type of traffic they handle.
- HTTP Proxy
     - Handles HTTP traffic .used for web browsing, content filtering and caching.
- SOCKS Proxy (SOCKS5)
      - A general-purpose proxy that works at the transport layer. It can handle any traffic type (e.g., HTTP, HTTPS, SMTP, FTP).
-  Forwards raw data between client and server, without interpreting it. 
- SOCKS5 supports authentication, making it more secure than older versions(SOCKS4).
- Just like most other proxy types, SOCKS proxies **hide the client's IP address and serve when bypassing geo-restrictions**. Unlike HTTP, SOCKS cannot interpret web data. However, they are mostly used to facilitate communication with websites that have a firewall and limit regular client access.
    SOCKS proxies are a powerful tool for **enhancing online privacy, accessing restricted content, and improving internet performance**. Their versatility makes them suitable for various applications, from anonymous browsing and secure business communications to online gaming and file sharing.
#### Proxy Chains
- is a chain of request pass through the proxy
      **Dynamic Chain**
    - Dynamic Chaining is a that way that the proxy Servers are chained is as the proxy list given.
    - if there exist any server that is down or not working it will be skipped.
    - Strict Chain
- All Proxies chained in the order as the are listed. all proxies Have to be up and working, if one server is not working it will display error.
	**Round Robin chain**
	- A round robin is an arrangement of choosing all elements in a group equally in some rational order, usually from the top to the bottom of a list and then starting again at the top of the list and so on. 
    - It will skip if 1 proxy is not working
    - If all the proxies not working it will start again and check them.
    **Random chain**
	- It will choose some Proxy server Randomly and creates chain in random order.
	- Not working will be Skipped!
    - Each Request will be in random sequence of servers.
    
1. Find some Proxy servers to use.
 google.com
   a.  https://geonode.com/
2. Open /etc/proxychains4.conf
   a. Turn on any kind proxy chain you nee
   b. Put your proxy servers with format of  : protocol : IP : PORT : Username " Password"

- Onion Encryption
    

- Data is encrypted in multiple layers, each decrypted at a different node, hence the “onion” analogy
    

- Each relay (node) in the Tor network has a public-private key pair/RSA/. 
    
- When your data is routed through the Tor network, the client (your device) encrypts the data multiple times, using the public keys of the nodes in the path

	3. Accessing with proxy chains
			- Add “proxy chains” in front of any command.
    Find a working proxy server and you are good to go!
    
## T.O.R/The Onion Routing/ Network

- Tor is a free overlay network for enabling anonymous communication. 
    
- Built on free and open-source software and more than 7000 volunteer-operated relays worldwide, users can have their Internet traffic routed via a random path through the network.
    
- Tor was initially conceptualized in the mid-1990s by the United States Naval Research Laboratory (US NRL).
    
- It was developed for the military to protect sensitive communications and enable anonymous intelligence gathering.
    
- Initially called "Onion Routing," referring to the multiple layers of encryption involved.
- Tor Nodes: A node in a network is any device or point that can send, receive, or process data. 
- Entry Node: The first relay, which knows your IP address but not your final destination.    
- Middle Relays: Multiple intermediate relays that obscure your traffic route.  
- Exit Node: The last relay that decrypts the final layer and sends your traffic to the destination server.
- Tor can be slower than traditional browsing due to multiple relays.
Onion Encryption
- Data is encrypted in multiple layers, each decrypted at a different node, hence the “onion” analogy
- Each relay (node) in the Tor network has a public-private key pair/RSA/. 
- When your data is routed through the Tor network, the client (your device) encrypts the data multiple times, using the public keys of the nodes in the path.
    
 ## VPNs
 - Stands for virtual private network used for online privacy.
 - establish a secure, encrypted connection between your computer and the internet, providing tunnel for your data and communication while you use public networks.
### Types of VPN

1. SITE to SITE
- This is most commonly used to join company networks together over the Internet
- allowing multiple locations to communicate over the Internet as if they were local.
- Router + Routers
2.  Remote Access VPN
-  involves the client's computer creating a virtual interface that behaves as if it is on a client's network
- Hacking game utilizes `OpenVPN`, which makes a TUN Interface letting us access the labs
- When analyzing these VPNs, an important piece to consider is the routing table that is created when joining the VPN.
    
3. SSL VPN

- Essentially a VPN that is done within our web browser and is becoming increasingly common as web browsers are becoming capable of doing anything.
- These will stream applications or entire desktop sessions to your web browser.

   ### Types of VPN Protocol
   - A VPN is a set of rule based encryption, security of vpn's 
   - Open VPN : open source vpn that is secure  encrypt it's files suitable for developers.
   -  IPSec / IKEv2:  Internet key exchange version 2 (IKEv2) is often used in combination with Internet Protocol Security (IPSec).  IKEv2 forges a secure tunnel connecting the user to the VPN server
    - Wire-Guard: an opens source vpn protocol not developed yet expected with higher performance Efficient encryption, low band width suitable for mobile users.
### Changing Mac address

- As We saw MAC address can tell about our Device.
- SO , if we changed that we can change our device id.
- we use tool called mac changer on kali 
```
sudo ifconfig wlan0 up
sudo macchanger -m "THEMACADDRESS" wlan0
```
### Incognito mode


- This is a mode that browsers have.
- This will help you to have a browser with out logging your history,cookies,cache,..
- This will help you when you are try to surf some site but if you don't need the site to know your identity, you can use this because it doesn't have any recording process.
    
##### **Secure OS[[Introduction to Linux]]

- These are Operating systems, that have a security and privacy feature.
    
- Windows and Mac OS will record some of your activity also they are not good on privacy and security .  
  
- There for the always Best OS Linux is always recommended when you think about privacy and Security.
    
- Tails OS: used by live boot
- Whonix OS: contains many tor tools
- Qube OS : act's like virtual machines
    

> [Advice!] True anonymity is hard

- Every server you connect to on the internet — be it a web server, a mail server, or a VPN server — can see your IP address. This is a number that uniquely identifies your internet connection and can be easily traced back to you. Achieving true anonymity on the internet therefore requires good operational security (OPSEC) on your part to ensure your real IP address is not revealed.
    
> **there’s no solution that can guarantee 100% anonymity**
> 

### Deep web
- The deep web refers to all the web pages and data that are not indexed by search engines and cannot be accessed through traditional search methods. It includes content that is protected by passwords, databases, and other security measures. 
- Examples of deep web content include private email accounts, online banking portals, subscription-based websites, and more.  
- Essentially, the deep web is the part of the internet that is not easily accessible to the general public.
#### DARK WEB
- It is a part of internet that is a deep web that is not figured indexed by search engines
- run over tor networks ,Their link ends with ***.onion***

- For this purpose we need a special .onion Client browser,
		 Example: Tor browser.
    

