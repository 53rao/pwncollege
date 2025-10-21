## Challenge 1:
### Description :
In this level, you will disrupt the operation of the /challenge/run program. This program will DELETE the flag file using the rm command. However, if it can't find the rm command, the flag will not be deleted, and the challenge will give it to you! Thus, you must make it so that /challenge/run also can't find the rm command!


### Solving
Just alter the PATH so that /challeneg/run cant find the rm 
```
PATH=""
```
### Flag :pwn.college{ktm4DPSM021tRlmpowGDGSJrRmY.QX2cDM1wyNwcTNxEzW}

---
## Challenge 2:
### Description :
This level's /challenge/run will run the win command via its bare name, but this command exists in the /challenge/more_commands/ directory, which is not initially in the PATH. The win command is the only thing that /challenge/run needs, so you can just overwrite PATH with that one directory. Good luck!
### Solving
```
PATH="/challenge/more_commands"
```
### Flag :pwn.college{Y9ravJ7ekR9IYQbBz5gDk3z45aE.QX1cjM1wyNwcTNxEzW}

---
## Challenge 3:
### Description :
In this challenge, we added a win command somewhere in your $PATH, but it won't give you the flag. Instead, it's in the same directory as a flag file that we made readable by you! You must find win (with the which command), and cat the flag out of that directory!
### Solving
```
which win 
>/challenge/paths/15839/win
cd /challenge/paths/15839
cat flag
```
### Flag :pwn.college{kexn8eVkhmUiNNFm0j1oyBTNteH.01NzEzNxwyNwcTNxEzW}

---
## Challenge 4:
### Description :
Previously, the win command that /challenge/run executed was stored in /challenge/more_commands. This time, win does not exist! Recall the final level of Chaining Commands, and make a shell script called win, add its location to the PATH, and enable /challenge/run to find it!
### Solving
```
PATH :'Original:/home/hacker' <-- Adding current since we cant access other paths
nano win
#In nano editor
cat /flag
#
/challenge/run
```
### Flag :pwn.college{4A_yUyQBpeqw9Wha9gjhvD6V04T.QX2cjM1wyNwcTNxEzW}

---
## Challenge 5:
### Description :
This challenge is almost the same as the first challenge in this module. Again, this challenge will delete the flag using the rm command. But unlike before, it will not print anything out for you.

How can you solve this? You know that rm is searched for in the directories listed in the PATH variable. You have experience creating the win command when the previous challenge needed it. What else can you create?
### Solving
Created a rm file in home directory and a symbolic link to cat and set the PATH to home directory, initially i just created rm which cat /flag like previous but that didnt work because cat was not recognised ,tried removing rm file and adding home directory so only this works ,faced issues in that.The follwing approach gave the flag 
```
nano rm
# in nano editor 
cat /flag
#
chmod +x rm
which cat
mv /run/dojo/bin/cat /home/hacker/cat <--This created a symbolic link\
/challenge/run
```
### Flag :pwn.college{k-ayg3JAkGmPBtGLuF9SUXqtzJL.QX3cjM1wyNwcTNxEzW}

---