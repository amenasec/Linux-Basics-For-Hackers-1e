<!---
  Name          : Chapter_5.md
  Project       : Linux Basics for Hackers 1e
  Description   : Solutions to chapter 5 exercise problems
  Creation Date : 06 September 2020
  Author        : amenasec
  Link          : https://github.com/amenasec
--->


# Chapter 5 Exercise Problems

### 1.
Select a directory and run a long listing on it. Note the permissions on the files and directory.

---

````shell
kali@kali:~$ ls -l ~
total 40
drwxr-xr-x 2 kali kali 4096 Sep  6 12:48 Desktop
drwxr-xr-x 2 kali kali 4096 Sep  6 12:48 Documents
drwxr-xr-x 2 kali kali 4096 Sep  6 12:48 Downloads
drwxr-xr-x 2 root root 4096 Sep  6 13:53 hackerdirectory
drwxr-xr-x 2 kali kali 4096 Sep  6 12:48 Music
-rw-r--r-- 1 kali kali   43 Sep  6 13:41 newfile
drwxr-xr-x 2 kali kali 4096 Sep  6 12:48 Pictures
drwxr-xr-x 2 kali kali 4096 Sep  6 12:48 Public
drwxr-xr-x 2 kali kali 4096 Sep  6 12:48 Templates
drwxr-xr-x 2 kali kali 4096 Sep  6 12:48 Videos
````

---


### 2.
Select a file you don't have permission to execute and give yourself execute permissions using the `chmod` command. Try using both the numerical method (`777`) and the UGO method.

---

````shell
kali@kali:~$ chmod 777 ~/newfile
kali@kali:~$ ls -l ~/newfile
-rwxrwxrwx 1 kali kali 43 Sep  6 13:41 /home/kali/newfile

kali@kali:~$ chmod g-w,o-wx ~/newfile
kali@kali:~$ ls -l ~/newfile
-rwxr-xr-- 1 kali kali 43 Sep  6 13:41 /home/kali/newfile
````

---


### 3.
Choose another file and change its ownership using `chown`.

---

````shell
root@kali:/home/kali# chown root ./newfile
root@kali:/home/kali# ls -l ./newfile
-rwxrwxrwx 1 root kali 43 Sep  6 13:41 ./newfile
````

---


### 4.
Use the `find` command to find all files with the `SGID` bit set.

---

````shell
root@kali:/home/kali# find / -perm -2000
/etc/ppp/peers
/etc/chatscripts
/var/local
/var/log/mysql
/var/log/journal
/var/log/journal/e9b560b98f414f91aa99c7bb7c6945de
/var/mail
/run/postgresql
/run/log/journal
/usr/lib/x86_64-linux-gnu/utempter/utempter
/usr/lib/xorg/Xorg.wrap
/usr/bin/expiry
/usr/bin/mlocate
/usr/bin/crontab
/usr/bin/wall
/usr/bin/dotlockfile
/usr/bin/ssh-agent
/usr/bin/chage
/usr/bin/bsd-write
/usr/sbin/unix_chkpwd
/usr/local/lib/python2.7
/usr/local/lib/python2.7/site-packages
/usr/local/lib/python2.7/dist-packages
/usr/local/lib/python3.8
/usr/local/lib/python3.8/dist-packages
/usr/local/share/fonts
````

---
