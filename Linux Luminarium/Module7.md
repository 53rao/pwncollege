
# Shell Variables
## Challenge 1: Printing Variable
### Description :
Let's start with printing variables out. The /challenge/run program will not, and cannot, give you the flag, but that's okay, because the flag has been put into the variable called "FLAG"! Just have your shell print it out!


### Solving
<li> we can $ do access varibles in the shell

```
echo $FLAG
```
### Flag :pwn.college{8FCNT_m63lxu7lX12aFm1-4tKY8.QX3UTN0wyNwcTNxEzW}

---

## Challenge 2:Setting Variables
### Description :
To solve this level, you must set the PWN variable to the value COLLEGE. Be careful: both the names and values of variables are case-sensitive! PWN is not the same as pwn and COLLEGE is not the same as College.
### Solving
<li>We can set variables using = 
```
PWN=COLLEGE
```
### Flag :pwn.college{Q1JpfjJW0BowyRMGyN-UP-6sIhu.QX5UTN0wyNwcTNxEzW}

---

## Challenge 3:Multi Word Variable
### Description :
Here, the shell reads 1337 SAUCE as a single token, and happily sets that value to VAR. In this level, you'll need to set the variable PWN to COLLEGE YEAH. Good luck!
### Solving
```
PWN="COLLEGE YEAH"
```
### Flag :pwn.college{Q9U23f3UUJ67LmYbWpj2LQds0nV.QXwYTN0wyNwcTNxEzW}

---

## Challenge 4:Exporting Varaibles
### Description :
In this challenge, you must invoke /challenge/run with the PWN variable exported and set to the value COLLEGE, and the COLLEGE variable set to the value PWN but not exported (e.g., not inherited by /challenge/run). Good luck!
### Solving
<li>We use export inorder to make shell variables environemnt variables

```
PWN=COLLEGE
export PWN
COLLEGE=PWN
/challenge/run PWN COLLEGE
```
### Flag :pwn.college{486IFWJjyfmDbEL3j7LY4RlKocY.QXyYTN0wyNwcTNxEzW}

---

## Challenge 5:Printing exported variables
### Description :
Try the env command: it'll print out every exported variable set in your shell, and you can look through that output to find the FLAG variable!
### Solving
```
env
```
returns a list which has FLAG=pwn.college{URXL9zmCbLwSC8AyseHsTQLNCiC.QX4UTN0wyNwcTNxEzW}
### Flag :pwn.college{URXL9zmCbLwSC8AyseHsTQLNCiC.QX4UTN0wyNwcTNxEzW}

---

## Challenge 6:
### Description :
Neat! Now, you practice. Read the output of the /challenge/run command directly into a variable called PWN, and it will contain the flag!
### Solving
<LI>We can also store the output exe directly into a variable

```
PWN=$(/challenge/run)
echo $PWN
```
### Flag :pwn.college{8DP8_vp7B-hXi-wEHrRZV4AiM1_.QX1cDN1wyNwcTNxEzW}

---

## Challenge 7:Reading input
### Description :
In this challenge, your job is to use read to set the PWN variable to the value COLLEGE. Good luck!


### Solving
<li> read -p "User interaction" variable_name read -p usede to input and store it in a varible

```
read -p "Yo" PWN
```
### Flag :pwn.college{4Dd6fC1ArlTLN8N3yc_f-ahqtkl.QX4cTN0wyNwcTNxEzW}

---

## Challenge 8:Reading files
### Description :
Now, use that to read /challenge/read_me into the PWN environment variable, and we'll give you the flag! The /challenge/read_me will keep changing, so you'll need to read it right into the PWN variable with one command!
### Solving
<li>We can combine read and < to set variables
```
read PWN</challenge/read_me
```
### Flag :pwn.college{UeJmKYKcZ_qNW8jrbTwFDFkFQf-.QXwIDO0wyNwcTNxEzW}

---