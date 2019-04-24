# Pipes

## Question 1: Update Account
Update account to create club_members, names and s1 in home directory of user demo.

## Question 2: sort
Using cat create a pipe that will concatenate the two files club_members and names, <br/>sort them and send the output to the file s1. <br/>
```bash
[demo@host-1-9 ~]$ cat club_members names | sort > s1
```

## Question 3: reverse sort
Using cat create a pipe that will concatenate the two files club_members and names, <br/>sort them in *reverse order* and send the output to the file s2. <br/>

> [demo@host-1-9 ~]$ cat club_members names | sort -r > s1
