# Module 5 :

## Challenge 1:Matching with *
### Description :
Now, practice this yourself! Starting from your home directory, change your directory to /challenge, but use globbing to keep the argument you pass to cd to at most four characters! Once you're there, run /challenge/run for the flag!
### Solving
```
cd /*ge
/challenge/run
```
Globbing : pattern matching with wildards like *,[] or ?
### Flag : pwn.college{Yb-cAG6PnBkvEN-7wVEvK_OYXx_.QXxIDO0wyNwcTNxEzW}

## Challenge 2: Matching with ?
### Description :
Now, practice this yourself! Starting from your home directory, change your directory to /challenge, but use the ? character instead of c and l in the argument to cd! Once you're there, run /challenge/run for the flag!
### Solving 
```
cd /?ha??enge
/challenge/run
```
### Flag : pwn.college{IheDAG4mjuMwGym-tiRF0X3PVkK.QXyIDO0wyNwcTNxEzW}

## Challenge 3:Matching with []
### Description :
Try it here! We've placed a bunch of files in /challenge/files. Change your working directory to /challenge/files and run /challenge/run with a single argument that bracket-globs into file_b, file_a, file_s, and file_h!
### Solving
```
cd /challenge/files
/challenge/run file_[absh]
```
### Flag :pwn.college{YmOsRKdAacG4mxPbyNTAzx0U7uC.QXzIDO0wyNwcTNxEzW}

## Challenge 4: Matching paths with []
### Description :
Now it's your turn. Once more, we've placed a bunch of files in /challenge/files. Starting from your home directory, run /challenge/run with a single argument that bracket-globs into the absolute paths to the file_b, file_a, file_s, and file_h files!
### Solving
```
/challenge/run /challenge/files/file_[absh]
```
Learning so far
<li> * : ls *.txt fills the *
<li>? : fills one charcter to ?
<li>[] : mcq version 
```
echo Look: file_[ab]
cd /challenge/files/file_[abcd]
```

### Flag pwn.college{sqiW_ciyg8iF-uAId4aCsAIZwd3.QX0IDO0wyNwcTNxEzW}

## Challenge 5:Multiple globs
### Description :
What happens above is that the shell looks for all files in / that start with anything (including nothing), then have an f and an l, and end in anything (including ag, which makes flag).

Now you try it. We put a few happy, but diversely-named files in /challenge/files. Go cd there and run /challenge/run, providing a single argument: a short (3 characters or less) globbed word with two * globs in it that covers every word that contains the letter p.
### Solving
```
cd /challenge/files
/challenge/run *p*
```
### Flag : pwn.college{E0FjeXbDP9zqe88P4tq2b43c4wO.0lM3kjNxwyNwcTNxEzW}

## Challenge 6:Mixing globs
### Description :
Now, let's put the previous levels together! We put a few happy, but diversely-named files in /challenge/files. Go cd there and, using the globbing you've learned, write a single, short (6 characters or less) glob that (when passed as an argument to /challenge/run) will match the files "challenging", "educational", and "pwning"!
### Solving
```
#Tried
/challenge/run *[in]*
#amazing beautiful challenging delightful educational fantastic incredible jovial kind laughing magical nice optimistic pwning queenly radiant splendid thrilling uplifting victorious wonderful xenial
# Each alphabet has just one word
/challenge/run [cep]*

```
### Flag : pwn.college{4-qxcgBve1k3Qy39wZ20Xf4aEkc.QX1IDO0wyNwcTNxEzW}

## Challenge 7:Exclusionary Globbing 
### Description :
Armed with this knowledge, go forth to /challenge/files and run /challenge/run with all files that don't start with p, w, or n!

NOTE: The ! character has a different special meaning in bash when it's not the first character of a [] glob, so keep that in mind if things stop making sense! ^ does not have this problem, but is also not compatible with older shells.
### Solving
<li> ! used in bash negates [not gate] the arguments provided
<li> In regex, ^ inside [] is the standard way to negate a character set. Example: [^aeiou] matches any character except vowels
But in this question both work

```
/challenge/files
 /challenge/run [^pwn]*
```


### Flag :pwn.college{gm6OniuhIeosnx2i1z7JU4qf7hf.QX2IDO0wyNwcTNxEzW}

## Challenge 8:Tab Completion 

### Description :
This challenge has copied the flag into /challenge/pwncollege, and you can freely cat that file. But you can't type the filename: we used some serious trickery to make sure that you must tab-complete it. Try it out!
### Solving
```
cat /challenge/pwn + tab
```
### Flag: pwn.college{AkcrujzLWqQLAPB-OVPsJRLtIwt.0FN0EzNxwyNwcTNxEzW}

## Challenge 9:Multiple option for tab completion 
### Description :
What happens varies based on the specific shell and its options. By default bash will auto-expand until the first point when there are multiple options (in this case, fl). When you hit tab a second time, it'll print out those options. Other shells and configurations, instead, will cycle through the options.

This challenge has a /challenge/files directory with a bunch of files starting with pwncollege. Tab-complete from /challenge/files/p or so, and make your way to the flag!
### Solving
Tried various command such as ls ,cd then found this approach
```
file /challenge/files/p<TAB>
# completes to pwn and it is ascii
file /challenge/files/pwn
```

No flag in this file!
```
file /challenge/files/pwnc<TAB>
# completes to pwncollege-
file /challenge/files/pwncollege-f
```
pwncollege-flag      pwncollege-flamingo  
```
file /challenge/files/pwncollege-flag
cat /challenge/files/pwncollege-flag
```
### Flag : pwn.college{AtSbCN-g94Dg5q6rBi7Kz5lOhff.0lN0EzNxwyNwcTNxEzW}

## Challenge 10: Tab Completion on Commands
### Description :
Tab completion is for more than files! You can also tab-complete commands. This level has a command that starts with pwncollege, and it'll give you the flag. Type pwncollege and hit the tab key to auto-complete it!
### Solving
```
pwncollege<TAB>
#Makes it pwncollege-30513
```
### Flag :pwn.college{cOsnZLaOFdOPPkIV6ts7rFj6Stb.0VN0EzNxwyNwcTNxEzW}
