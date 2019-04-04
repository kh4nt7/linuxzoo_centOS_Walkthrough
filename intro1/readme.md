## Linux Zoo Walkthrough

### Question 1 : cal
cal takes 2 arguments [month] [year]

```bash
[root@host-1-185 demo]# cal 12 2002
    December 2002
Mo Tu We Th Fr Sa Su
                   1
 2  3  4  5  6  7  8
 9 10 11 12 13 14 15
16 17 18 19 20 21 22
23 24 25 26 27 28 29
30 31
```

It output that so, the answer is "Tu"

### Question 3: cal year
```
[root@host-1-185 demo]# cal 2005 > yearfile
```
Bingo!

### Question 4: ls
To get the list including "." and "..", we have to execute ls -al<br/>
where flag "a" shows all files and  "l" shows us long listing format<br/>
I used ls -al piped with wc -l</br>
You can read about info at man wc (i.e man cmd_name)
```
[root@host-1-185 demo]# ls -a | wc -l
7
```
So, the answer is 7

### Question 5: file size
```
[root@host-1-185 demo]# find -type f -printf "%s \\0" | sort -n -z | tr '\0' '\n' | head -n 1
18
```
sry I am lazy to count manually :P

### Question 6: append
simply execute cal to print current month<br/>
And redirect output with ">" and append it with ">>"

```
[root@host-1-225 demo]# cal > thismonth | date >> thismonth
```

### Question 7: copy
just use cp yearfile yearfile2 yearfile3

### Question 8: moving
mv is used when we need to move a file from one place to another<br/>
it is also used in renaming a file
```
[root@host-1-225 demo]# mv yearfile3 thisyear
```

### Question 9: deleting
```
[root@host-1-225 demo]# rm yearfile
```

### Question 10: big concat
```
[root@host-1-217 ~]# cat thismonth yearfile2 thisyear > bigfile
[root@host-1-217 ~]# cat bigfile
April
2018
2019
```
