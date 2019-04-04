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
[demo@host-1-217 misc]$ mv let1.doc rpt1.doc
[demo@host-1-217 misc]$ mv let2.doc rpt2.doc
[demo@host-1-217 misc]$ mv let3.doc rpt3.doc
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
