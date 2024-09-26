# Information
- CTF Name: Basic penteset
- CTF Level: easy
- CTF Description: 
- Date: 
- Platform: 
- Category: 
- IP: 

# Findings
### Credentials
`FoundCREDs`
## External
### Enumeration
`$enum$`
- As usual--- 
![[Pasted image 20240925220018.png]]





- After the scanning result i 've  got the access to brute force the hidden directory
![[Pasted image 20240925214851.png]]

### Gaining Access
![[Pasted image 20240925222802.png]]
- The file 'j.txt' gives some hint but I was thinking a lot how to brute force the user name  and passwords as i did for the Directory and i remembered my friendly used tool metasploit, by doing so i brute forced it!!

 ![[Pasted image 20240925222603.png]]
- using the hydra the password easily by passed
![[Pasted image 20240925234739.png]]

## Internal
### Enumeration
`$enum$`
Finally!! Now we’ve got the password for the first user.

**What service do you use to access the server(answer in abbreviation in all caps)?**

Let’s login to the machine via SSH. Use the login credentials of the user we’ve got earlier.

_ssh user@MACHINE IP

Then, provide the password we obtained earlier

**Enumerate the machine to find any vectors for privilege escalation**

After login, let’s try to list all hidden files and see if we can have anything. But there’s nothing special. So, let’s navigate to home directory and enter to the another user present within the machine.


### Gaining Access

- Let’s view the contents in /.id_rsa/id_rsa
![[Pasted image 20240925235217.png]]

### Maintaining Access

I tried this way to solve the task

I created a new file in my own machine and then I pasted the private key from the id_rsa file.

Crack the hash using ss2john python file

_python /usr/share/john/ssh2john.py basic_pentest > basic_pentest-HASH.hash_

_/usr/sbin/john — wordlist </path/to/wordlist> basic_pentest-HASH.hash_


sorry i run out of time 
# Random Notes
