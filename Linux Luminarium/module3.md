# Module 3 :

## Challenge 1:cat : not the bet but the command
### Description :
In this challenge, I will copy the flag to the flag file in your home directory (where your shell starts). Go read it with cat!

### Solving 
Just cat flag file present in the home directory returns the flag
### Flag :pwn.college{MH9ttr5DQH-XW1ua6NmJEE4v4q7.QXxcTN0wyNwcTNxEzW}

## Challenge 2:Catting absolute paths
### Description :
In this directory, I will not copy it to your home directory, but I will make it readable. You can read it with cat at its absolute path: /flag.
### Solving 
cat /flag
### Flag :pwn.college{Ep15ZkBRaeWHNYRtyZ3IJiz1nzy.QX5ETO0wyNwcTNxEzW}

### Challenge 3:more catting practice
### Description :
You can specify all sorts of paths as arguments to commands, and we'll practice some more with cat. In this level, I'll put the flag in some crazy directory, and I will not allow you to change directories with cd, so no cat flag for you. You must retrieve the flag by absolute path, wherever it is.
### Solving 
Note was present You cannot use the 'cd' command in this level, and must retrieve the flag by 
absolute path. Plus, I hid the flag in a different directory! You can find it 
in the file /lib/systemd/user/flag. Go cat it out **without** cding into that 
directory!  
so
```
cat /lib/systemd/user/flag
```
### Flag :pwn.college{0JHUloT6dwGFaTCy3DeCnTRNt99.QXwITO0wyNwcTNxEzW}



## Challenge 4:grepping for a needle in a haystack
### Description :
Invoked like this, grep will search the file for lines of text containing SEARCH_STRING and print them to the console.

In this challenge, I've put a hundred thousand lines of text into the /challenge/data.txt file. Grep it for the flag!

HINT: The flag always starts with the text pwn.college.
### Solving 
grep pwn.college /challenge/data.txt
### Flag : pwn.college{YQmnB4Waf8pTexn-ihTAr6h_q-c.QX3EDO0wyNwcTNxEzW}

## Challenge 5:Listing files
### Description :
ls will list files in all the directories provided to it as arguments, and in the current directory if no arguments are provided. Observe:
In this challenge, we've named /challenge/run with some random name! List the files in /challenge to find it.


### Solving 
```
ls /challenge
/challenge/3157-renamed-run-11112
```
### Flag : pwn.college{QfvLPjjbdA_v6kfP_gVUqiWqHs2.QX4IDO0wyNwcTNxEzW}

## Challenge 6:Touching files
### Description :
It's that simple! In this level, please create two files: /tmp/pwn and /tmp/college, and run /challenge/run to get your flag!
### Solving 
```
touch /tmp/pwn
touch /tmp/college
/challenge/run
```
### Flag :pwn.college{4Y_80jH1sG8uIM-vrWv8tNaBENQ.QXwMDO0wyNwcTNxEzW}

## Challenge 7:Removing files
### Description :
Let's practice. This challenge will create a delete_me file in your home directory! Delete it, then run /challenge/check, which will make sure you've deleted it and then give you the flag!
### Solving 
```
touch delete_me
rm delete_me
/challenge/check
```
### Flag :pwn.college{gjlt0m4Y6nQdb1yhBn7zSUudq_d.QX2kDM1wyNwcTNxEzW}


## Challenge 8:Moving files
### Description :
This challenge wants you to move the /flag file into /tmp/hack-the-planet (do it)! When you're done, run /challenge/check, which will check things out and give the flag to you.
### Solving 
```
mv /flag / 
mv <source> <target> 
```
### Flag :pwn.college{UOHgY6iKWF46aKuftVbAhzk7kSw.0VOxEzNxwyNwcTNxEzW}

## Challenge 9:Hidden files
### Description :
Now, it's your turn! Go find the flag, hidden as a dot-prepended file in /.
### Solving 
```
ls -a /
file /.flag-11735100851106
cat //.flag-11735100851106
```
### Flag :pwn.college{4rllFcvQMOsk9UdZTiTe3qHCiWi.QXwUDO0wyNwcTNxEzW}


## Challenge 10:An file system quest
### Description :
In this challenge, I have hidden the flag! Here, you will use ls and cat to follow my breadcrumbs and find it! Here's how it'll work:

