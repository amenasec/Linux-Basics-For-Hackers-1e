<!---
  Name          : Chapter_3.md
  Project       : Linux Basics for Hackers 1e
  Description   : Solutions to chapter 3 exercise problems
  Creation Date : 06 September 2020
  Author        : amenasec
  Link          : https://github.com/amenasec
--->


# Chapter 3 Exercise Problems

### 1.
Find information on your active network interfaces.

---

````shell
kali@kali:~$ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000
    link/ether 00:0c:29:f6:8e:f2 brd ff:ff:ff:ff:ff:ff
    inet 172.16.194.131/24 brd 172.16.194.255 scope global dynamic noprefixroute eth0
       valid_lft 1539sec preferred_lft 1539sec
    inet6 fe80::20c:29ff:fef6:8ef2/64 scope link noprefixroute
       valid_lft forever preferred_lft forever
````

---


### 2.
Change the IP address on `eth0` to `192.168.1.1.`

---

````shell
kali@kali:~$ sudo ip addr add 192.168.1.1 dev eth0
kali@kali:~$ sudo ip addr del 172.16.194.131/32 dev eth0
kali@kali:~$ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000                                                 
    link/ether 00:0c:29:f6:8e:f2 brd ff:ff:ff:ff:ff:ff
    inet 192.168.1.1/32 scope global eth0
       valid_lft forever preferred_lft forever
    inet6 fe80::20c:29ff:fef6:8ef2/64 scope link noprefixroute
       valid_lft forever preferred_lft forever
````

---


### 3.
Change your hardware address on `eth0`.

---

````shell
kali@kali:~$ sudo ip maddr add 11:22:33:44:55:66 dev eth0
kali@kali:~$ ip maddr
1:      lo
        inet  224.0.0.1
        inet6 ff02::1
        inet6 ff01::1
2:      eth0
        link  01:00:5e:00:00:01
        link  33:33:00:00:00:01
        link  33:33:ff:f6:8e:f2
        link  11:22:33:44:55:66 static
        inet  224.0.0.1
        inet6 ff02::1:fff6:8ef2
        inet6 ff02::1
        inet6 ff01::1
````

---


### 4.
Check whether you have any available wireless interfaces active.

---

````shell
kali@kali:~$ sudo iwconfig
lo        no wireless extensions.

eth0      no wireless extensions.
````

---


### 5.
Reset your IP address to a DHCP-assigned address.

---

````shell
kali@kali:~$ sudo dhclient eth0
kali@kali:~$ sudo ip addr del 192.168.1.1/32 dev eth0
kali@kali:~$ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000                                                 
    link/ether 00:0c:29:f6:8e:f2 brd ff:ff:ff:ff:ff:ff
    inet 172.16.194.131/24 brd 172.16.194.255 scope global dynamic eth0
       valid_lft 1791sec preferred_lft 1791sec
    inet6 fe80::20c:29ff:fef6:8ef2/64 scope link noprefixroute
       valid_lft forever preferred_lft forever
````

---


### 6.
Find the nameserver and email server of your favorite website.

---

````shell
kali@kali:~$ dig github.com ns
--snip--
;; QUESTION SECTION:
;github.com.                    IN      NS

;; ANSWER SECTION:
github.com.             5       IN      NS      ns-1707.awsdns-21.co.uk.
github.com.             5       IN      NS      ns-421.awsdns-52.com.
github.com.             5       IN      NS      ns-520.awsdns-01.net.
github.com.             5       IN      NS      dns1.p08.nsone.net.
github.com.             5       IN      NS      dns2.p08.nsone.net.
github.com.             5       IN      NS      dns3.p08.nsone.net.
github.com.             5       IN      NS      dns4.p08.nsone.net.
github.com.             5       IN      NS      ns-1283.awsdns-32.org.

;; ADDITIONAL SECTION:
dns1.p08.nsone.net.     5       IN      A       198.51.44.8
dns2.p08.nsone.net.     5       IN      A       198.51.45.8
dns3.p08.nsone.net.     5       IN      A       198.51.44.72
dns4.p08.nsone.net.     5       IN      A       198.51.45.72
ns-1283.awsdns-32.org.  5       IN      A       205.251.197.3
ns-1283.awsdns-32.org.  5       IN      AAAA    2600:9000:5305:300::1
ns-1707.awsdns-21.co.uk. 5      IN      A       205.251.198.171
ns-1707.awsdns-21.co.uk. 5      IN      AAAA    2600:9000:5306:ab00::1
ns-421.awsdns-52.com.   5       IN      A       205.251.193.165
ns-421.awsdns-52.com.   5       IN      AAAA    2600:9000:5301:a500::1
ns-520.awsdns-01.net.   5       IN      A       205.251.194.8
ns-520.awsdns-01.net.   5       IN      AAAA    2600:9000:5302:800::1
--snip--
````

---


### 7.
Add Google's DNS server to your `/etc/resolv.conf` file so your system refers to that server when it can't resolve a domain name query with your local DNS server.

---

````shell
root@kali:/home/kali# echo "nameserver 8.8.8.8" >> /etc/resolv.conf
````

---
