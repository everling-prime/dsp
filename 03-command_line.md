# Learn command line

Please follow and complete the free online [Command Line Crash Course
tutorial](https://web.archive.org/web/20160708171659/http://cli.learncodethehardway.org/book/) or [Codecademy's Learn the Command Line](https://www.codecademy.com/learn/learn-the-command-line). These are helpful tutorials. Each "chapter" focuses on a command. Type the commands you see in the _Do This_ section, and read the _You Learned This_ section. Move on to the next chapter. You should be able to go through these in a couple of hours.

---

### Q1.  Cheat Sheet of Commands  

Here's a list of items with which you should be familiar:  
* show current working directory path
* creating a directory
* deleting a directory
* creating a file using `touch` command
* deleting a file
* renaming a file
* listing hidden files
* copying a file from one directory to another

Make a cheat sheet for yourself: a list of at least **ten** commands and what they do.  (Use the 8 items above and add a couple of your own.)  

* `pwd`: show present working directory
* `mkdir`: create a directory
* `rmdir dir`: delete a directory
* `touch file`: create file
* `rm file`: delete file
* `mv file1 file2`: rename file1 to file2
* `ls -a`: list all files including hidden
* `cp file dir`: copy file to directory
* `cp -r dir1 dir2`: copy recursively the contents of dir1 to dir2
* `grep pattern file`: look for text matching the pattern in a file

---

### Q2.  List Files in Unix   

What do the following commands do:  
`ls`  
`ls -a`  
`ls -l`  
`ls -lh`  
`ls -lah`  
`ls -t`  
`ls -Glp`  

>
`ls`  List files  
`ls -a` List all files (including hidden files)  
`ls -l` List dir contents in long format  
`ls -lh`  List files in long format with readable file size  
`ls -lah`  List files in long format with readable file size including hidden files  
`ls -t` List files by timestamp  
`ls -Glp`  List in long format, inhibit display of group information, and append a type indicator  

---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

* `ls -d` Display only directories
* `ls -u` Display files by time last accessed
* `ls -R` Display subdirs
* `ls -q` Display nonprinting chars as ?
* `ls -t` Display by timestamp

---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

`xargs` allows you to run commands on the output of something. For example,  
> `find . -name '*.txt' | xargs grep 'string'`  

will find all the .txt files in the current directory, and search each one with `grep` for the given string

 

