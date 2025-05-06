---
layout: page
title: 💻 Command-Line Cheat Sheet
nav_exclude: true
---

# 💻 Command-Line Cheat Sheet
{:.no_toc}

---

The DSMLP servers use Linux. As such, when interacting with them, all of the command-line commands you use should be Linux-specific (which, for the most part, also work on macOS). Many of the key commands you'll need to know are summarized below.

## Basics

| Command | Description | Example |
| --- | --- | --- | 
| `man` | Shows the `man`ual for a command. This can be helpful for seeing how to run a command or what flags (parameters) a command takes. | `man cp` shows the manual for the `cp` (copy) command. |
| `pwd` | Displays your `p`resent `w`orking `d`irectory. | `pwd`, when run immediately after opening my Terminal, shows `/Users/surajrampure`.  |
| `ls` | `l`i`s`ts all files in the current directory. | `ls` <br> `ls -a` (also shows all of the hidden files and folders in the current directory (like `.gitignore`)) |
| `mkdir` | `m`a`k`es a new `dir`ectory (folder) with the name you specify. | `mkdir hello` creates a folder in your present working directory named `hello`. Verify this using `ls`. |
| `cd` | `c`hanges your current `d`irectory to be the one specified. | `cd hello` enters the directory `hello`, if it exists in the present working directory. `cd` by itself always returns you to your "home" directory. |
| `touch` | Creates an empty file with the specified name. | `touch ucsd.txt` creates a file named `ucsd.txt` in the present working directory. |
| `cat` | Shows the contents of a file. | `cat hello.txt` will display all of `hello.txt`. |
| `mv` | `m`o`v`es a file to a specified location. | `mv ucsd.txt ../hello.txt` moves a file from the present working directory to the parent directory. <br> **Note: In Linux, `.` represents the current directory and `..` represents the parent directory.** |
| `cp` | `c`o`p`ies a file from one location to another. | `cp hello.txt ../hey.txt` makes a copy of the contents in the file `hello.txt` and saves it in the file `hey.txt`, stored in the parent directory of the present working directory. <br> **Note:** To copy a folder, use the `-r` flag, which stands for "recursive." |

To verify that you've synthesized the above information, answer the following questions: 
- **What does `cd ..` do?**
- **What does `ls ../hello` do?**

## File Editing

| Command | Description | Example |
| --- | --- | --- |
| `vim` | A command line-based text editor. | `vim hello.txt` opens `hello.txt` in `vim`. |
| `emacs` | Another command line-based text editor. | `emacs hello.txt` opens `hello.txt` in `emacs`.|


## Servers and Networks

| Command | Description | Example |
| --- | --- | --- |
| `ssh` | Used to access servers (amongst other things). | `ssh srampure@dsmlp-login.ucsd.edu` is how Suraj accesses DSMLP. |
| `scp` / `sftp` | Allows you to move files between your local machine and a remote server (essentially `ssh` + `cp`). | `scp dog.txt srampure@dsmlp-login.ucsd.edu:test.txt` copies the file `dog.txt` from your local machine to Suraj's DSMLP drive (replace with your own username). See [DSMLP documentation](https://support.ucsd.edu/services?id=kb_article_view&sysparm_article=KB0032277&sys_kb_id=a8457b3787451558947a0fa8cebb352d) for more.
| `wget` | Downloads the contents of a webpage. | `wget https://raw.githubusercontent.com/ericmichael/cooltxt/master/cool.txt` creates a new file called `cool.txt` with the contents of the aforementioned URL. |


## Other

| Command | Description |
| --- | --- |
| `clear` or `ctrl + l` | Clears the Terminal window. |
| `history` | Shows the commands you've entered in the past. |
| `ctrl + r` | Allows you to search your command history to easily find a command you entered in the past. |
| `screen`  | Allows you to run tasks in the background. See [here](https://www.geeksforgeeks.org/screen-command-in-linux-with-examples/) for more details. |
| `git` | See usage reference [here](https://docs.github.com/en/get-started/quickstart/set-up-git). |
| `grep` | Helps you quickly search text (both individual documents and folders). The general pattern is `grep -inr <keyword> <file_path>`. <br> For example, `grep -inr dog hello.txt` will display all lines in which `'dog'` occurred in `hello.txt`. |
| `find` | Helps you quickly find a file using regex. For example, `find <path> -iname <regex>`. |
| `htop` | Shows you all of the processes currently running on your server and the amount of resources (e.g. CPU and memory) that you're using. |

<center>

<img src="../assets/images/fire.png" width="30%"><br>

(<a href="https://www.instagram.com/p/8N8J8wRgPq/?utm_source=ig_web_copy_link">source</a>)

</center>

If you have any feedback for this page, let us know!