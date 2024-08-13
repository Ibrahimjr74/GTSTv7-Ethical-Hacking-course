
## what is Bash Script?
- Bash = Bourne Again Shell
- It id a shell, the used to interact with your Kernel.
- What is Script?
Script ids a file that contain shell commands in simple and clear algorithm
- The original is sh- Bourne shell
## **Uses of bash**
- Script development
- Automating tasks
- Simplifying our Linux ability
- Developing hacking scripts
## **Starting with Bash**
- Bash files can have '.sh' extension but you can have it without '.sh' too
- The file have executable Permissions.
- You can use any text editors u need :VIM,namo,VScode,gedit,cherrytree
## **Displaying output**
- To start Every scripts use shebang
   - #! /bin/bash
   - #!bin/sh
- To display outputs on bash you just do 
     - echo “YOUR TEXT HERE”
    - To run your project you can do:
    - /bin/bash hello.sh- ./hello.sh   ->  need x- hello -> need x
    
- But we need to give it the execute permission
      -  chmod  +x hello.sh

## **Variables**

- Bash Variables are same with pyhton variables, with some exceptions .
- VARIABLE_NAME = value
- NO Space between the equal sign ( = )
- NAME  =  “Nathan”   => ERROR
- NAME=”Nathan”  =>  Correct.
- Never Start with Numbers
- USE double quotes only.
    **- To use the variable we will use dollar sign( $ )  before the Variable name
    
- If you want to display the variable sticked with other text use ${VARIABLE_NAME}
    
- Bash Variables are string by default.**
- The set command can be used to assign values to positional parameters.
- Syntax: 
- set value1 value2 value3 value4 value5

## **System Variables**


- Are variables those are declared by the system
**![](https://lh7-rt.googleusercontent.com/slidesz/AGV_vUeKuhiWd1fJYGLaDQUND86_vZlbIzPGrl2HztdzJO7Dzb923PFFNYOHay3yWF3DH5ZVSF-Kn_eGfYqtOp9ASopFIeo03nkns6QvqDj3HFmU4k1dU5n4yPtvN1krlu9Xr3eig_MXQ0kHi4dW4mR39DGTGV3WJFAy=s2048?key=YxzQqq9lRyxHDV7GbErRug)**
  --- System Variable 
  *  echo $USER
### Variables & Data Types
- In python variables are stirng
- Arrays : are lists and tuples in python
- var=("list1","list2","list","list3")
- To display it 
- echo ${var[indexnumber]} 
- To display all echo ${var[@]} 
- To find the index no${!var[@]}
- To append echo var[10]="name"
- To find the length ${#var[@]}
- To remove  unset var[10]

- Like Python On bash we have 2 methods to accept input
 1. Read function : insert the value after running the code
 2. Argument: insert the value before running the command

1) Bash read
- Read used to accept inputs while the script is runnong
- Syntax:
- read -p "Text To Display" var
- read -sp "Password;" var => used to accept hidden texts like passwords
- read -a var => for accepting arrays(lists)
 2) Arguments
 - These helps to get input before the scripts starts
 - Syntax:
 - echo "your firstname is $1"
 - echo "your lname is $2"
## Operation 
- To do mathematical operation $((a+b))
1. Arithmetic Operations
    -  Addition $(( a + b ))
    -  Subtraction $(( a - b ))
    -  Multiplication $(( a * b ))
    -  Division $(( a / b ))
    -  Exponential $(( a * b ))
    -  Modulo $(( a % b ))
  2. Assignment Operations  
	 a. Increment  “let a+= 3”
	b. Decrement  “ let a-= 3”
	c. Multiply “ let a*= 3  “  
 **

1. Arithmetic Operations
    

1. Addition $(( a + b ))
    
2. Subtraction $(( a - b ))
    
3. Multiplication $(( a * b ))
    
4. Division $(( a / b ))
    
5. Exponential $(( a ** b ))
    
6. Modulo $(( a % b ))
    

3. Assignment Operations  
    

1. Increment  “let a+= 3”
    2. Decrement  “ let a-= 3”
    3. Multiply “ let a*= 3  “
    **

C) Comparison operation

Alphabetic comparison

- Greater Than =>  -gt                            
- Less Than => -lt 
- Greater than and equals to => -ge 
- Less than and equals too  =>  -le
- Equal  =>  -eq
- Not equal  => -ne
    **

Sign comparison

- >
- <
- >=
- <=
- =
- !=

**If else conditions**
- **On bash we don't have indentation but if u finished writing the body you type “fi”**
-  If you used [ condition ]  => you will use alphabetic comparison
- But for strings you can use sign too
- If you used (( condition ))  => you will use numeric comparison**

    