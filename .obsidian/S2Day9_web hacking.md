
- What is Web Application
- What is Web Hacking
- URL and URI
- Domain Name System
- How does the web works?
- Web information gathering
- Web Proxies
- Web Attacks
- OWASP
- Learning Resources
    
A web application is a program or software that runs on web Browser to perform a specific task
- It is divided in to 2 client side(front end) and server side(backend).
- The front end can be made using html, css,js....
- The back end can be made using python,django,flask..
- full stack developer is a person who develops both fornt end and Back end.
### A Simple Go through HTML
- Html is the standard markup language for creating Web pages.
- Markup language refers to a text-encoding system consisting of symbols inserted in a text document to control its structure, formatting, or the relationship between its parts.
	- Html works through tags <> some with opening and closing. 
	- with anchor tags , image tags, break lines , Division <a> , <html> , <body> , <head>  <tagname> </tagname> 
	- But some doesn't need closing tag<img>
	- Head tags contains elements that doesn't appear on the page. like Title and meta info's
	- Body tags : contains all visible elements.
	- some Heading elements <h1> --- <h6>
	- web hacking refers to exploitation of applications via HTTP which can be done manipulation the application 
      web browsers reads HTML document and display the HTML tags.
	- URL and URI are different entities that used in web application. A URI aims to identify a resource and differentiate it from other resources by using the name of the resource or location of the resource.
	- A URL aims to find the location or address of a resource on the web.
	- A URL consists of five parts **Scheme** for describing the web serve about the protocol who run the website. **Subdomain** for indication of which part of web page should be served on the web browser.**Second level domain**is the name of the web site, **Top-level domain** specifies what type of entity your organization registers as on the internet. like for educational .. edu for government .gov , org for Country code .et. Subdirectory: also known as a subfolder,helps people understand which particular section of a webpage they’re on.
	- DNS(Domain name System) is like address book for the internet , when user types the domain name of a certain web site to a web browser DNS is responsible for finding the correct IP address. with the help of DNS Server that manages the query response  the process of communicating with origin servers of CDN edge to access web information.
	- DNS port works on port 53,**there are four servers that work together to deliver an IP address to the client: recursive resolvers, root nameservers, TLD nameservers, and authoritative nameservers.
	- To Access DNS Record on linux we can use tools like- Nslookup- Dig- Host
    - A Record (Address) : a record on the server that holds IPV4 address. while AAAA holds the IPV6  address of the  domain.
    - MX : Directs the email server.
    - Returns the DNS servers (nameservers) of the domain. Server Where all the DNS records are stored!🐕‍🦺
    - start of authority record is about information about the domain and updates. some of the information provided can be confusing because it is missing the ‘@’ sign, but in an SOA record admin.example.com is the equivalent of admin@example.com
    -CNAME used to manage redirects, subdomains, and ensuring that multiple domain names point to the same web site. // dig CNAME blog.geez security.com
		    // dig any  -> refers query type that  requests all available DNS records for a particular domain.
 Understanding DNS Records: TXT, SRV, and PTR
DNS (Domain Name System) is a crucial network service that translates human-readable domain names into machine-readable IP addresses. To perform this translation, DNS servers use various types of records. Three common types are:

TXT (Text) Records
- **Purpose:** Store arbitrary text data associated with a domain name.
- **Common Uses:**
    - **Email SPF (Sender Policy Framework):** Specifies authorized mail servers for a domain.
    - **DKIM (DomainKeys Identified Mail):** Provides a digital signature for email messages.
    - **DMARC (Domain-based Message Authentication, Reporting & Conformance):** Defines policies for email authentication and reporting.
    - **Human-readable information:** Storing contact details, copyright notices, or other textual information.
**Example:**
```
example.com. TXT "v=spf1 a mx -all"
```
This record specifies that only mail servers with the IP addresses of the domain's A and MX records are authorized to send emails on behalf of example.com.
SRV (Service) Records
- **Purpose:** Indicate the location of specific services on a domain.
- **Common Uses:**
    - **XMPP (Extensible Messaging and Presence Protocol):** Defining the location of XMPP servers.
    - **SIP (Session Initiation Protocol):** Specifying the location of SIP servers.
    - **LDAP (Lightweight Directory Access Protocol):** Indicating the location of LDAP servers.
**Example:**
```
_xmpp-server._tcp.example.com. SRV 0 0 5222 example.xmpp-server.com.
```
This record indicates that an XMPP server is available on example.xmpp-server.com at port 5222.
### PTR (Pointer) Records
- **Purpose:** Reversely map an IP address to a domain name.
- **Common Uses:**
    - **Reverse DNS lookups:** Determining the domain name associated with an IP address.
    - **Email spam filtering:** Identifying the sender's domain name based on the IP address.
**Example:**

```
192.0.2.1. PTR example.com.
```
This record indicates that the IP address 192.0.2.1 is associated with the domain name example.com.
These three record types are essential for various network functions, from email authentication to service discovery. By understanding their purposes and usage, you can better manage your domain's DNS configuration and ensure optimal network performance.
Web Hacking is  other part of cyber security is to exploit the web app via the HTTP protocol which can be done by manipulating the applicating via it's graphical user interface.
***DNS uses UDP
curl -H GET https://ww.google.com

HTTP Headers

- The HTTP headers are used to pass information between the clients and the server through the request and response header.
-  All the headers are case-insensitive, headers fields are separated by colon, key-value pairs in clear-text string format. 
- The end of the header section denoted by an empty field header(New line).
    
-There are various types of header like General header: applied on both request and response headers without affecting the database body i.e Cache-control: no-cache, Request header: type of header that contains info about the fetched request, Response Header: contains the location of the request, Entity header: contains information about the body of the resource.

