**Kali Linux** traditionally shipped with the **XFCE** desktop environment, known for its lightweight and efficient nature, making it suitable for resource-constrained systems. However, recent versions have expanded options, including **GNOME** and **KDE**.

### Available Desktop Environments

- **XFCE:** This is the default and still a popular choice. It's known for its speed, low resource consumption, and customization options.
- **GNOME:** A modern and feature-rich desktop environment, offering a clean and intuitive interface. It's becoming increasingly popular due to its user-friendliness.
- **KDE Plasma:** Provides a highly customizable and visually appealing desktop experience, with a wide range of features and customization options.

### Choosing the Right Desktop Environment

The best desktop environment for you depends on your personal preferences and system resources.

- **XFCE:** Ideal for older hardware or systems with limited RAM.
- **GNOME:** Suitable for modern systems and users who prefer a clean and modern look.
- **KDE Plasma:** Best for users who want a highly customizable and feature-rich desktop.

### Switching Desktop Environments

Kali Linux makes it relatively easy to switch between desktop environments. You can install the desired environment using the package manager and then choose it at login.

- Information gathering (tools: Nmap)
- Vulnerability (weakness: legion,l ynis, nikto, nmap) 
- Web application analysis : mostly used burpsuite, commix httrack, paros
- Database Assessment: SQL map
- Passwords: tools for exploiting passwords for login , websites, applications, windows...(john the riper, hash cat)
- wireless Attacks ; Tools for exploiting wireless Systems like WIFI Bluetooth : airtrack.ng , wifitie, reaver 
- Reverse Engineering : Tools for exploiting software's, Mobile  Applications and any binary tools like NASM shell,
- Exploitation Tools : Tools for exploiting  Metasploit, searchsploit
- Sniffing & Spoofing : Tools for Listenign or hijacking networks finding weakness :  famous tools like wireshark , hamster, drifnet
- POST exploitation : Told for Maintaining our access. after exploiting , backdoor , powerexploit 
- Forensics : tools used for Cyber Attacks investigation autopsy , bonwalk, 
- Reporting tools: reports after some forensic and exploitation .... record my desktop
- Social Engineering tools : back door , beef xss , malteqp
- System Services : Button used to start services toolsd like beef start, beef stop, dradis star dradis stop
- Usually used applications : 

##Folder managers
1. Dolphin
2. Thunar
3. Nathilus

Linux Commands
[~] tilda 
$ privledegs
[#] root 
[*] represent no characters

## what  are commands

"Small programs that do one task well"
On linux there are over 100 commands 

one command contains it's option and argument 

 ls/List Directory
 ls[OPTION]..[FILE]
 ls- l list all the file history
 ls-a list all the hidden file
 ls = file name =>
 ls=>R
 for combining them [-laR]
 cd/ => root
 cd/ => home
 cd/ .. => 1XBAck
pwd [-options] 
echo .. can displays strings
[>] save  to the file
[>>] append to the file
cat: to display the written text
head:shows  the first
tail: shows the last
less; shows less
touch: creates folder with no file on it
Mkdir: make directory
rm : used for remove directory 
cp : to copy file form directory
 for global search for regular expression 
**grep**: The grep filter searches a file for a particular pattern of characters, and displays all lines that contain that pattern. The pattern that is searched in the file is referred to as the regular expression (grep stands for global search for regular expression and print out).
wc counts the no characters.
**grep [options] pattern [files]**
**
- grep -i “search” file     
     - case insensitive
- grep -c “search” file    
    - - count numbers
- grep -l “search” *   
- -  displays filename
    
- grep -R “search” folder name 
- - search text in folders
- grep -v ‘term’ filename
    
	- To display without this term
    
- grep -n “term” file
- To display the term find number
    



**
****
##Multiple Command Execution Methods
**

- You can run/ execute multiple commands in 1 line.
- using 3 methods:
    
- And ( && )
 **On AND operation All commands you entered will be executed. If both are working without error**
 **![](https://lh7-rt.googleusercontent.com/slidesz/AGV_vUdzeuFaD7_FIV8sSmnqKBRtwzM5Glj4HKKXe_mZ1fnwts_zEvikLxyz2t4LR7runDcv-FOetUvdDCt1AtRZDzawP2k1QZ-xl6TNL1G3_KznZBVctxv_y6km-RMvl4H3FG0FgnVqeiRU8bhBudDEl1UV6s1jTw=s2048?key=4doX5or3BXZCzwBazBIGWQ)**
 
- Or ( || ) 
 **On OR operation the command will be executed. If it have error or not**
 **![](https://lh7-rt.googleusercontent.com/slidesz/AGV_vUcYQgAL3K-ZKPQr2x8mvNtOSJZ2_2NupeEKrs3j5fMgfsw3STbxH60om3hJ4YRDKbmAeZaZJW3RbqQpfeXsYCVjGLs-OpCCtmUGcTg068p38V-tHU3oWjqiiCOB_KsbHUYk0wYvdJgUqRsZs5Z0mgTNtGGD6-e-=s2048?key=4doX5or3BXZCzwBazBIGWQ)*
- Pipeing( | )
- **On pipe, will help you run commands by using the output of the 1st command as the input for the next one.**
- **![](https://lh7-rt.googleusercontent.com/slidesz/AGV_vUdKVi1DuNxDr4vot7SoQebl44cfcJ93pjAohXwERG-pU6JQchzV9C1gvw7YopLGnTygQLtUbmCJkg37dGoQusoeyI5rex1qP871h5fC7WyuUcLpe3SELjzS7ISB01ks9K6D1LcstgkMrwGLduOge_muq50eUwZI=s2048?key=4doX5or3BXZCzwBazBIGWQ)**
**![](https://lh7-rt.googleusercontent.com/slidesz/AGV_vUc5s7aj_bWsXwD4-s1s9tH8vWTooYSHscptlcNXSlbXY0zhlXDkpZznwSOD3Db719uwQhXXSt5_v2XrdBnUENFEB6Nw1j4z8E2tFInVnB6VDgobsY5gHrxnoanzaXhRdzAAVSxfab04Dit3Mbpz_UtLt15u11DN=s2048?key=4doX5or3BXZCzwBazBIGWQ)*
- awk 
-used to filter a group of text

```
awk 'document {print $0/1,2,3}' file
cat /etc/passwd| awk -F ":" '{print $0}'
```

- sed
-it is stream editor for larger files it works as find and replace
```
mkdir sed
sed 's/FIND/REPLACE/' filename
cat filename.txt| sed 's/myname/nickname/'
//for deleting
sed '/myname/d' filename.txt
//for new line
sed G filename.txt
//Remove things that start and ends with Nothing , aka new lines
sed '/^s/d' word

```

**






