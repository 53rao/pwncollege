# LINUX Luminarium

##  Module 1 : *Hello Hackers*
### Challenge 1 : Intro to Commands
In this challenge, you will invoke your first command! When you type a command and hit enter, the command will be invoked, as so:
```
hacker@dojo:~$ whoami
hacker
hacker@dojo:~$
```
Here, the user executed the whoami command, which simply prints the username (hacker) to the terminal. When the command terminates, the shell once again displays the prompt, ready for the next command.
In this level, invoke the hello command to get the flag!   
__Keep in mind: commands in Linux are case sensitive__  
hello is different from HELLO.*
### Solution and Learning : 
A simple hello command returns the flag .All linux commands are case sensitive.
### Flag : pwn.college{wfPKeCxs66G-zYdqlLS3SLlvnxb.QX3YjM1wyNwcTNxEzW} 

### Challenge 2 : Intro to Arguments
Let's try something more complicated: a command with arguments, which is what we call additional data passed to the command. When you type a line of text and hit enter, the shell actually parses your input into a command and its arguments. The first word is the command, and the subsequent words are arguments. Observe:
```
hacker@dojo:~$ echo Hello
Hello
hacker@dojo:~$
```
In this case, the command was echo, and the argument was Hello. echo is a simple command that "echoes" all of its arguments back out onto the terminal, like you see in the session above.

Let's look at echo with multiple arguments:
```
hacker@dojo:~$ echo Hello Hackers!
Hello Hackers!
hacker@dojo:~$
```
In this case, the command was echo, and Hello and Hackers! were the two arguments to echo. Simple!

In this challenge, to get the flag, you must run the hello command (NOT the echo command) with a single argument of hackers. Try it now!

### Solution and Learning :
hello command along with hackers argument returns the flag.   
echo command is used display output in terminal.

### Flag : pwn.college{s3e3hgAWMvb0JTVOGoaCXE1YqvF.QX4YjM1wyNwcTNxEzW}

### Challenge 3 :Command History
### Description :
You're going to type a lot of commands, and typing everything from scratch can be annoying. Luckily, the shell saves a history of every command you invoke.

You can scroll through those saved commands with the up/down arrow keys, and we'll practice that in this challenge. This challenge will inject the flag into your history. Bring up a terminal, hit the up arrow, and grab it! In other challenges, the history will contain the log of the commands you've run, so if you need to run a similar command again, you can use the arrow keys to scroll through and find it!
### Solving :
I had missed this challenge intially so using arrow keys wasnt an option therfore used history and grep tool
```
history | grep flag
```
### Flag : pwn.college{YeXTmk9FVP58oQE1KFSA_zQIRyP.0lNzEzNxwyNwcTNxEzW}
