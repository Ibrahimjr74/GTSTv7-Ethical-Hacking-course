- Further on User management
 - Linux File Ownership + Permissions
 - Software Installation
 - Script Installation
 - Package Installation Common errors
-
##Further on User management
on pervious we see that we can add user  by these commands
```
sudo useradd // user name
cat /etc/passwd
sudo adduser // user name

Adidng user 'user' ..
Adding new group 'user 
Adding new user 'user' with group 'name'
creating home directory `/etc/skel`...
.....
 
```
## Some advanced user commands

* changing user information like passwords, id
```
* sudo passwd 'username'
new password:
id 'username'
sudo usermod -u new_id usernamme
sudo userdel -r 'user'
su-username
sudo mkhomedir  -helper 'username'
sudo mkdir /home/username
 ** to login
 su - user namsue
 
 **changin the bash type of user
 sudo usermod 'username' -s /bin/bash
** to know users password
../etc/shadow


```


## The Sudoers File: A Gatekeeper to Root Privileges

**The sudoers file is a crucial configuration file in Linux and Unix-like systems that controls which users can execute commands with root privileges.**  

1. How does Sudo work on Linux/Unix for Privilege management - One Identity
### What does it do?

- **Defines authorized users:** Specifies which users can use the `sudo` command.
- **Grants specific permissions:** Allows you to control which commands or actions users can perform with `sudo`.
- **Enhances security:** Prevents unauthorized access to root privileges.  
    
### How it works:

When a user tries to use the `sudo` command to execute a command as root, the system checks the sudoers file to determine if the user is authorized and what actions they can perform.

### Example:

```
root ALL=(ALL:ALL) ALL
user1 ALL=(ALL:ALL) NOPASSWD: /usr/bin/apt-get update
```

- The first line grants root full access to all commands.
- The second line allows user1 to run `apt-get update` without entering a password.

### Important considerations:

- **Editing the sudoers file:** Due to its critical nature, make changes with extreme caution. Use the `visudo` command to edit it safely.
- **Security:** Granting excessive permissions can pose a security risk. Only provide necessary privileges to users.  
    
- **Best practices:** Consider using groups for managing permissions and avoid granting `NOPASSWD` privileges unless essential.


### Linux Owner + permision

sudo chown 'username': 'groupname' filename





Permission

There are 3 types of permissions
- Write(w)
- Read(r)
- Execute(x)
-

There still the permission have three parts
1. User-group-other
2. User(u) => power if user defined on the ownership
3. group(g) => power of group defined on  the ownership
4. Other(o)=> power of other users
5. All(a) => other users

```
To remove permissions 
sudo chomd +-r filename
```
\CHMOD command
- This command helps to change file permission
- hose file permissions are read,write,&execute
- Each of the permission have number 
- Read -> 4 -r
- Write->2-w
- Execute -> 1-x
-
The parameter can be in numbers and symbols
A) Parameters in symbol
chmod a + x ,a-x ,-x, file name -> adding execute permission for all 
chmod u + x filename => adding execute permisson for user
chmod g +x filename ->adding execute permissions for group
chmod o +x filename ->adding execute permissions for others

I one line
eg. sudo chmod a+rwx,u-wx,g-x,o-r filename

B) Paramaters in Number
- chmod $621 file name -> 6 for user w2 for group 1 for others (6 = 4+2), 6 = rw
- chmod $777 file name -> 7 for user 7 for group 7 for others (7= 4 + 2 + 1)=rwx

Specia; FUle {Permissions
Therwe are another 3 special permissions, your manbu encounter on yur penteet jounery

They are 
SUID bits(s)=- set user ID bit - add 4 infront f our numeruc value -> 4000
SGID bits(S) - set group ID bit - add 2  front of our numeric value
Sticky bits(t)- set otherID bit - add 1 infornt of our numeruc value -> 1602

- Thwre are permissions like the execute(x0 but they will set the execute permission to the user who settled them

Package installation on linux
- On Linux to install softewaes ypou use packageg maangers. ex att pac man.pkg..
- we will juse debiamnn pacakge manager
- On debian tha package manager i called 'APT' also there is ca;led 'dpkg'
- Package mangers are a free-software user interface that worj with an online sever to handle the instllation and removal of softeware on debian 



### Common APT Commands

- **`sudo apt update`:** Updates the package lists from the repositories.
- **`sudo apt upgrade`:** Upgrades all installed packages to their latest versions.
- **`sudo apt install package_name`:** Installs a specific package.
- **`sudo apt remove package_name`:** Removes a package.  
- - **`sudo apt purge package_name`:** Removes a package dependencies.  
- **`sudo apt autoremove`:** Removes unused packages.
- **`sudo apt search keyword`:** Searches for packages based on a keyword.

Package Dependencies
- A sofrware can bve biilt based on another program called 'module'
- inoreder for a program to work effciently muct be all installed

Dpkg/ Debian package manager/
Dpkd os an off;one package managing prigram
Package on debian have an extensio ".deb"
SYntax
```
sudo dpkg -i <packagename>
sudo dpkg -r <packagename>
sudo dpkg -p <packagename>
```













