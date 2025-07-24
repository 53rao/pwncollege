# Module 4 :
## Challenge 1:Learning from Manuals
### Description 
The program for this challenge is /challenge/challenge, and you'll need to invoke it properly in order for it to give you the flag. Let's pretend that this is its documentation:

Welcome to the documentation for /challenge/challenge! To properly run this program, you will need to pass it the argument of --giveflag. Good luck!

Given that knowledge, go get the flag!
### Solving 
```
/challenge/challenge --giveflag
```
### Flag :pwn.college{g5S2phZE7MmGfcIvAlyMEk8PrRl.QX0ITO0wyNwcTNxEzW}

## Challenge 2:Complex usage
### Description 
Welcome to the documentation for /challenge/challenge! This program allows you to print arbitrary files to the terminal, when given the --printfile argument. The argument to the --printfile argument is the path of the flag to read. For example, /challenge/challenge --printfile /challenge/DESCRIPTION.md will print out the description of the level!

### Solving
```
/challenge/challenge --printfile /challenge/DESCRIPTION.md
/challenge/challenge --printfile /flag
```
### Flag :pwn.college{8sP2tOwzSKe3x3WmeZ79e4iaLXI.QX1ITO0wyNwcTNxEzW}

## Challenge 3:Learning Manuals
### Description 
Manpages are stored in a centralized database. If you're curious, this database lives in the /usr/share/man directory, but you never need to interact with it directly: you just query it using the man command. The arguments to the man command aren't file paths, but just the names of the entries themselves (e.g., you run man yes to look up the yes manpage, rather than man /usr/bin/yes, which would be the actual path to the yes program but would result in man displaying garbage).

The challenge in this level has a secret option that, when you use it, will cause the challenge to print the flag. You must learn this option through the man page for challenge!
### Solving
```
man challenge
/challenge/challenge        --yyiicg 003
```
<li> q to exit
<li>/ search withtin the file
<li>n to got to the next result 
<li>up/down key to navigate   

### Flag :pwn.college{0yyD0iO3TiCH0c7Zgd8mgs4puEf.QX0EDO0wyNwcTNxEzW}

## Challenge 4: Seraching Manuals
### Description 
You can scroll man pages with the arrow keys (and PgUp/PgDn) and search with /. After searching, you can hit n to go to the next result and N to go to the previous result. Instead of /, you can use ? to search backwards!

Find the option that will give you the flag by reading the challenge man page.
### Solving
```
man challenge
/challenge/challenge --ehh
```
### Flag:pwn.college{kzMbNy2RhwVtndjSSBle0IS7DO-.QX1EDO0wyNwcTNxEzW}

## Challenge 5:Searching for manuals
### Description 

HINT 1: man man teaches you advanced usage of the man command itself, and you must use this knowledge to figure out how to search for the hidden manpage that will tell you how to use /challenge/challenge

HINT 2: though the man page is randomly named, you still actually use /challenge/challenge to get the flag!
### Solving
```
 man -k challenge
 // Shows all manpages whose name or description contains challenge
 >zfijyhrugn (1)       - print the flag!
 man zfijyhrugn
  /challenge/challenge --zfijyh 88
```
### Flag :pwn.college{887-JZJzX8fYUijy4LhW0r3ugnn.QX2EDO0wyNwcTNxEzW}

## Challenge 6:Help
### Description 
Some programs don't have a man page, but might tell you how to run them if invoked with a special argument. Usually, this argument is --help, but it can often be -h or, in rare cases, -?, help, or other esoteric values like /? (though that latter is more frequently encountered on Windows).

In this level, you will practice reading a program's documentation with --help. Try it out!
### Solving
```
/challenge/challenge --help
```
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give you the flag
```
/challenge/challenge --p
/challenge/challenge --g 98
```
### Flag :pwn.college{0Y9U80mRzDyLQosu3KhKPkG1zoN.QX3IDO0wyNwcTNxEzW}

## Challenge 7:Builtins
### Description 
Some good information! In this challenge, we'll practice using help to look up help for builtins. This challenge's challenge command is a shell builtin, rather than a program. Like before, you need to lookup its help to figure out the secret value to pass to it!
### Solving
```
help challenge

```
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!
    
    Options:
      --fortune         display a fortune
      --version         display the version
      --secret VALUE    prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "sT67WGB9".
```
challenge --secret sT67WGB9
```
### Flag :pwn.college{sT67WGB9HNUSSh8hOAPZSVj2uR5.QX0ETO0wyNwcTNxEzW}