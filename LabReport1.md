# Lab Report 1

## Change Directory `cd` Examples:
**1: Without arguments**

Without arguments, `cd` always reverts to the home directory regardless of the current working directory.
If the working directory is the home directory:
```
[user@sahara ~]$ cd
[user@sahara ~]$
```
There is no error. The prompt remains unchanged in the above code. If the working directory is not the home directory:
```
[user@sahara ~/lecture1]$ cd
[user@sahara ~]$
```
There is no error. In this case, the working directory was in the `lecture1` folder. But `cd` with no arguments redirected it back to home. 

**2: With a directory as an argument**

With a directory within the current working directory as an argument, `cd` changes the working directory to the absolute directory of the working + argument.
If the working directory is the home directory:
```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$
```
There is no error. 
If you instead put `cd` messages from the home directory, then an error message prints:
```
[user@sahara ~]$ cd messages
bash: cd: messages: No such file or directory
```
The `cd` command can only change directories to directories within the same working directory or layer.

**3: With a file as an argument**

An error message will always print. You cannot change directories to a file.
When the working directory is the `lecture1` folder.
```
[user@sahara ~/lecture1]$ cd Hello.java
bash: cd: Hello.java: Not a directory
```


## List `ls` Examples:
**1: Without arguments**

When the working directory is the home directory, and when you `cd` into `lecture1` folder making the working directory in the `lecture1` folder:
```
[user@sahara ~]$ ls
lecture1
[user@sahara ~]$ cd lecture1/
[user@sahara ~/lecture1]$ ls
Hello.class  Hello.java  messages  README
```
There is no error. From the above code, `ls` without arguments prints out or lists all available files and directories within the current working directory. Directories are printed in blue and bold.

**2: With a directory as an argument**

When the working directory is the `lecture1` folder.
```
[user@sahara ~/lecture1]$ ls messages/
ar-eg.txt  en-us.txt  es-mx.txt  zh-cn.txt
[user@sahara ~/lecture1]$ ls ..
lecture1
```
There is no error. The command lists all files contained within that absolute directory. 

**3. With a file as an argument**

When the working directory is the `lecture1` folder.
```
[user@sahara ~/lecture1]$ ls Hello.java 
Hello.java
[user@sahara ~/lecture1]$ ls messages/ar-eg.txt 
messages/ar-eg.txt
```
There is no error. This time, `ls` prints out the argument only.

## Concatenate `cat` Examples:
**1: Without arguments**

Without arguments, the terminal breaks down and doesn't know what to do. When the working directory is the home directory.
```
[user@sahara ~]$ cat
aaaa
aaaa
djfksf
djfksf
lecture1
lecture1
Hello.java
Hello.java
```
This is probably an error. However, there is no error-handling message. The terminal prints out whatever you input. Using special characters breaks or changes the position of the cursor. The terminal is unusable until `<Ctrl> + C` is pressed.

**2: With a directory as an argument**

When the working directory is the `lecture` folder.
```
[user@sahara ~/lecture1]$ cat messages/
cat: messages/: Is a directory
```
This is an error. `cat` with any valid directory as an argument prints an error-handling message.

**3: With a file as an argument**

When the working directory is the `lecture1` folder.
```
[user@sahara ~/lecture1]$ cat messages/ar-eg.txt 
مرحبا بالعالم!
```
There is no error. `cat` with a file as an argument prints out the contents of that file.
