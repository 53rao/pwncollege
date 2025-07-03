#
## Module 1 :
### Challenge 1: Your first register
In this challenge, you will write your first assembly. You must move the value 60 into rax. Write your program in a file with a .s extension, such as rax-challenge.s (while not mandatory, .s is the typical extension for assembly files), and pass it as an argument to the /challenge/check file (e.g., /challenge/check rax-challenge.s). You can use either your favorite text editor or the text editor in pwn.college's VSCode Workspace to implement your .s file!
### Solving :
```
touch m1_t1.s
echo "mov rax,60">m1_t1.s
/challenge/check m1_t1.s
```

### Flag :pwn.college{oEbbgY5UVEEsPbpzWYt_N3so5Vq.QXzQDO1wyNwcTNxEzW}

### Challenge 2 : Your first Syscall
### Solving :syscall
```
mov rax,60;
syscall;

```


### Flag :pwn.college{sGVqbmHx7db_wYah13e4oSEVWx8.QX4YDO1wyNwcTNxEzW}

### Cgallenge 3 : Exit Code
### Solving : rdi
```
mov rax,60;
mov rdi,42(exit_code);
syscall;
```

### Flag: pwn.college{YjoltK-7Hi5GM2lgap26qB1AV8X.QXwcDO1wyNwcTNxEzW}

### Challenge 4:Building executables

### Flag : pwn.college{I3OQzRT4q4R-A1u9--oR1_QmDVS.0FM3IDMxwyNwcTNxEzW}

### Challenge 5: 

### Flag : pwn.college{gfGFxbAiY_s-stbkeDlhK4zf1YI.QX5QTN2wyNwcTNxEzW}