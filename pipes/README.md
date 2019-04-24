## Pipes

### Question 1: Update Account
Update account to create club_members, names and s1 in home directory of user demo.

### Question 2: sort
Using cat create a pipe that will concatenate the two files club_members and names, <br/>sort them and send the output to the file s1. <br/>
```bash
[demo@host-1-9 ~]$ cat club_members names | sort > s1
```

### Question 3: reverse sort
Using cat create a pipe that will concatenate the two files club_members and names, <br/>sort them in *reverse order* and send the output to the file s2. <br/>
```
[demo@host-1-9 ~]$ cat club_members names | sort -r > s2
```

### Question 4: sort on a field
Sort the file club_members numerically by meetings attended (this is the last field). Send the output to file s3
```bash
[demo@host-1-9 ~]$ cat club_members | sort -k5 -n > s3
```

### Question 5: sort with field separator
Sort the /etc/passwd numerically by user id numbers (third field) in ascending order. <br/>
You may wish to use the -t option here. Send the output to file s4
```bash
[demo@host-1-9 ~]$ cat /etc/passwd | sort -k 3 -t : -n > s4
```

### Question 6: using grep
Use grep on /usr/share/dict/words to find the first word that contains the three letter <br/>sequence wta
```bash
[demo@host-1-9 ~]$ cat /usr/share/dict/words | grep wta
```

### Question 7: count with grep
Use grep piped through wc on file /usr/share/dict/words to find the number of words that contain the letter x.
```bash
[demo@host-1-9 ~]$ cat /usr/share/dict/words | grep x | wc
```

### Question 8: negative grep
Use grep to find all lines in /etc/passwd that do not have nologin one the line. Make grep include the line <br/>numbers of the matching lines and send the output to file s5
```bash
[demo@host-1-9 ~]$ cat /etc/passwd | grep -v nologin
```

### Question 9: grep and ls
Use ls -l and grep to find all the files in the directory /etc that were last modified in August <br/>(hint: try looking for the case sensitive string "Aug"). Send this list to s6. 
```bash
[demo@host-1-9 ~]$ ls -l /etc | grep "Aug"
```

### Question 10: ls grep and sort
Use ls -l and grep and sort to find all the files in /etc that were last modified in Jun. Sort this list in descending <br/>order of size and then alphabetically by name (so 2 files with the same size will appear in alphabetic order). <br/>Send the output to s7. Sorting using other techniques will probably not get the same answer...
```bash
[demo@host-1-9 ~]$ ls -l /etc | grep "Jun" | sort -n -k5
```

### Question 11: find root files
Find all the files and directories in /var (including subdirectories) that are owned by user root. <br/>Send the list of full path names to s8. 
```bash
[demo@host-1-9 ~]$ find /var -group root
```

### Question 12: find .conf files
Find all the files in /etc (including subdirectories) end .conf Send the list of full path names to s9. <br/>
Your find command may produce "Permission Denied" errors during this search. This will have no effect on the answer, and this error can be safely ignored for this question. 
```bash
[demo@host-1-9 ~]$ find /etc -name *.conf
```

### Question 13: find new files
Find all the files and directories in the demo directory that are newer than s1. Send the output of the command to<br/> /var/tmp/t1 (don't send it to the demo directory). The names of the files should appear as full names. For example,<br/> the file "s5" would appear as "/home/demo/s5". The "/home/demo", if it appears in the output, should not have a trailing "/".<br/> The secret to avoiding the trailing slash is to use "/home/demo" not "/home/demo/" in the find command. 
```bash
[demo@host-1-9 ~]$ find . -cnewer s1
```

### Question 14: list large files
Find all the files in the directory directory /etc/ and its subdirectories that are larger than 1 megabyte <br/>(which you can assume is 2048 blocks of 512 bytes). Send the output to s10. 
```bash
[demo@host-1-9 ~]$ find /etc -type f -size +1M
```

### Question 15: small xsl files
Create a directory called smallc in /home/demo. Copy into it all the file that begin with s from /usr/include<br/> that are smaller or equal to 12K. You may find these instructions on the use of [find](http://www.devdaily.com/unix/edu/examples/find.shtml) from Developer's Daily useful.
```bash
[demo@host-1-9 ~]$ find /usr/include -name 's*' -size -25 -exec cp {} /home/demo/smallc
```

## Reference Links
https://alvinalexander.com/unix/edu/examples/find.shtml
https://stackoverflow.com/questions/17368872/how-to-move-or-copy-files-listed-by-find-command-in-unix


















