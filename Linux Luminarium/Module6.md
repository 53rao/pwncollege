# Module 6 : Practicing Piping

## Challenge 1:Redirecting output
### Description :
In this challenge, you must use this input redirection to write the word PWN (all uppercase) to the filename COLLEGE (all uppercase).
### Solving
```
echo PWN > COLLEGE
```
<li> > operator redirects stdout to files

### Flag :pwn.college{EzN0zdusShlVhiH29CpGJrWde5D.QX0YTN0wyNwcTNxEzW}

---

## Challenge 2:Redirecting more output
### Description :
Aside from redirecting the output of echo, you can, of course, redirect the output of any command. In this level, /challenge/run will once more give you a flag, but only if you redirect its output to the file myflag. Your flag will, of course, end up in the myflag file!

You'll notice that /challenge/run will still happily print to your terminal, despite you redirecting stdout. That's because it communicates its instructions and feedback over standard error, and only prints the flag over standard out!
### Solving
```
/challenge/run > myflag
cat myflag

```
### Flag :pwn.college{kVsMGViQuU4DCVRkeY8m9atGwRO.QX1YTN0wyNwcTNxEzW}

---

## Challenge 3:Appending output
### Description :
To practice, run /challenge/run with an append-mode redirect of the output to the file /home/hacker/the-flag. The practice will write the first half of the flag to the file, and the second half to stdout if stdout is redirected to the file. If you properly redirect in append-mode, the second half will be appended to the first, but if you redirect in truncation mode (>), the second half will overwrite the first and you won't get the flag!
### Solving
```
/challenge/run >> the-flag
```
<li> >> appends the desired input to the file [It appends not write]

### Flag :pwn.college{EgKIDx8W4DQXDDhbLABkpTErC0k.QX3ATO0wyNwcTNxEzW}

---

## Challenge 4:Redirecting errors
### Description :
That command will redirect output to output.log and errors to errors.log.

Let's put this into practice! In this challenge, you will need to redirect the output of /challenge/run, like before, to myflag, and the "errors" (in our case, the instructions) to instructions. You'll notice that nothing will be printed to the terminal, because you have redirected everything! You can find the instructions/feedback in instructions and the flag in myflag when you successfully pull this off!
### Solving
File descriptor is a number that describes the communications channel
<li> 0 for input stream
<li> 1 for output stream
<li> 2 for standards error
By default it is 1 


```
/challenge/run >myflag 2>instructions
cat myflag
```
### Flag :pwn.college{U1wYsE903oNmjLoNzLyhTSM0gNq.QX3YTN0wyNwcTNxEzW}

---

## Challenge 5:Redirecting input
### Description :
You can do interesting things with a lot of different programs using input redirection! In this level, we will practice using /challenge/run, which will require you to redirect the PWN file to it and have the PWN file contain the value COLLEGE! To write that value to the PWN file, recall the prior challenge on output redirection from echo!
### Solving
<li> For FD 0: 


```
# EXE < File 
# By default the value is 0 in this case
echo COLLEGE > PWN
/challenge/run < PWN

```
### Flag :pwn.college{c9mfsQt6d14VUHC4CArP7LtbJGu.QXwcTN0wyNwcTNxEzW}

---

## Challenge 6:Grepping stored results
### Description :
In preparation for more complex levels, we want you to:

Redirect the output of /challenge/run to /tmp/data.txt.
This will result in a hundred thousand lines of text, with one of them being the flag, in /tmp/data.txt.
Grep that for the flag!
### Solving
```
 /challenge/run > /tmp/data.txt
 grep pwn.college{ /tmp/data.txt
```
### Flag :pwn.college{0D9HDGWP50s29F2o4HfJE7GVRXK.QX4EDO0wyNwcTNxEzW}

---

## Challenge 7: Grepping live output
### Description :
Now try it for yourself! /challenge/run will output a hundred thousand lines of text, including the flag. Grep for the flag!
### Solving
```
/challenge/run | grep pwn.college{
```
### Flag :pwn.college{ozvh8nzbCARICy5_dhvUCEMoUFI.QX5EDO0wyNwcTNxEzW}

---

## Challenge 8:Grepping errors
### Description :
The shell has a >& operator, which redirects a file descriptor to another file descriptor. This means that we can have a two-step process to grep through errors: first, we redirect standard error to standard output (2>& 1) and then pipe the now-combined stderr and stdout as normal (|)!

