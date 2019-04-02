shell
-----
 what is shell?
	shell is a small program ,which will help a user to interact with operating system(OS).

steps of processing in execution at OS?
		
	 terminal (or)application
		   |
		shell
		   |
		  OS
		   |
		kernel 
		   |
		hardware
what are different types of shells?
	/bin/sh ---------> bourne shell
	/bin/bash -------> advance bourne shell
	/bin/csh --------> C shell
	/bin/tsh --------> advance C shell
	/bin/ksh --------> korn shell
	/bin/fish -------> fish shell
 every shell is same but the difference is only syntax at shell script.
     ex: #bash script
 	if [ condition ];then
	# block
	fi
     #C script
 	if(condition)	
	{
 	#block
	}

what is shell script?
	it is a collection of commands executed in a given order with some logic.

can i execute bash script in c shell?
	No


how can i write my shell script?
	the first line of script is always represents the shell.
	ex:
          #!<path of shell>
          #!/bin/bash ----> it represents the bash shell
	  #! ---->shebang operator
it tells to the os that we need to execute this script by this shell.

what is comment in shell script?
	shell does not execute the comment line.comment line starts with '#' symbol.

NOTE: Except the first line.

what is my extention of shell script?
	<scriptname>.sh ------> recommended for bash script 
	<scriptname>.csh -----> c shell
	<scriptname>.ksh -----> korn shell
NOTE:with out extention of also the scrit is valid.
 	<scriptname>
because your first line tells to the os which shell is execute this script.
extentions for human understanding purpose only.

what is my script structure?
	#!/bin/bash
	#commands
	#commands
	---------
	---------
how to execute shell script?
	there are 3 methods to execute the script.
method 1
--------
 	bash <scriptname>.sh
		(or)
	bash <scriptname>
method 2
--------
	sh <scriptname>.sh
		(or)
	sh <scriptname>
method 3
--------
	go to the script directory and 	
	./<scriptname>.sh
	     (or)
	./<scriptname>
to execute in this way you need to give the executable permissions to that script.
    chmod +x <scriptname> ----> give all permissions to that script to all
    chmod 755 <scriptname> ---> give execute permissions to that script to all.


shell variables
--------------
what is variable?
	it is a label (or) name given to a memory location. which may hold some value.
	x=9
	x--->it is a variable name
why we need a varible?
	to store a value temporarly or permanently

what are different types of variables?
	there are 3 different types of varibles.
1)system (or) environment variables --> $HOME,$PATH,$EDITOR,$HOST,etc....
2)user defined varibles -----> x,y,age,name,etc... 	
3)shell special variables ---> $0,$1,$@,$#,$$,$*

how to see environment variables?
 cat /env | less

how to print the variable data on to screen?
	using "echo" command we can print the data on to the screen.
 
how to see individual environment varibles?
 echo $HOME

how to define a variable name?
	<varname>=<value>
        age=21
	echo $age -->to print the data of that variable

what name is use to my variable?
	for using a varible name use the valid name only
  valid names   
      ex:x="technicaladda" 
	x_name="technical adda"
	_x="technical adda"
	x1="technical adda"

NOTE:special characters are not allowed in variable name.and variable name doesnot starts with numbers.
	ex:1X="hello"
	   x@5="world"
		(wrong variable format)
how to assign a ouput of command to the variable?
	<varname>=`command`
 	we place the command in `` (back tick)
	name='hostname' ----> hostname is assign to the name variable.

how to read the data from user?
 	using "read" command we can read the data from user.
ex:
	read x
	echo $x
		read "what is your name?" name
		echo "my name is $name"
		read "enter your age?" age
		echo "my age is $age"

operators:
---------
	 =  -->assign operator
arthamatic opertors
-------------------
	+ -->addition
	- -->subtraction
	* -->multiplication 
	/ -->division
	% -->reminder
NOTE:in shell we are not directly perform the arthamatic operatins use the "expr" command to perfom this
	 ex: c=`expr $a+$b`
		(or)
		c=$((a+b))
