### Question 1: Update demo account
```
[root@host-1-217 ~]# adduser demo
adduser: user 'demo' already exists
[root@host-1-217 ~]# passwd demo
Changing password for user demo.
New password:
BAD PASSWORD: The password is shorter than 8 characters
Retype new password:
passwd: all authentication tokens updated successfully.
```

### Question 2: Create a directory structure
[demo@host-1-217 ~]$ mkdir -p work/{progs,tutorial,misc} letters scripts

### Question 3: cp
Cp Usage is simple
cp <source> <destination>
If there were more than 1 source file, cp <source> <source> <source> <destination>
In this case, I used 
```
[demo@host-1-217 ~]$ cp /etc/group /etc/vimrc work/misc/
```
  
### Question 4: Relative move
So, simple
```
[demo@host-1-217 ~]$ cd work/misc
[demo@host-1-217 misc]$ mv vimrc ../progs
[demo@host-1-217 misc]$ ls ../progs
vimrc
```

### Question 6: cp
```
[demo@host-1-217 ~]$ echo file > bigfile
[demo@host-1-217 ~]$ cp bigfile work/tutorial/bigfile2 ../scripts/
[demo@host-1-217 ~]$ls ../scripts
bigfile2
```

### Question 7: tilde
echo ~$USERNAME show the home directory of $USERNAME
```
[demo@host-1-217 work]$ echo ~mysql
/var/lib/mysql
```

### Question 7: tilde
```
[demo@host-1-217 work]$ mkdir My\ Documents
```

BOOM! Finished intro2
