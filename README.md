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
SO, the answer is 7