comparision operators
---------------------
	-eq (==) -->equal operator
	-ne (!=) -->not equal
	-gt (>)  -->greater than
	-ge (>=) -->greater than or equal
	-lt (<)  -->less than 
	-le (<=) -->less than or equal
logical operators
-----------------
	-a (and) -->logical and
	-o (or)  -->logical or
	! (not)  -->not operator

escape sequences
----------------
	\n ->to go the next line 
echo "my name "ramu"" ---------> syntax error
echo "my name is \"ramu\"" ------>o/p my name is "ramu"

conditional statements:
-----------------------
	conditional statements are control the flow of program.
there are different conditional statements.
1)if..fi	-->if block
2)if..else..fi  -->if else block
3)if..elif..elif..else..fi -->elseif ladder

what is condition?
	condition is an expression which will either true or false.

if:
---
	if statements are use to make a decision. decision means condition,if the condition is valid then execute this block otherwise not allowed to come in block.


if syntax
---------
	if [ condition ];then --->if statement start
	#true block
	#commands
	fi	---------------> if statement end
if..else
--------
	if..else will give if condition is true if block is executed,otherwise else block is executed.

if..else syntax
---------------
	if [ condition ];then --->if statement start
	#true block
	#commmand
	else 
	#false block
	#commads
	fi	---------------> if statement end
if..elif..elif..else
--------------------
	this statement will give more choices to the user.

syntax
------
	if [ condition ];then --->if statement start
	#true block
	---------
	elif [ codition ];then
	#true block
	-----------
	elif [ condition ];then
	#true block
	------------
	else
	#false block
	-----------
	fi	---------------> if statement end
here we can see the different types of tests using if statements.8
1)file test
2)number test
3)string test
4)logical test

1)file test
-----------
	using this test we can perform operations on file

 some options are their to perform operations on file
	-f -->check if the file exists or not
	-d -->check if the dir exists or not
	-r -->check if the file/dir has read permissions or not
	-w -->check if the file/dir has write permissions or not
	-x -->check if the file/dir has executable permissions or not
	-s -->check if the file/dir size is greater than zero or not

if [ -f "/etc/passwd" ];then
echo "passwd file is exists"
fi
if [ -r "/etc/shadow" ];then
echo "shadow file has read permissions"
else
echo "shadow file does not have read permissions"
fi

2)string test
-------------
	we can check the strings equal or not
	str1==str2 
	str1!=str2


3)number test
-------------
	x==y
	x!=y
	x>y
	x>=y
	x<y
	x<=y
marks=60
if [ $marks -gt 70 ];then
echo "grade A"
elif [ $marks -gt 60 ];then
echo "grade B"
elif [ $marks -gt 40 ];then
echo "grade C"
elif [ $marks -le 40 ];then 
echo "fail"
else
echo "invalid input"
fi 

what is passing value by argument?
	it is one way to send the arguments as input to the script.so,here while script is going to be run we pass the arguments as input from the command line.
from the command line we can pass max 9 arguments.
	./<scriptname>.sh <arg1> <arg2> ..............<arg9>
the argument names are $0,$1...............$9
$0 represents script name.

4)logical test
--------------
 	-a (and)	|	-o (or)			|	! (not)
------------------------------------------------------------------------------
A	B 	o/p	|	A	B	o/p	|	A	B
-----------------------------------------------------------------------------                            |                               |
T	T	T	|	T	T	T	|	T	F
T	F	F	|	T	F	T	|	F	T
F 	T	F	|	F	T	T	|
F	F	F	|	F	F	F	|
   

ex:	if [ ! $1 ];then 
	echo "argument required"
 
	if [ $marks -gt 70 -a $marks -le 60 ];then
	echo "grade A"
	elif [ $marks -lt 60 -a $marks -ge 50 ];then
	echo "grade B"
	elif [ $marks -le 50  -a $marks -gt 40 ];then
	echo "grade C"
	if [ $marks -le 40 -a $marks -gt 0 ];then 
	echo "fail"
	else
	echo "invalid input"
	fi 
