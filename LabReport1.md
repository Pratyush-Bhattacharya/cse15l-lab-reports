# Lab Report 1

## Change Directory (cd) Examples:
1: Without arguments
Without arguments, cd always reverts to the home directory regardless of the current working directory.
If the working directory is the home directory:
```
[user@sahara ~]$ cd
[user@sahara ~]$
```
The prompt remains unchanged in the above code. If the working directory is not the home directory:
```
[user@sahara ~/lecture1]$ cd
[user@sahara ~]$
```
In this case, the working directory was in the lecture1 folder. But cd with no arguments redirected it back to home. 

2: With a directory as an argument
With a directory within the current working directory as an argument, the command changes the working directory to the absolute directory of the working + argument.
If the working directory is the home directory:
```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$
```
If you instead put cd messages from the home directory, then an error message prints:
```
[user@sahara ~]$ cd messages
bash: cd: messages: No such file or directory
```
The cd command can only change directories to directories within the same working directory or layer.

3: With a file as an argument
An error message will always print. You cannot change directories to a file.
```
[user@sahara ~/lecture1]$ cd Hello.java
bash: cd: Hello.java: Not a directory
```

## List (ls) Examples:
1: Without arguments

