### Question 2: Wild copy
We have to copy wild card files(i.e, all files that match with a condition)
cp file (copy that match with name "file")
cp file* (copy that starts with name "file")
cp *file* (copy that includes name "file")
* is called wildcards

```
[demo@host-1-217 ~]$ touch file1 1file
[demo@host-1-217 ~]$ cp *file* work
[demo@host-1-217 ~]$ ls work
1file  bigfile  file1  misc  progs  tutorial  yearfile2
```
In this case, I used touch to create blank files

### Question 3: Duplicate thismonth
```
[demo@host-1-217 ~]$ echo APril > thismonth
[demo@host-1-217 ~]$ cp thismonth letters/let1.doc
[demo@host-1-217 ~]$ cd letters/
[demo@host-1-217 letters]$ cp let1.doc let2.doc
[demo@host-1-217 letters]$ cp let1.doc let3.doc
[demo@host-1-217 letters]$ ls
let1.doc  let2.doc  let3.doc
```

### Question 4: Copy and Rename

> The question mark (?) is used as a wildcard character in shell commands 
> to represent exactly one character, which can be any single character. Thus, two question 
> marks in succession would represent any two characters in succession, 
> and three question marks in succession would represent any string consisting of three characters. 

More [info](http://www.linfo.org/wildcard.html)

```
[demo@host-1-217 letters]$ cp let?.doc ../work/misc
[demo@host-1-217 letters]$ cd ../work/misc
[demo@host-1-217 misc]$ ls
group  let1.doc  let2.doc  let3.doc
```
### Question 5: Square Brackets

Square Brackets wildcards is called range wildcards.
For example, in `cp [sv]*`, it will copy a file that start with s or v 
```
[demo@host-1-217 ~]$ cd work/misc
[demo@host-1-217 misc]$ ls
group  rpt1.doc  rpt2.doc  rpt3.doc
[demo@host-1-217 misc]$ mv *[23]* ~/scripts/
[demo@host-1-217 misc]$ ls ~/scripts/
bigfile2  rpt2.doc  rpt3.doc
```
### Question 6: rm
rm -i always ask us to delete or not after executing the commands
```
[demo@host-1-217 work]$ cd ../scripts/
[demo@host-1-217 scripts]$ rm -i r*
rm: remove regular file  Ç rpt2.doc Ç ? yes
rm: remove regular file  Ç rpt3.doc Ç ? yes
```

### Question 7: Hard Link
A hard link is merely an additional name for an existing file on Linux or other 
Unix-like operating systems.[Read More](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=13&cad=rja&uact=8&ved=2ahUKEwjM59H6vbXhAhVSjeYKHRv2DD0QFjAMegQIABAB&url=https%3A%2F%2Fmedium.com%2F%40wendymayorgasegura%2Fwhat-is-the-difference-between-a-hard-link-and-a-symbolic-link-8c0493041b62&usg=AOvVaw0YU_kFtS1kh6Itd8za5rl5)

```
[demo@host-1-217 ~]$ ln bigfile biglink
[demo@host-1-217 ~]$ file biglink
biglink: ASCII text
[demo@host-1-217 ~]$ cat biglink
file
[demo@host-1-217 ~]$ cat bigfile
file
[demo@host-1-217 ~]$ ls -l
total 20
-rw-r--r--. 1 demo tutorial    0 Apr  4 03:27 1file
-rw-r--r--. 2 demo tutorial    5 Apr  4 03:16 bigfile
```

### Question 8: Soft link
```
[demo@host-1-217 ~]$ ln -s -r ~/thismonth work/progs/mylink
```

### Question 9: Soft link - absolute
Absolute link needs full path
```
[demo@host-1-217 ~]$ `pwd`
bash: /home/demo: Is a directory
[demo@host-1-217 ~]$ ls `pwd`
1file  bigfile  file1  gordon  Gordon  letters  My Documents  scripts  thismonth  thisyear  work  yearfile2
[demo@host-1-217 ~]$ ls `pwd`/work
1file  bigfile  file1  misc  progs  tutorial  yearfile2
[demo@host-1-217 ~]$ ln -s `pwd`/thismonth work/progs/mylink2
```