Try it now! Like the last level, this level will overwhelm you with output, but this time on standard error. Grep through it to find the flag!
### Solving

#### NOTE : 2>&1 to convert FD 0 TO FD 1
```
/challenge/run 2>&1 | grep pwn.college{
```
### Flag :pwn.college{QX30wUeF9lX49Ij5Z6Oze6q3xK0.QX1ATO0wyNwcTNxEzW}

---

## Challenge 9:Filtering with grep -v
### Description :
Sometimes, the only way to filter to just the data you want is to filter out the data you don't want. In this challenge, /challenge/run will output the flag to stdout, but it will also output over 1000 decoy flags (containing the word DECOY somehwere in the flag) mixed in with the real flag. You'll need to filter out the decoys while keeping the real flag!

Use grep -v to filter out all the lines containing "DECOY" and reveal the real flag!
### Solving
<li> grep with argument -v just avoids the line with the word provided

```
/challenge/run | hrep -v DECOY
```
### Flag : pwn.college{QMclrg-wRg9oXv2LQ_q_zQIfseB.0FOxEzNxwyNwcTNxEzW}

---

## Challenge 10:Duplicate with piped tee
### Description :
Now, you try it! This process' /challenge/pwn must be piped into /challenge/college, but you'll need to intercept the data to see what pwn needs from you!
### Solving
<li>tee can be used to copy the input provided into two different file 

echo hi | tee file1 file2

<li>tee can also be used two intercept and pass on 

echo hi | tee copy | file

```
/challenge/pwn --secret MzoukRLQ |tee dist| /challenge/college
/challenge/pwn --secret MzoukRLQ | /challenge/college
```
### Flag :pwn.college{MzoukRLQADsdhi4vWPGZ-PoHgZj.QXxITO0wyNwcTNxEzW}

---

## Challenge 11:Process subsitution for input 
### Description :
Now for your challenge! Recall what you learned in the diff challenge from Comprehending Commands. In that challenge, you diffed two files. Now, you'll diff two sets of command outputs: /challenge/print_decoys, which will print a bunch of decoy flags, and /challenge/print_decoys_and_flag which will print those same decoys plus the real flag.

Use process substitution with diff to compare the outputs of these two programs and find your flag!
<li>Process substitution lets us treat command line output as input to a different command and supports multiple input unlike piping 

```
 diff <(/challenge/print_decoys_and_flag) <(/challenge/print_decoys)
```
### Flag : pwn.college{Qdisgytp_OMRk6H1P8xWqYlPo92.0lNwMDOxwyNwcTNxEzW}

---

## Challenge 12:Process substitution for input
### Description :
Now it's your turn! In this challenge, we have /challenge/hack, /challenge/the, and /challenge/planet. Run the /challenge/hack command, and duplicate its output as input to both the /challenge/the and the /challenge/planet commands!
### Solving
<li> Process substitution can als be used for input
```
echo HACK | tee >(rev)
HACK
KCAH
```
Providing input too multiple exe

```
 /challenge/hack |tee >(/challenge/the) >(/challenge/planet)
```


### Flag : pwn.college{oWzastuJWJrbRi56yR1afz5s-be.QXwgDN1wyNwcTNxEzW}

---

## Challenge 13:Split pipping stderr and stdout
### Description :
In this challenge, you have:

/challenge/hack: this produces data on stdout and stderr
/challenge/the: you must redirect hack's stderr to this program
/challenge/planet: you must redirect hack's stdout to this program
Go get the flag!
### Solving
#### Note : 2> >(command not 2>(command)
```
/challenge/hack 2> >( /challenge/the ) | /challenge/planet
```
### Flag :pwn.college{EHUbyxuE9Ztjn7pzjWkjZfL7f9K.QXxQDM2wyNwcTNxEzW}

---

## Challenge 14:Named pipes
### Description :
This challenge will be a simple introduction to FIFOs. You'll need to create a /tmp/flag_fifo file and redirect the stdout of /challenge/run to it. If you're successful, /challenge/run will write the flag into the fifo! Go do it!
### Solving
```

```
### Flag :pwn.college{s4qCojEoa1Z2sECcECfh7WBi_QF.01MzMDOxwyNwcTNxEzW}



