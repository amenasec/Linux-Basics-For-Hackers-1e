<!---
  Name          : Chapter_4.md
  Project       : Linux Basics for Hackers 1e
  Description   : Solutions to chapter 4 exercise problems
  Creation Date : 06 September 2020
  Author        : amenasec
  Link          : https://github.com/amenasec
--->


# Chapter 4 Exercise Problems

### 1.
Install a new software package from the Kali repository.

---

````shell
root@kali:/home/kali# apt-get install synaptic
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following additional packages will be installed:
  libcairo-gobject-perl libcairo-perl libept1.6.0
  libextutils-depends-perl libextutils-pkgconfig-perl
  libglib-object-introspection-perl libglib-perl libgtk3-perl libxapian30
  pkg-config
Suggested packages:
  libfont-freetype-perl libxml-libxml-perl xapian-tools dwww menu
  deborphan apt-xapian-index software-properties-gtk
The following NEW packages will be installed:
  libcairo-gobject-perl libcairo-perl libept1.6.0
  libextutils-depends-perl libextutils-pkgconfig-perl
  libglib-object-introspection-perl libglib-perl libgtk3-perl libxapian30
  pkg-config synaptic
0 upgraded, 11 newly installed, 0 to remove and 491 not upgraded.
Need to get 3,932 kB of archives.
After this operation, 13.0 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://kali.download/kali kali-rolling/main amd64 libextutils-depends-perl all 0.8000-1 [18.9 kB]
Get:2 http://kali.download/kali kali-rolling/main amd64 pkg-config amd64 0.29.2-1 [65.1 kB]
Get:3 http://kali.download/kali kali-rolling/main amd64 libextutils-pkgconfig-perl all 1.16-1 [10.7 kB]
Get:4 http://kali.download/kali kali-rolling/main amd64 libcairo-perl amd64 1.107-1 [93.0 kB]
Get:5 http://kali.download/kali kali-rolling/main amd64 libglib-perl amd64 3:1.329.3-1 [351 kB]
Get:6 http://kali.download/kali kali-rolling/main amd64 libcairo-gobject-perl amd64 1.005-2+b1 [12.3 kB]
Get:7 http://kali.download/kali kali-rolling/main amd64 libept1.6.0 amd64 1.2+b1 [92.1 kB]
Get:8 http://kali.download/kali kali-rolling/main amd64 libglib-object-introspection-perl amd64 0.048-2 [68.4 kB]
Get:9 http://kali.download/kali kali-rolling/main amd64 libgtk3-perl all 0.037-1 [34.4 kB]
Get:10 http://kali.download/kali kali-rolling/main amd64 libxapian30 amd64 1.4.17-1 [1,089 kB]
Get:11 http://kali.download/kali kali-rolling/main amd64 synaptic amd64 0.90+nmu1 [2,096 kB]
Fetched 3,932 kB in 2s (1,643 kB/s)    
Selecting previously unselected package libextutils-depends-perl.
(Reading database ... 257971 files and directories currently installed.)
Preparing to unpack .../00-libextutils-depends-perl_0.8000-1_all.deb ...
Unpacking libextutils-depends-perl (0.8000-1) ...
Selecting previously unselected package pkg-config.
Preparing to unpack .../01-pkg-config_0.29.2-1_amd64.deb ...
Unpacking pkg-config (0.29.2-1) ...
Selecting previously unselected package libextutils-pkgconfig-perl.
Preparing to unpack .../02-libextutils-pkgconfig-perl_1.16-1_all.deb ...
Unpacking libextutils-pkgconfig-perl (1.16-1) ...
Selecting previously unselected package libcairo-perl.
Preparing to unpack .../03-libcairo-perl_1.107-1_amd64.deb ...
Unpacking libcairo-perl (1.107-1) ...
Selecting previously unselected package libglib-perl:amd64.
Preparing to unpack .../04-libglib-perl_3%3a1.329.3-1_amd64.deb ...
Unpacking libglib-perl:amd64 (3:1.329.3-1) ...
Selecting previously unselected package libcairo-gobject-perl.
Preparing to unpack .../05-libcairo-gobject-perl_1.005-2+b1_amd64.deb ...
Unpacking libcairo-gobject-perl (1.005-2+b1) ...
Selecting previously unselected package libept1.6.0:amd64.
Preparing to unpack .../06-libept1.6.0_1.2+b1_amd64.deb ...
Unpacking libept1.6.0:amd64 (1.2+b1) ...
Selecting previously unselected package libglib-object-introspection-perl.
Preparing to unpack .../07-libglib-object-introspection-perl_0.048-2_amd64.deb ...
Unpacking libglib-object-introspection-perl (0.048-2) ...
Selecting previously unselected package libgtk3-perl.
Preparing to unpack .../08-libgtk3-perl_0.037-1_all.deb ...
Unpacking libgtk3-perl (0.037-1) ...
Selecting previously unselected package libxapian30:amd64.
Preparing to unpack .../09-libxapian30_1.4.17-1_amd64.deb ...
Unpacking libxapian30:amd64 (1.4.17-1) ...
Selecting previously unselected package synaptic.
Preparing to unpack .../10-synaptic_0.90+nmu1_amd64.deb ...
Unpacking synaptic (0.90+nmu1) ...
Setting up libxapian30:amd64 (1.4.17-1) ...
Setting up libept1.6.0:amd64 (1.2+b1) ...
Setting up libextutils-depends-perl (0.8000-1) ...
Setting up pkg-config (0.29.2-1) ...
Setting up synaptic (0.90+nmu1) ...
Setting up libextutils-pkgconfig-perl (1.16-1) ...
Setting up libcairo-perl (1.107-1) ...
Setting up libglib-perl:amd64 (3:1.329.3-1) ...
Setting up libcairo-gobject-perl (1.005-2+b1) ...
Setting up libglib-object-introspection-perl (0.048-2) ...
Setting up libgtk3-perl (0.037-1) ...
Processing triggers for desktop-file-utils (0.26-1) ...
Processing triggers for mime-support (3.64) ...
Processing triggers for hicolor-icon-theme (0.17-2) ...
Processing triggers for libc-bin (2.30-8) ...
Processing triggers for man-db (2.9.3-2) ...
Processing triggers for kali-menu (2020.3.2) ...
````

---


### 2.
Remove that same software package.

---

````shell
root@kali:/home/kali# apt-get remove synaptic
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following packages were automatically installed and are no longer required:
  libept1.6.0 libxapian30
Use 'sudo apt autoremove' to remove them.
The following packages will be REMOVED:
  synaptic
0 upgraded, 0 newly installed, 1 to remove and 491 not upgraded.
After this operation, 8,031 kB disk space will be freed.
Do you want to continue? [Y/n] y
(Reading database ... 258481 files and directories currently installed.)
Removing synaptic (0.90+nmu1) ...
Processing triggers for desktop-file-utils (0.26-1) ...
Processing triggers for mime-support (3.64) ...
Processing triggers for hicolor-icon-theme (0.17-2) ...
Processing triggers for man-db (2.9.3-2) ...
Processing triggers for kali-menu (2020.3.2) ...
````

---


### 3.
Update your repository.

---

````shell
root@kali:/home/kali# apt-get update
Hit:1 http://kali.download/kali kali-rolling InRelease
Reading package lists... Done
````

---


### 4.
Upgrade your software packages.

---

````shell
root@kali:/home/kali# apt-get update
Hit:1 http://kali.download/kali kali-rolling InRelease
Reading package lists... Done
````

---


### 5.
Select a new piece of software from github and clone it to your system.

---

````shell

````

---
