# Lab Report 1

## Change Directory (cd) Examples:
1: Without arguments
Without arguments, cd always reverts back to the home directory regardless of the current working directory.
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

2: With directory argument
```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$
```

3: With file argument
```
[user@sahara ~/lecture1]$ cd Hello.java
bash: cd: Hello.java: Not a directory
```
