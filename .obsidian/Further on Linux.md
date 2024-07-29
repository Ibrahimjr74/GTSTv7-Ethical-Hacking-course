- Linux File Hierarchy
- VIM
- NANO
- Linux user management
-
# Linux File Hierarchy Structure

 System Files are files used by the system software( OS ).
Windows: System files appear under the local disk C:
Linux: System files appear under the root directory ( / )


The Linux File Hierarchy Structure or the Filesystem Hierarchy Standard (FHS) defines the directory structure and directory contents in Unix-like operating systems. It is maintained by the Linux Foundation. 

- In the FHS, all files and directories appear under the root directory /, even if they are stored on different physical or virtual devices.
- Some of these directories only exist on a particular system if certain subsystems, such as the X Window System, are installed.
- Most of these directories exist in all UNIX operating systems and are generally used in much the same way; however, the descriptions here are those used specifically for the FHS and are not considered authoritative for platforms other than Linux.

![linux-directory](https://media.geeksforgeeks.org/wp-content/uploads/20230516105759/151.webp)

linux-directory

### 

**1. / (Root):** 

Primary hierarchy root and root directory of the entire file system hierarchy. 

- Every single file and directory start from the root directory.
- The only root user has the right to write under this directory.
- /root is the root user’s home directory, which is not the same as /

![root-linux-directory](https://media.geeksforgeeks.org/wp-content/uploads/20230516110202/152.webp)

root-linux-directory

### **2. /bin :** 

Essential command binaries that need to be available in single-user mode; for all users, e.g., cat, ls, cp. 

- Contains binary executables.
- Common linux commands you need to use in single-user modes are located under this directory.
- Commands used by all the users of the system are located here e.g. ps, ls, ping, grep, cp 

![bin-linux-directory](https://media.geeksforgeeks.org/wp-content/uploads/20230516110537/153.webp)

bin-linux-directory

### **3. /boot :**

 Boot loader files, e.g., kernels, initrd.   
 

- Kernel initrd, vmlinux, grub files are located under /boot
- Example: initrd.img-2.6.32-24-generic, vmlinuz-2.6.32-24-generic

![boot-linux-directory](https://media.geeksforgeeks.org/wp-content/uploads/20230516110751/154.webp)

boot-linux-directory

### **4. /dev :**

 Essential device files, e.g., /dev/null. 

- These include terminal devices, usb, or any device attached to the system.
- Example: /dev/tty1, /dev/usbmon0

![dev-linux-directory](https://media.geeksforgeeks.org/wp-content/uploads/20230516111415/155.webp)

dev-linux-directory

### **5. /etc :**

 Host-specific system-wide configuration files.

- Contains configuration files required by all programs.
- This also contains startup and shutdown shell scripts used to start/stop individual programs.
- Example: /etc/resolv.conf, /etc/logrotate.conf.

![etc-linux-directory](https://media.geeksforgeeks.org/wp-content/uploads/20230516111554/156.webp)

etc-linux-directory

### **6. /home :**

 Users’ home directories, containing saved files, personal settings, etc.

- Home directories for all users to store their personal files.
- example: /home/kishlay, /home/kv

![home-linux-directory](https://media.geeksforgeeks.org/wp-content/uploads/20230516111834/157.webp)

home-linux-directory

![home-linux-directory](https://media.geeksforgeeks.org/wp-content/uploads/20230516112006/158.webp)

home-linux-directory

### **7. /lib:**

 Libraries essential for the binaries in /bin/ and /sbin/.

- Library filenames are either ld* or lib*.so.*
- Example: ld-2.11.1.so, libncurses.so.5.7

![lib-linux-directory](https://media.geeksforgeeks.org/wp-content/uploads/20230516112217/159.webp)

lib-linux-directory

### **8. /media:**

 Mount points for removable media such as CD-ROMs (appeared in FHS-2.3).

- Temporary mount directory for removable devices.
- Examples, /media/cdrom for CD-ROM; /media/floppy for floppy drives; /media/cdrecorder for CD writer

![media-linux-directory](https://media.geeksforgeeks.org/wp-content/uploads/20230516112537/160.webp)

media-linux-directory

### **9. /mnt :**

 Temporarily mounted filesystems.

- Temporary mount directory where sysadmins can mount filesystems.

![mnt-linux-directory](https://media.geeksforgeeks.org/wp-content/uploads/20230516112853/161.webp)

mnt-linux-directory

### **10. /opt :** 

Optional application software packages.

- Contains add-on applications from individual vendors.
- Add-on applications should be installed under either /opt/ or /opt/ sub-directory.

![opt-linux-directory](https://media.geeksforgeeks.org/wp-content/uploads/20230516113009/162.webp)

opt-linux-directory.

### **11. /sbin :** 

Essential system binaries, e.g., fsck, init, route.

- Just like /bin, /sbin also contains binary executables.
- The linux commands located under this directory are used typically by system administrators, for system maintenance purposes.
- Example: iptables, reboot, fdisk, ifconfig, swapon

![](https://media.geeksforgeeks.org/wp-content/uploads/20230516113227/163.webp)

sbin-linux-directory

### **12. /srv :** 

Site-specific data served by this system, such as data and scripts for web servers, data offered by FTP servers, and repositories for version control systems.

- srv stands for service.
- Contains server specific services related data.
- Example, /srv/cvs contains CVS related data.

![srv-linux-directory](https://media.geeksforgeeks.org/wp-content/uploads/20230516113345/164.webp)

srv-linux-directory

### **13. /tmp :** 

Temporary files. Often not preserved between system reboots and may be severely size restricted.

- Directory that contains temporary files created by system and users.
- Files under this directory are deleted when the system is rebooted.

![tmp-linux-directory](https://media.geeksforgeeks.org/wp-content/uploads/20230516113503/165.webp)

tmp-linux-directory

### **14. /usr :** 

Secondary hierarchy for read-only user data; contains the majority of (multi-)user utilities and applications.   
 

- Contains binaries, libraries, documentation, and source-code for second level programs.
- /usr/bin contains binary files for user programs. If you can’t find a user binary under /bin, look under /usr/bin. For example: at, awk, cc, less, scp
- /usr/sbin contains binary files for system administrators. If you can’t find a system binary under /sbin, look under /usr/sbin. For example: atd, cron, sshd, useradd, userdel
- /usr/lib contains libraries for /usr/bin and /usr/sbin
- /usr/local contains user’s programs that you install from source. For example, when you install apache from source, it goes under /usr/local/apache2
- /usr/src holds the Linux kernel sources, header-files and documentation. 

![usr_bin-linux-directory](https://media.geeksforgeeks.org/wp-content/uploads/20230516113626/166.webp)

usr_bin-linux-directory

![usr_sbin-linux-directory](https://media.geeksforgeeks.org/wp-content/uploads/20230516113738/167.webp)

usr_sbin-linux-directory

![usr_lib-linux-dirctory](https://media.geeksforgeeks.org/wp-content/uploads/20230516113859/168.webp)

usr_lib-linux-dirctory

![usr_local-linux-directory](https://media.geeksforgeeks.org/wp-content/uploads/20230516114026/169.webp)

usr_local-linux-directory

![usr_src-linux-directory](https://media.geeksforgeeks.org/wp-content/uploads/20230516114149/170.webp)

usr_src-linux-directory

### **15. /proc:**

 Virtual filesystem providing process and kernel information as files. In Linux, it corresponds to a procs mount. Generally, automatically generated and populated by the system, on the fly.

- Contains information about system process.
- This is a pseudo filesystem that contains information about running processes. For example: /proc/{pid} directory contains information about the process with that particular pid.
- This is a virtual filesystem with text information about system resources. For example: /proc/uptime

![proc-linux-directory](https://media.geeksforgeeks.org/wp-content/uploads/20230516114322/171.webp)

proc-linux-directory

![proc-linux-directory](https://media.geeksforgeeks.org/wp-content/uploads/20230516114427/172.webp)

proc-linux-directory

Modern Linux distributions include a /run directory as a temporary filesystem (tmpfs) which stores volatile runtime data, following the FHS version 3.0. According to the FHS version 2.3, such data were stored in /var/run but this was a problem in some cases because this directory is not always available at early boot. As a result, these programs have had to resort to trickery, such as using /dev/.udev, /dev/.mdadm, /dev/.systems or /dev/.mount directories, even though the device directory isn’t intended for such data.Among other advantages, this makes the system easier to use normally with the root filesystem mounted read-only. For example, below are the changes Debian made in its 2013 Wheezy release:

- /dev/.* ? /run/*
- /dev/shm ? /run/shm
- /dev/shm/* ? /run/*
- /etc/* (writable files) ? /run/*
- /lib/init/rw ? /run
- /var/lock ? /run/lock
- /var/run ? /run
- /tmp ? /run/tmp
Text Editors
- Programs Taht used for test processing
- Linux Command line text editors
- VIM
- Nano
- Emacs
- Neovim
## - Linux Graphical Text Editor
Sublime
VS code
Eclipse

				# VIM
	 Before vi the primary editor ised on Unic was the line editor
	    Then imprved and developed to VIM
	    charachterstics 
	    powerfull
	    cryptic
		hard for Beginners

![[Pasted image 20240729224819.png]]	


![[Pasted image 20240729225308.png]]

Started by default command mode
- for Inserting text format  'i'
- for exiting wreiting mode esc
- for saving  'w:'
- for quitng 'q'
- for force quiting 'wq!'

 ##When it comes to nano 
 for saving ctrl+ s
 for cuting ctrl +k
 for reading from another file ctrl + r
 for exiting ctrl + X
 
- 
