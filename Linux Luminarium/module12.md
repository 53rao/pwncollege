## Challenge 1:Chaining wth semicolon
### Description :
Give it a try now! In this level, you must run /challenge/pwn and then /challenge/college, chaining them with a semicolon.
### Solving
```
/challenge/pwn ;/challenge/college
```
### Flag : pwn.college{wcFDU2AQd9N7OTaQ6bvZzGzpUNH.QX1UDO0wyNwcTNxEzW}

---

## Challenge 2: Build on success
### Description :
In this challenge, you need to chain the programs /challenge/first-success and /challenge/second using the && operator. Try running each command separately first to see what happens (which is that you will not get the flag). But if you chain them with &&, the flag will appear!
### Solving
```
 /challenge/first-success && /challenge/second
```
### Flag : pwn.college{IL6TTLDtadfs3MhTTrYk6bX7mMv.0lM0MDOxwyNwcTNxEzW}

---
## Challenge 3: Handling Failure
### Description :
In this challenge, you need to chain /challenge/first-failure and /challenge/second using the || operator. Go for it!
### Solving
```
which win
 /challenge/first-failure || /challenge/second
```
### Flag : pwn.college{MBu-eBJrBIVfGercUu1QAKqrTnB.01M0MDOxwyNwcTNxEzW}

---
## Challenge 4:Your first Shell Script
### Description :
Same as last level, run /challenge/pwn and then /challenge/college, but this time in a shell script called x.sh, then run it with bash!
### Solving
```
nano x.sh
#In nano editor
/challenge/pwn;
/challenge/college
#
bash x.sh
```
### Flag : pwn.college{s5zQVn2JiJyA8VK31FxZHV4Q9IQ.QXxcDO0wyNwcTNxEzW}

---
## Challenge 5:Redirecting Output
### Description :
In this level, we will practice piping (|) from your script to another program. Like before, you need to create a script that calls the /challenge/pwn command followed by the /challenge/college command, and pipe the output of the script into a single invocation of the /challenge/solve command!
### Solving
```
bash x.sh | /challenge/solve
```
### Flag : pwn.college{81LbIL-qKIqsdcJqaa2hX4BC-8m.QX4ETO0wyNwcTNxEzW}
---

## Challenge 6: Exec Shell Script
### Description :
Make a shellscript that will invoke /challenge/solve, make it executable, and run it without explicitly invoking bash!
### Solving
```
nano script.sh
#In editor 
/challenge/solve
#
chmod +x script.sh
./script.sh
```
### Flag : pwn.college{Utv42McnK6LoT5gBYShijCMZtwF.QX0cjM1wyNwcTNxEzW}
---
---
## Challenge 7:Understanding shebangs
### Description :
For this challenge, create a script at /home/hacker/solve.sh that has a proper shebang and outputs "hack the planet". Remember to make it executable, then run /challenge/run to verify your script works correctly!

### Solving
```
nano solve.sh
# In nano editor
#!/bin/bash
echo "hack the planet"
#
chmod +x solve.sh

 /challenge/run
```
### Flag : pwn.college{AZWACdzA8P1tpQUC_rCGpEUEqNH.0VOzMDOxwyNwcTNxEzW}

---
---
## Challenge 8:Scripting with arguments
### Description :
For this challenge, you need to write a script at /home/hacker/solve.sh that:

Takes two arguments
Outputs them in REVERSE order (second argument first, then the first argument)
### Solving
```
nano solve.sh
#!/bin/bash
echo "$2 $1"
```
### Flag : pwn.college{w55U5XSxX553x1bNKTaA43YLpMH.0VNzMDOxwyNwcTNxEzW}

---
---
## Challenge 9:Scripting with conditions
### Description :
For this challenge, write a script at /home/hacker/solve.sh that:

Takes one argument
If the argument is "pwn", output "college"
For any other input, output nothing

### Solving
nano solve.sh
```
#
if [ "$1" == "pwn" ]
then
    echo "college"
fi
#
```
### Flag : pwn.college{8Z7r-DnD0h2KdcvvR87OUVLFxwz.0lNzMDOxwyNwcTNxEzW}

---
---
## Challenge 10:Scripting with default
### Description :

### Solving
Just alter solve.sh from previous question
```
if [ "$1" == "pwn" ]
then
    echo "college"
else
        echo "nope"
fi
```
### Flag : pwn.college{I5SPK9EzXz7ARtjV5oQcu1ujZXp.01NzMDOxwyNwcTNxEzW}

---
---
## Challenge 11:Scripting Multiple conditions
### Description :
For this challenge, write a script at /home/hacker/solve.sh that:

Takes one argument
If the argument is "hack", output "the planet"
If the argument is "pwn", output "college"
If the argument is "learn", output "linux"
For any other input, output "unknown"
### Solving
### Note : [] requires space and even == requires space "$1"=="pwn" causes problems
```
if [ "$1" == "hack" ]
then
    echo "the planet"
elif [ "$1" == "pwn" ]
then
        echo "college"
elif  [ "$1" ==  "learn" ]
then
        echo "linux"
else
        echo "unknown"
fi
```
### Flag : pwn.college{Ei3addGV_99QTmyysOosp9hYbKf.0FOzMDOxwyNwcTNxEzW}

---
---
## Challenge 12:
### Description :
In this level, we will learn to read shell scripts. /challenge/run is a shell script that requires you to put in a secret password, but that password is hardcoded into the script iself! Read the script (using, say, cat), figure out the password, and get the flag!
### Solving
```
cat /challenge/run
read GUESS
if [ "$GUESS" == "hack the PLANET" ]
then
        echo "CORRECT! Your flag:"
        cat /flag
else
        echo "Read the /challenge/run file to figure out the correct password!"
fi

/challenge/run 
INPUT : hack the PLANET
```
### Flag : pwn.college{EgFTwHMpgkb_LSU8-2FH7c9-inN.0lMwgDOxwyNwcTNxEzW}

---
