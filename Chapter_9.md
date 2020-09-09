<!---
  Name          : Chapter_9.md
  Project       : Linux Basics for Hackers 1e
  Description   : Solutions to chapter 9 exercise problems
  Creation Date : 07 September 2020
  Author        : amenasec
  Link          : https://github.com/amenasec
--->


# Chapter 9 Exercise Problems

### 1.
Create three scripts to combine, similar to what we did in Chapter 8. Name them `Linux4Hackers1`, `Linux4Hackers2`, and `Linux4Hackers3`.

---

````shell
kali@kali:~$ echo $'#! /bin/bash\n\n echo "This is 1"' > Linux4Hackers1
kali@kali:~$ echo $'#! /bin/bash\n\n echo "This is 22"' > Linux4Hackers2
kali@kali:~$ echo $'#! /bin/bash\n\n echo "This is 333"' > Linux4Hackers3
````

---


### 2.
Create a tarball from these three files. Name the tarball `L4H`. Note how the size of the sum of the three files changes when they are tarred together.

---

````shell
kali@kali:~$ tar -cf L4H Linux4Hackers1 Linux4Hackers2 Linux4Hackers3
kali@kali:~$ ls -l Linux4Hackers? L4H
-rw-r--r-- 1 kali kali 10240 Sep  7 23:19 L4H
-rw-r--r-- 1 kali kali    32 Sep  7 23:16 Linux4Hackers1
-rw-r--r-- 1 kali kali    33 Sep  7 23:16 Linux4Hackers2
-rw-r--r-- 1 kali kali    34 Sep  7 23:16 Linux4Hackers3
````

---


### 3.
Compress the `L4H` tarball with `gzip`. Note how the size of the file changes. Investigate how you can control overwriting existing files. Now uncompress the `L4H` file.

---

````shell
kali@kali:~$ gzip L4H
kali@kali:~$ ls -l L4H.gz
-rw-r--r-- 1 kali kali 212 Sep  7 23:19 L4H.gz
kali@kali:~$ gunzip L4H.gz
````

---


### 4.
Repeat Exercise `3` with both `bzip2` and `compress`.

---

````shell
kali@kali:~$ bzip2 L4H
kali@kali:~$ ls -l L4H.bz2
-rw-r--r-- 1 kali kali 224 Sep  7 23:19 L4H.bz2
kali@kali:~$ bunzip2 L4H.bz2
````

````shell
kali@kali:~$ compress L4H
kali@kali:~$ ls -l L4H.Z
-rw-r--r-- 1 kali kali 416 Sep  7 23:19 L4H.Z
kali@kali:~$ uncompress L4H.Z
````

---


### 5.
Make a physical, bit-by-bit copy of one of your flash drives using the `dd` command.

---

````shell
kali@kali:~$ dd if=/dev/sdb of=/home/kali/flashcopy
--snip--
````

---
