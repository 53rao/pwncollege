# Data Manipulation

## Challenge 1:Translating Chacrters

### Description :
Now, you try it! In this level, /challenge/run will print the flag but will swap the casing of all characters (e.g., A will become a and vice-versa). Can you undo it with tr and get the flag?
### Solving
<li> tr command can be used to alter charcters and we can also pass multiples switches seperated by commas

```
 /challenge/run | tr A-Z,a-z a-z,A-Z
```
### Flag :pwn.college{Me_kI5rAFXd3km3WvToFCcThI0U.01MxEzNxwyNwcTNxEzW}

---
## Challenge 2:Deleting Charaters
### Description :
Pretty simple! Now you give it a try. I'll intersperse some decoy characters (specifically: ^ and %) among the flag characters. Use tr -d to remove them!
### Solving
```
/challenge/run | tr -d %,^
```
### Flag :pwn.college{0usPHgYjCDBKP1AENltEtcw2bF4.0FNxEzNxwyNwcTNxEzW}

---
## Challenge 3:
### Description :
Now, let's combine this with deletion. In this challenge, we'll inject a bunch of newlines into the flag. Delete them with tr's -d flag and the escaped newline specification!
### Solving
```
/challenge/run | tr -d "\n"
```
### Flag :pwn.college{0X4ILOoB3tozkjYhCSlt1BKNJqM.0VNxEzNxwyNwcTNxEzW}

---
## Challenge 4:Extracting first lines with head
### Description :

### Solving
```
/challenge/pwn | head -n 7 |/challenge/college
```
### Flag :pwn.college{gZIjiKQ22Cf0ayy8lAnvyv3M3kh.0lNxEzNxwyNwcTNxEzW}

---
## Challenge 5:
### Description :
In this challenge, the /challenge/run program will give you a bunch of lines with random numbers and single characters (characters of the flag) as columns. Use cut to extract the flag characters, then pipe them to tr -d "\n" (like the previous level!) to join them together into a single line. Your solution will look something like /challenge/run | cut ??? | tr ???, with the ??? filled out.
### Solving
#### cut -d 'delimiter' -f Column_Number .
```
/challenge/run | cut -d ' ' -f 2|tr -d '\n'
```
### Flag :pwn.college{kL5zxthpwG8yQNlHdIlwACJpo-i.01NxEzNxwyNwcTNxEzW}

---
## Challenge 6:
### Description :
In this challenge, there's a file at /challenge/flags.txt containing 100 fake flags, with the real flag mixed among them. When sorted alphabetically, the real flag will be at the end (we made sure of this when generating fake flags). Go get it!
### Solving
```
sort -r /challenge/flags.txt
```
### Flag :pwn.college{s86QYZJdqJAyLXgehbk2WiEE2VL.0FM0MDOxwyNwcTNxEzW}

---