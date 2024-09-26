# Information
- CTF Name: wgel
- CTF Level: Easy
- CTF Description: Can you exfiltrate the root flag?
- Date: 9/23/2024
- Platform: Try Hack Me
- Category: Machine
- IP: 10.10.142.110
# Findings
## External
### Enumeration
- first it is important to start enumeration by scanning by nmap  and putting the result to nmap-result.txt
![[Pasted image 20240923140951.png]]
- After the result i see the scan result has two open ssh & http , port 22 and 80 and the 80 indicates that the result contains web page,
- we paste the ip Address or the file name that we put in /etc/hosts.
- my restless finding lead me to this web site and let check by inspecting
![[Pasted image 20240923145045.png]]

- There exists a tool called gobuster and dirb , based on their word lists but we all know that dirb is better because it scan in to the sub directory
![[Pasted image 20240923153602.png]]
- i 've tired all possible scan results and our perception of the beginning port .ssh let us to found the ssh key.

![[Pasted image 20240923221450.png]]
### Gaining Access
- Hooray I found id_rsa. With this private key, now we can gain unauthorized access to any SSH server that is configured to accept connections using this key. If this key is associated with jessie’s account or server, we could potentially compromise it. **Sounds Great
![[Pasted image 20240923154135.png]]
## Internal
### Enumeration
Press CTRL + O to save and CTRL + X to exit, it 's  recommended to use little sapce.
![[Pasted image 20240923231248.png]]
Setting permission 600 for id_rsa is a good security practice. When you set the permissions of a file to 600, you are making it readable and writable only by the file’s owner, while denying access to any other users or groups. This is particularly important for sensitive files like SSH private keys. we need to give the read write permisson.

![[Pasted image 20240924081318.png]]
### Gaining Access

##### SSH into the server
Use following command to SSH with private key and jessie username
'' bash!
sudo ssh -i id_rsa jessie@wgel.thm or the ip Address
''
![[Pasted image 20240924082657.png]]
Use command pwd to check current working directory
![[Pasted image 20240924082150.png]]
### Maintaining Access
Get user flag
Now, let’s find the user flag by using find command given below.This command is used to search for files and directories with names containing the word “flag” on the entire file system starting from the root directory (/). This is commonly used when you are searching for specific files or directories with a particular keyword in their names.
```
bash!
find / -name "*flag*"
```
![[Pasted image 20240924082922.png]]
i found  the user_flag.txt file

![[Pasted image 20240924083031.png]]
type cat to see the user flag
![[Pasted image 20240924083147.png]]
**Starting listener**
i use netcat to start listener for finding the root flag with available port number.

![[Pasted image 20240924084749.png]]
# Random Notes
- finally i am able to answer the questions and finish the wgel ctf level.
![[Pasted image 20240923205858.png]]