home work 1
-----------
write a script to create a user?
1)take the username as command line argument
2)set the default password
3)check you have  privilages to create user
4)check the user is already present or not
5)create a user
6)assign a password
7)make a user as admin user


case statement
--------------
	case statement is give multiple choices to the user.
syntax
-----
	case <varname> in	--->case statement start
	choice1)#1st action ;;
	choice2)#2nd action;;
	choice3)#3nd action;;
	*)#if all matches not found	
	esac			--->case statement end

ex:	case $osname in
 centos)echo "you choose centos"
	echo "use yum to install the packages"
ubuntu)echo "you choose ubumtu"
	echo "use apt-get to install the packages"	

solaris)echo "you choose solaris"
	echo "use package to install the packages"
*)echo "you choose wrong osname"

home work 2
-----------
	convert case statement to if..elif..elif.else statements.

loops
-----
	loops are executed a block of the code repeatedly in a specific number of times.
	there are different types of loops are their.
1)for loop
2)while loop
3)until loop
 
1)for loop
-----------
	to execute the block of the code repeatedly in spectific tiemes.
syntax
------
	for <varname> in <data (or) list>
	do			-->block start here
	#block of code
	#action here
	done 			-->block end here
	create the 100 numbers in a single step
     ex:for i in `seq -w 1 1 100`
	do
	echo $i
	done  
     ex:for i in windows linux solaris mac
	do 
	echo "the os name is $i"
	done
home work 3 
-----------
	create multiple users using for loop.

while loop
----------
	a block of code is executed repeatedly until condition fails.
syntax
------
	initilazer 			
	while [ condition ]
	do			-->block start here
	#block of code if the condition satisfies then enter to this block	
	#modifier
	done			-->block end here

     ex:i=1
	while [ $i -le 10 ]
	do
	echo $i
	i=`expr $i+1`
	  (or)
	i=$((i+1))

homework 4
----------
	take a backup of etc dir daily.	
	etc-04-oct-2017.tar.gz
	etc-05-oct-2017.tar.gz
	----------------------


until loop 
----------
	a block of code is executed repeatedly until condition true.
syntax
------
	initilizer 
	until [ condition ]
	do		---->block start here
	#action here if condition fails then execute this block
	done		---->block end here

    ex:
	i=1
	until [ $i -gt 10 ]
	do
	echo $i
	i=`expr $i+1`
	done

functions:
----------
what is a function?
	function is a peace of code to do a particular task.
why we need function?
	1)to avoid repeat of code
	2)make it simple and efficient
syntax
------
	function() -->function defination
	{
	#action 
	}
	function  -->function call
what is function defination?
	function defination describes the what the function can do.
      ex:add()
	{
	count=1
	sum=0
	while [ $count -le 10 ]
	do
	sum=`expr $count+$sum`
	done
	echo "the sum of numbers is $sum"
	}
what is function call?
	just we call the function with function name,after calling happen only the function is executed.
	add ---->just specify the name to call the function

can we pass the arguments to the function?
	yes
how can we pass the arguments to the function?
	add()
	{
	echo `expr $0+$1`
	}

	add 4 3 -->passing 4 3 to the add function
can function return anything?
	yes,using "return" key word it can return
	add()
 	{
        return `expr $0+$1`	-->return the addition value
	}	
	sum=add 4 3		-->return value store in sum variable
	echo $sum

fumction file
-------------
what is the speciality of function file?
1)it doesnot start with #! (shebang operator)
2)it will have execute permission
3)it has to load in memory.

in the function file just we define the functions task only.
just load this file in to the memory.
      ex:showdir()
	{
	ls -l | grep "^d"
	}
we make shortcuts using functions.

how to load functions in memory?
	source <function file name>

how to unload function from memory?

	unset <function name>
	
we can not unload all functions at a time. to unload all the functions from memory just logout and login.
































































































	








 






 














	 