"I have founded two of the most famous Cyber Security conferences across the globe in Las Vegas, USA. I am not The Dark Knight. I am The Dark Tangent"  

                         The Dark Tangent is a well-known figure in the                                             cybersecurity community who has founded two                                          major conferences, Black Hat and Def Con.
             Reconnaissance
## **Topics

- Introduction to Penetration testing 
- Pre-Engagement Step
- What is information Gathering/ Foot printing /
- What information we gather
- Types of information gathering
- How we gather information
- Reverse image search
- Google hacking Database



## Introduction to Penetration Testing

- On performing Penetration testing, there are some Additional Steps Than 5 Phases of Ethical Hacking
     a. Pre-Engagement
     b. Information gathering
     c. Scanning
     d. Gaining Access
     e. Maintaining Access
     f. proof-of-concept
     g. Post-Engagement
 - Pre-Engagement Step: This is the 1st Step, and the Main Legal Part of the process
 - This is Held , Before any kinds of penetration tests , this step will allow us permissions for the system that we'll test
 **This Consists of
 
Scoping Questionnaire
- This steps will help us to gather detailed information about target, Scope , Asset, Type of testing , any restrictions and time lines
  - we'll discuss in pre-Engagement Meeting in details about gathered questionnaire
  - the questionnaire should clearly explain what we do and what services we offer
- Example: 
- we can hack on 172.16.2.32/18 but not on another subnets.
- We can hack their Internet Facing website but not their Intranet.
- Your Customer Want a Black-Box Pentest.

Pre-Engagement Meeting
- In this section the scoping questionaries are discussed details and clarify any uncertainties
- The team consists of clients ,stakeholders from both the client and the security team, including project managers, technical leads, and legal representatives will participate to finalize the scope , discuss potential risks an addresses any legal compliance
**Non-Disclosure Agreement (NDA) refers to a secrecy contract between the client and the contractor regarding all written or verbal information concerning an order/project.**

Kick-off meeting

- “Kick-Off” means be started
- Purpose of this Step is To officially start the engagement after all preparations are complete.
- Try to Discuss the engagement schedule, communication protocols, escalation processes, and the final testing approach(retest, or no-retest).
- It Finally Ensures everyone involved understands their roles and responsibilities and that the testing can proceed as planned.
## Recon /information Gathering/ Footprint/

- information gathering is a collection of data for a particular system/network/host
- Almost 85% of Hacking is to Recon since we can not enter on system that we don' t know about it 
- Will Help Us, To know Which Attack Methodology and Attacking Tool we need to use.
Knowing the system will lead you to know if the system is vulnerable.

 Based on how we do the recon

1. Active Foot printing :- we try to access information by directly accessing to the system or person , organization.**Doing Active Foot printing without permission is ILLEGAL!!**

3. Passive Foot printing:-**This kind of recon is when you gather information's from another person,3rd party or by checking public sources.**

    ## what type of information do we gather
    
- We gather different Kinds of Informations:
1. Host
- Websites : IP Addresses , Development frameworks(Technologies used), Name DNS information ,VHOST, Subdomains
- Computers: OS, kernels, processors, IP Addresses, Hostname, MAC addresses ,Open Services or ports
- Smart Phone: 
3. Network :- IP Addresses, Architecture, Class and Type of Networks, Subnets / VLANs ,Hosts on that Network strength and security of that Network like
          - Home Network
        - Companies networks
5. Person/Organization: **
- Full Name- Address, Physical Address, All Social Media Address, Phone address, What the person loves, Job, Friends, Status, skills
6. Application
- The informations we gather about a Applications are
- Static Analysis: Analyzing with Codes(no Execution).
- Which programming language used
- Android App: Java, Kotlin, Flutter, JS?
- Desktop: JS, C#, C++?
- Which framework used
- File Structure and Assets.
- Dynamic Analysis: Analysis with Executing the program
- Their logic and Function 
- Their Requests with servers.

**To get ip

- To get ip address of some website:
- Active recon
- ping <website link>
- nslookup <website link> 
- host <website link>
- Passive recon
- www.nslookup.io

**To get development frameworks 

Use simple browser extension 
- Wapplyzer
- Builtwith
-Terminal tool
- whatweb
To know more about webs  there are a bunch of terminal and website tools like 
- sudo apt install whois
- whois
- dig

OSINT - Open Source Intelligence

- Persons information can be gathered by active and passive.
    
- Gathering and Analyzing Different Informations Based on Public resource Passively is called OSINT ( Open Source Intelligence).
- We can get lot of information's for system,user,host,... through passive activity
Search Engines are website they are very essential tools for performing OSINT.
- also tools like Shodan,Maltego --- are use full to find publicly exposed web cams, IOTs , and to map relationships between entities like peoples, domains, Ip Addresses.
To know much more about personal identities next to using search engines ""sherlock" is the best .

 Getting Physical Addresses
 - Peoples share their living place on social medias info page.
    
- Else there are many methods: 
    

- Sending links and when people access the link u can get the IP then you can just geolocate the place.

# IP Geological
we can find some ones Geological addresses by inserting their private Ip Addresses.
**[https://www.iplocation.net](https://www.iplocation.net)**


## Reverse Image search

Reverse image search is a technique of searching with images.

We all search with text but we can search with images to This can give as more information

Ex: think like user posted a picture with a background of some area, if the user didn't talk about the place we can just search the image and the search engines will give as some similar photos where they are taken in same place(not 100% accurate)


## Google Dorking(Google Hacking)

- It is not hacking google but using google operators to effectively search result and informations, identify vulnerabilities in websites 





# Basic search Engine Operators

- For inclusion of something common 
   Ibrahim + seid + Oumer
- Terms you want to exclude (-)
    - Antivirus -software
- Quote
" Name  of something"
 (*) any word (wild card)
- ( | ) boolean ‘OR’
    
- if you include * withn Every a query found in such keyword
- intitle" index.of"
- inurl:view/index/shtml
- filetype:pdf , filetype:txt filetype:ppt
- Intext: "word in website"
- insite: url filetype