Your first clue is in /. Head on over there.
Look around with ls. There'll be a file named HINT or CLUE or something along those lines!
cat that file to read the clue!
Depending on what the clue says, head on over to the next directory (or don't!).
Follow the clues to the flag!
Good luck!
### Solving 
```
ls -a /
cat /CUE
```
Tubular find!
The next clue is in: /usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/Gyre-Termes/Monospace

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
```
ls -a /usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/Gyre-Termes/Monospace
file /usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/Gyre-Termes/Monospace/BRIEF-TRAPPED
cat /usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/Gyre-Termes/Monospace/BRIEF-TRAPPED
```
Lucky listing!
The next clue is in: /usr/lib/python3/dist-packages/networkx/utils/tests

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
```
ls -a /usr/lib/python3/dist-packages/networkx/utils/tests
file /usr/lib/python3/dist-packages/networkx/utils/tests/.BLUEPRINT
cat /usr/lib/python3/dist-packages/networkx/utils/tests/.BLUEPRINT
```
Yahaha, you found me!
The next clue is in: /usr/local/lib/python3.8/dist-packages/flask/__pycache__

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
```
cd /usr/local/lib/python3.8/dist-packages/flask/__pycache__
cat WHISPER

```
Lucky listing!
The next clue is in: /usr/share/doc/zlib1g

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!

```
ls /usr/share/doc/zlib1g
cat /usr/share/doc/zlib1g/NUGGET-TRAPPED 

```
Great sleuthing!
The next clue is in: /opt/linux/linux-5.4/include/linux/clk

```
ls / /opt/linux/linux-5.4/include/linux/clk/
cat / /opt/linux/linux-5.4/include/linux/clk/README
```
Congratulations, you found the clue!
The next clue is in: /usr/lib/python3/dist-packages/docutils/parsers/rst/languages
```
ls /usr/lib/python3/dist-packages/docutils/parsers/rst/languages
cat /usr/lib/python3/dist-packages/docutils/parsers/rst/languages/TRACE

```
Tubular find!
The next clue is in: /usr/lib/python3.8/pydoc_data

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'
```
cd /usr/lib/python3.8/pydoc_data
cat EVIDENCE
```
Congratulations, you found the clue!
The next clue is in: /usr/lib/R/library/grid/html

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
```
cd /usr/lib/R/library/grid/html
cat TIP
```
On running this we get the flag
### Flag : pwn.college{ALVh73GZQwX6fDJSddnfocOgtbk.QX5IDO0wyNwcTNxEzW}


## Challenge 11: Making directories
### Description :
Now, go forth and create a /tmp/pwn directory and make a college file in it! Then run /challenge/run, which will check your solution and give you the flag!
### Solving 
```
mkdir /tmp/pwn
touch /tmp/pwn/college
/challenge/run
```
### Flag :pwn.college{Q0uFhGV1aJIDUqLefpw7W7SSCLh.QXxMDO0wyNwcTNxEzW}

### Challenge 12: finding files
### Description :
Now it's your turn. I've hidden the flag in a random directory on the filesystem. It's still called flag. Go find it!

Several notes. First, there are other files named flag on the filesystem. Don't panic if the first one you try doesn't have the actual flag in it. Second, there're plenty of places in the filesystem that are not accessible to a normal user. These will cause find to generate errors, but you can ignore those; we won't hide the flag there! Finally, find can take a while; be patient!

### Solving 
```
find / -type f -name flag 2>/dev/null
# /usr/lib/python3.8/xmlrpc/__pycache__/flag
cat /usr/lib/python3.8/xmlrpc/__pycache__/flag
```
<li>We can also specifiy the file type while searching using -type
<li>We can use  2>/dev/null
### Flag :pwn.college{wlpkK-9FanhJPeYqxr8auI5UGFg.QXyMDO0wyNwcTNxEzW}

## Challenge 13: Linking files
### Description :
### Solving 
Checked the file type of /home/hacker/not-the-flag but there was no such file so 
```
ln -s /flag /home/hacker/not-the-flag
/challenge/catflag
```
### Flag :pwn.college{AAwaeEKnRBzscRK68iBszVzGBZU.QX5ETN1wyNwcTNxEzW}