# Linux Fundamentals Part 1

- **Platform:** TryHackMe
- **Difficulty:** Easy
- **Topics:** Linux, command line
- **Room link:** [Linux Fundamentals Part 1](https://tryhackme.com/room/linuxfundamentalspart1)

*Note: answers and flags are hidden. Try to find them yourself, it is more fun this way!*

---
## Walkthrough
### #Task1 - Introduction
To begin with, I can see some information about **Linux OS** (Operating System). It is very important to read it attentively, because I must understand what I am working with.
Firstly, it requires deploying a lab machine so I can interact with the Linux command line.

---
### #Task2 - Talking to Linux
There are 2 commands: `whoami` and `echo`

After understanding and using these commands, I can see how they work:

`whoami` - shows in the terminal who I am, so I can understand which user (there can be several) is interacting with the command line.
```
tryhackme@linux1:~$ whoami
tryhackme
```
`echo` - it writes what I type to the terminal, it outputs the input.
```
tryhackme@linux1:~$ echo TryHackMe
TryHackMe
```
Text can also be written in single `' '` or double quotes `" "`.

---
### #Task3 - Finding Your Way Around
There are new commands!
`ls`, `cd`, `cat`, `pwd`
These are navigation commands, which allow to move around the terminal without using the mouse.

`ls` - stands for **list directory**, which means it lists what is in the current path we are in.

`cd` - **change directory**, allows moving from one path to another, navigating the terminal.

`cat` - **concatenate**, it shows the inside of the file, what it contains.

`pwd` - **print working directory**, it shows the full path of the directory I am currently in.

After learning and understanding these new commands, I can do the given tasks.

**#1 Run `ls` in the current folder. How many folders are there?**

```
tryhackme@linux1:~$ ls
access.log  folder1  folder2  folder3  folder4
```

As I can see, this command showed 4 folders.

**#2 One of those folders contains a file. Which folder is it?**

These folders are directories. I learned before that I can change directory with the command `cd`.
```
tryhackme@linux1:~$ cd <folder_name>
```
I went to each one, and returned to the previous path with the command `cd ..`, and I found the file in one of the folders.
```
tryhackme@linux1:~$ cd <folder_name>
tryhackme@linux1:~/<folder_name>$ ls
access.log  <file_2>
```

**#3 Use `cat` to read the file within this folder. What does it say?**
```
tryhackme@linux1:~/<folder_name>$ cat <file_name>
***********
```
Hooray! This task is completed!

---
### #Task4 - Let the Machine Do the Searching
Great! There are also two more commands: `find` and `grep`.

`find` - it searches for files and folders by their attributes (name, type, size, etc.).

`grep` - it also searches, but inside the files, looking for specific text.

**#1 Type cd /home/tryhackme to return to your home folder.**
```
tryhackme@linux1:~/<folder_name>$ cd /home/tryhackme
tryhackme@linux1:~$
```
There I returned to the home directory.

**#2 Run grep "THM" access.log to use grep to search the log file for us.**
```
grep "THM" access.log
13.127.130.212 - - [04/May/2021:08:35:26 +0000] "GET THM{******} lang=en HTTP/1.1" 404 360 "-" "Mozilla/5.0 (Windows  NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/77.0.3865.120 Safari/537.36"
```
The next step says to copy the **THM{}** output that has been found.

I submitted the flag and it was correct!

---
### #Task5 - Shell Operators (Combining Commands)
There are several characters (`&`, `&&`, `>`, `>>`) that help to combine the commands, which makes work more comfortable and efficient.

`&` - runs the command in the background, so I can keep working in the terminal while it is running.

`&&` - runs two commands one by one. The second one starts only when the first is finished.

`>` - sends the output of a command to a file. Be careful, because it overwrites everything in the file.

`>>` - does the same, but adds the output to the end of the file instead of overwriting.

For example:
```
tryhackme@linux1:~$ echo "TryHackMe" > thm
tryhackme@linux1:~$ cat thm
TryHackMe
tryhackme@linux1:~$ echo "Hello World" >> thm
tryhackme@linux1:~$ cat thm
TryHackMe
Hello World
tryhackme@linux1:~$ echo "Linux" > thm
tryhackme@linux1:~$ cat thm
Linux
```
The last `>` erased everything that was in the file, so only the word **Linux** is left.

---
### Conclusion
This room shows the basic Linux commands like how to check which user I am, move between folders, read files, search for things and combine commands.

Thanks for reading! I hope this walkthrough was useful and everything was clear!
