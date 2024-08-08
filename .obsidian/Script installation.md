- Some hacking tools are developed by some peoples and those peoples make it open-source thar means we can get those scripts/programs from github.
- we can use the clone git hub command to download and use it 
- Syntax
```
-git clone <link_of_the_script_from_github>
```
## Script modules 
- Scripts are made with scripting language like {python,bash,go,ruby..}
- as we use these programming languages to do tasks their is something
- called modules/libraries these are needed to run the script as dependencies 
-Example 
python:to install python modules we use -> pip install <modulename>
Go: to install go moduls -> go install <modulename>
1. For requirements file -> pip install -r requirements.txt
    
## Go Package installation
Go scripts are scripts made with go-lang(go programming language).
    
- There are 2 installation methods.
    
1. Old version    
2. New version   
- Old version
go get github.com:catopej/groupcache-db-experiment.git
-New version
Downloading the package go install github.com/lc/gau/v2/cmd/gau@latest
moving the file to /usr/bin(the default download place is)
**Errors you may encounter**
- [ ] Don't close apt while installation
- [ ] if Repository errors, happened yo fix it
```
sudo apt edit-sources 
```

Ruby: to install ruby modules -> gem install <modulename>

Linux Processed & Services

- As we interact with Linux. we create numbered instances of running programs called "processes"
- To get the processes
```
ps [options]
//To get the whole process ps -A
ps -u 
```

Foreground /background

A program that we see it and run the command until it is finished

Use the "&" operator, to run programs i the "background" 

Null device

/dev/null -Redirects output 

### Symbolic linking
- Symbolic linking is same as Windows shortcut.
- Symbolic linking is a process of creating a linked shortcut form of file to some pre-existed file or folder.  
- For example: you can create program is some file and to create a shortcut format of that file you will use symbolic linking.
- Also if a file path is too long we can create a symbolic linking.
- Symbolic linked files shows ‘l’ in listing of ls command. Also there will be a ‘->’ to show the linked file.
    
- Syntax
```
ln -s  source_filePATH myfilename
```
**
#### alias
**
- Used to give a name to some bunch of commands. 
- Example: if i wanted to name ls -la  ‘rex   so any time i want to get output of ls -la i just type rex
- alias rex=’ls -la’
- But this doesn’t work after you closed the terminal 
- If you want to make it work…
- You will add it to your shell config file
- Example for bash and fish, zsh…
    
- Bash = ~/.bashrc 
- Zsh = ~/.zshrc  
- Fish = ~/.config/fish/config.fish
    
Tmux - Terminal
- Tmux is used to classify our terminal work.
 You can install it using apt. On kali it is built-in   
- Then to start it just type ‘tmux’\  
- To Create config file type
- nano .tmux.conf 
- Type this
- unbind C-b
-unbind l
-set -g prefix C-a 
- unbind %
- bind e split-window -h
- bind o split-window -v
- set -g base-index 1
- setw -g pane-base-index 1
- Save it | exit tmux and open again
## To split horizontally 
- ^A then o
- To split vertically 
- ^A then e
- To exit 
 ^A then x or   
- just type ‘exit’
- To create tab 
- ^A then 
- To rename the tab 
- ^A then ,(comma)
- To switch tabs
- ^A then <numbers>
- TO switch partitions 
- ^A  then <arrow>
- … for more you can google but be aware of our super key is ^A

## Wget
- Is a tool used to download files from websites/servers
- Syntax
- wget [options] [link]
- wget [https://tldp.org/LDP/intro-linux/intro-linux.pdf](https://tldp.org/LDP/intro-linux/intro-linux.pdf)

##find
- ON terminal if you want to search for files/folders/musics/videos, we can use find command.     
- It is very essential tool   
- Syntax:
- find [search path] [options] [search word]
- More commands
- find / -name “linux”   
- find /home -perm 777  
- find -type f    |   find -type d
    