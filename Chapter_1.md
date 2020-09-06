<!---
  Name          : Chapter_1.md
  Project       : Linux Basics for Hackers 1e
  Description   : Solutions to chapter 1 exercise problems
  Creation Date : 06 September 2020
  Author        : amenasec
  Link          : https://github.com/amenasec
--->


# Chapter 1 Exercise Problems

### 1
Use the `ls` command from the root (`/`) directory to explore the directory structure of Linux. Move to each of the directories with the `cd` command and run `pwd` to verify where you are in the directory structure.

---

````shell
root@kali:/# ls -l
total 68
lrwxrwxrwx   1 root root     7 Sep  6 12:30 bin -> usr/bin
drwxr-xr-x   3 root root  4096 Sep  6 12:41 boot
drwxr-xr-x  18 root root  3420 Sep  6 13:12 dev
drwxr-xr-x 157 root root 12288 Sep  6 13:02 etc
drwxr-xr-x   3 root root  4096 Sep  6 12:40 home
lrwxrwxrwx   1 root root    33 Sep  6 12:30 initrd.img -> boot/initrd.img-5.7.0-kali1-amd64
lrwxrwxrwx   1 root root    33 Sep  6 12:30 initrd.img.old -> boot/initrd.img-5.7.0-kali1-amd64
lrwxrwxrwx   1 root root     7 Sep  6 12:30 lib -> usr/lib
lrwxrwxrwx   1 root root     9 Sep  6 12:30 lib32 -> usr/lib32
lrwxrwxrwx   1 root root     9 Sep  6 12:30 lib64 -> usr/lib64
lrwxrwxrwx   1 root root    10 Sep  6 12:30 libx32 -> usr/libx32
drwx------   2 root root 16384 Sep  6 12:30 lost+found
drwxr-xr-x   3 root root  4096 Sep  6 12:30 media
drwxr-xr-x   2 root root  4096 Sep  6 12:30 mnt
drwxr-xr-x   2 root root  4096 Sep  6 12:30 opt
dr-xr-xr-x 220 root root     0 Sep  6 12:43 proc
drwx------   3 root root  4096 Sep  6 12:43 root
drwxr-xr-x  34 root root   820 Sep  6 12:48 run
lrwxrwxrwx   1 root root     8 Sep  6 12:30 sbin -> usr/sbin
drwxr-xr-x   3 root root  4096 Sep  6 12:39 srv
dr-xr-xr-x  13 root root     0 Sep  6 12:43 sys
drwxrwxrwt  15 root root  4096 Sep  6 13:18 tmp
drwxr-xr-x  14 root root  4096 Sep  6 12:32 usr
drwxr-xr-x  12 root root  4096 Sep  6 12:32 var
lrwxrwxrwx   1 root root    30 Sep  6 12:30 vmlinuz -> boot/vmlinuz-5.7.0-kali1-amd64
lrwxrwxrwx   1 root root    30 Sep  6 12:30 vmlinuz.old -> boot/vmlinuz-5.7.0-kali1-amd64
root@kali:/# cd boot/
root@kali:/boot# pwd
/boot
root@kali:/boot# cd /dev/
root@kali:/dev# pwd
/dev
root@kali:/dev# cd /etc/
root@kali:/etc# pwd
/etc
root@kali:/etc# cd /home/
root@kali:/home# pwd
/home
root@kali:/home# cd /lost+found/
root@kali:/lost+found# pwd
/lost+found
root@kali:/lost+found# cd /media/
root@kali:/media# pwd
/media
root@kali:/media# cd /mnt/
root@kali:/mnt# pwd
/mnt
root@kali:/mnt# cd /opt/
root@kali:/opt# pwd
/opt
root@kali:/opt# cd /proc/
root@kali:/proc# pwd
/proc
root@kali:/proc# cd /root/
root@kali:~# pwd
/root
root@kali:~# cd /run/
root@kali:/run# pwd
/run
root@kali:/run# cd /srv/
root@kali:/srv# pwd
/srv
root@kali:/srv# cd /sys/
root@kali:/sys# pwd
/sys
root@kali:/sys# cd /tmp/
root@kali:/tmp# pwd
/tmp
root@kali:/tmp# cd /usr/
root@kali:/usr# pwd
/usr
root@kali:/usr# cd /var/
root@kali:/var# pwd
/var
````

---


### 2
Use the `whoami` command to verify which user you are logged in as.

---

````shell
root@kali:/var# whoami
root
````

---


### 3
Use the `locate` command to find wordlists that can be used for password cracking.

---

````shell
root@kali:/var# locate wordlists
/usr/bin/wordlists
/usr/lib/python3/dist-packages/theHarvester/wordlists
/usr/share/wordlists
/usr/share/amass/wordlists
/usr/share/amass/wordlists/all.txt
/usr/share/amass/wordlists/bitquark_subdomains_top100K.txt
/usr/share/amass/wordlists/deepmagic.com_top500prefixes.txt
--*snip*--
/var/lib/dpkg/info/wordlists.prerm
````

---


### 4
Use the `cat` command to create a new file and then append to that file. Keep in mind that `>` redirects input to a file and `>>` appends to a file.

---



---


### 5
Create a new directory called `hackerdirectory` and create a new file that directory named `hackedfile`. Now copy that file to your `/root` directory and rename it `secretfile`.

---



---
