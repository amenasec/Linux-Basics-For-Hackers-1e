<!---
  Name          : Chapter_7.md
  Project       : Linux Basics for Hackers 1e
  Description   : Solutions to chapter 7 exercise problems
  Creation Date : 07 September 2020
  Author        : amenasec
  Link          : https://github.com/amenasec
--->


# Chapter 7 Exercise Problems

### 1.
View all of your environment variables with the `more` command.

---

````shell
kali@kali:~$ set | more
BASH=/bin/bash
BASHOPTS=checkwinsize:cmdhist:complete_fullquote:expand_aliases:extglob:ext
quote:force_fignore:globasciiranges:histappend:interactive_comments:progcom
p:promptvars:sourcepath
BASH_ALIASES=()
BASH_ARGC=([0]="0")
BASH_ARGV=()
--snip--
}
````

---


### 2.
Use the `echo` command to view the `HOSTNAME` variable.

---

````shell
kali@kali:~$ echo $HOSTNAME
kali
````

---


### 3.
Find a method to change the slash (`/`) to a backslash ('\') in the faux Microsoft `cmd PS1` example (see Listing 7.2).

---

````shell
kali@kali:~$ PS1='C:\\\W> '
C:\~> cd /home
C:\home>
````

---


### 4.
Create a variable names `MYNEWVARIABLE` and put your name in it.

---

````shell
kali@kali:/home$ MYNEWVARIABLE=amenasec
````

---


### 5.
Use `echo` to view the contents of `MYNEWVARIABLE`.

---

````shell
kali@kali:/home$ echo $MYNEWVARIABLE
amenasec
````

---


### 6.
Export `MYNEWVARIABLE` so that it's available in all environments.

---

````shell
kali@kali:/home$ export MYNEWVARIABLE
````

---


### 7.
Use the echo command to view the contents of the `PATH` variable.

---

````shell
kali@kali:/home$ echo $PATH
/usr/local/bin:/usr/bin:/bin:/usr/local/games:/usr/games
````

---


### 8.
Add your home directory to the `PATH` variable so that any binaries in your home directory can be used in any directory.

---

````shell
kali@kali:/home$ PATH=$PATH:/home/kali
````

---


### 9.
Change your `PS1` variable to "World's Greatest Hacker:".

---

````shell
kali@kali:/home$ PS1="World's Greatest Hacker: "
World's Greatest Hacker:
````

---
