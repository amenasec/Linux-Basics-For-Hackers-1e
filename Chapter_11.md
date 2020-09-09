<!---
  Name          : Chapter_11.md
  Project       : Linux Basics for Hackers 1e
  Description   : Solutions to chapter 11 exercise problems
  Creation Date : 07 September 2020
  Author        : amenasec
  Link          : https://github.com/amenasec
--->


# Chapter 11 Exercise Problems

### 1.
Use the `locate` command to find all the `rsyslog` files.

---

````shell
kali@kali:~$ locate rsyslog
/etc/rsyslog.conf
/etc/rsyslog.d
/etc/init.d/rsyslog
/etc/logcheck/ignore.d.server/rsyslog
/etc/logrotate.d/rsyslog
/etc/rc0.d/K01rsyslog
/etc/rc1.d/K01rsyslog
/etc/rc2.d/S01rsyslog
/etc/rc3.d/S01rsyslog
/etc/rc4.d/S01rsyslog
/etc/rc5.d/S01rsyslog
/etc/rc6.d/K01rsyslog
/etc/systemd/system/multi-user.target.wants/rsyslog.service
/usr/lib/rsyslog
/usr/lib/rsyslog/rsyslog-rotate
/usr/lib/systemd/system/rsyslog.service
/usr/lib/x86_64-linux-gnu/rsyslog
/usr/lib/x86_64-linux-gnu/rsyslog/fmhash.so
/usr/lib/x86_64-linux-gnu/rsyslog/imfile.so
/usr/lib/x86_64-linux-gnu/rsyslog/imjournal.so
/usr/lib/x86_64-linux-gnu/rsyslog/imklog.so
/usr/lib/x86_64-linux-gnu/rsyslog/imkmsg.so
/usr/lib/x86_64-linux-gnu/rsyslog/immark.so
/usr/lib/x86_64-linux-gnu/rsyslog/impstats.so
/usr/lib/x86_64-linux-gnu/rsyslog/imptcp.so
/usr/lib/x86_64-linux-gnu/rsyslog/imtcp.so
/usr/lib/x86_64-linux-gnu/rsyslog/imudp.so
/usr/lib/x86_64-linux-gnu/rsyslog/imuxsock.so
/usr/lib/x86_64-linux-gnu/rsyslog/lmnet.so
/usr/lib/x86_64-linux-gnu/rsyslog/lmnetstrms.so
/usr/lib/x86_64-linux-gnu/rsyslog/lmnsd_ptcp.so
/usr/lib/x86_64-linux-gnu/rsyslog/lmregexp.so
/usr/lib/x86_64-linux-gnu/rsyslog/lmtcpclt.so
/usr/lib/x86_64-linux-gnu/rsyslog/lmtcpsrv.so
/usr/lib/x86_64-linux-gnu/rsyslog/lmzlibw.so
/usr/lib/x86_64-linux-gnu/rsyslog/mmanon.so
/usr/lib/x86_64-linux-gnu/rsyslog/mmexternal.so
/usr/lib/x86_64-linux-gnu/rsyslog/mmfields.so
/usr/lib/x86_64-linux-gnu/rsyslog/mmjsonparse.so
/usr/lib/x86_64-linux-gnu/rsyslog/mmnormalize.so
/usr/lib/x86_64-linux-gnu/rsyslog/mmpstrucdata.so
/usr/lib/x86_64-linux-gnu/rsyslog/mmrm1stspace.so
/usr/lib/x86_64-linux-gnu/rsyslog/mmsequence.so
/usr/lib/x86_64-linux-gnu/rsyslog/mmutf8fix.so
/usr/lib/x86_64-linux-gnu/rsyslog/omjournal.so
/usr/lib/x86_64-linux-gnu/rsyslog/ommail.so
/usr/lib/x86_64-linux-gnu/rsyslog/omprog.so
/usr/lib/x86_64-linux-gnu/rsyslog/omuxsock.so
/usr/lib/x86_64-linux-gnu/rsyslog/pmaixforwardedfrom.so
/usr/lib/x86_64-linux-gnu/rsyslog/pmcisconames.so
/usr/lib/x86_64-linux-gnu/rsyslog/pmlastmsg.so
/usr/lib/x86_64-linux-gnu/rsyslog/pmsnare.so
/usr/sbin/rsyslogd
/usr/share/doc/rsyslog
/usr/share/doc/rsyslog/AUTHORS
/usr/share/doc/rsyslog/NEWS.Debian.gz
/usr/share/doc/rsyslog/README.Debian
/usr/share/doc/rsyslog/changelog.Debian.gz
/usr/share/doc/rsyslog/changelog.gz
/usr/share/doc/rsyslog/copyright
/usr/share/doc/rsyslog/examples
/usr/share/doc/rsyslog/examples/rsyslog.d
/usr/share/doc/rsyslog/examples/tmpfiles.d
/usr/share/doc/rsyslog/examples/rsyslog.d/console.conf
/usr/share/doc/rsyslog/examples/rsyslog.d/xconsole.conf
/usr/share/doc/rsyslog/examples/tmpfiles.d/xconsole.conf
/usr/share/lintian/overrides/rsyslog
/usr/share/man/man5/rsyslog.conf.5.gz
/usr/share/man/man8/rsyslogd.8.gz
/usr/share/metasploit-framework/modules/auxiliary/dos/syslog/rsyslog_long_tag.rb
/var/cache/apt/archives/rsyslog_8.2006.0-2_amd64.deb
/var/lib/dpkg/info/rsyslog.conffiles
/var/lib/dpkg/info/rsyslog.list
/var/lib/dpkg/info/rsyslog.md5sums
/var/lib/dpkg/info/rsyslog.postinst
/var/lib/dpkg/info/rsyslog.postrm
/var/lib/dpkg/info/rsyslog.preinst
/var/lib/dpkg/info/rsyslog.prerm
/var/lib/dpkg/info/rsyslog.triggers
/var/lib/systemd/deb-systemd-helper-enabled/rsyslog.service.dsh-also
/var/lib/systemd/deb-systemd-helper-enabled/multi-user.target.wants/rsyslog.service
````

---


### 2.
Open the `rsyslog.conf` file and change your log rotation to one week.

---

````shell
kali@kali:~$ vi /etc/rsyslog.conf
--snip--
````

````shell
kali@kali:~$ vi /etc/logrotate.conf
--snip--
````

---


### 3.
Disable logging on your system. Investigate what is logged in the file `/var/log/syslog` when you disable logging.

---

````shell
root@kali:/home/kali# service rsyslog stop
Warning: Stopping rsyslog.service, but it can still be activated by:
  syslog.socket
root@kali:/home/kali# tail /var/log/syslog
Sep  8 10:28:21 kali systemd[1]: Stopped User Runtime Directory /run/user/131.
Sep  8 10:28:21 kali systemd[1]: Removed slice User Slice of UID 131.
Sep  8 10:31:22 kali systemd[1]: Stopping System Logging Service...
Sep  8 10:31:22 kali rsyslogd: [origin software="rsyslogd" swVersion="8.2006.0" x-pid="490" x-info="https://www.rsyslog.com"] exiting on signal 15.
Sep  8 10:31:22 kali systemd[1]: rsyslog.service: Succeeded.
Sep  8 10:31:22 kali systemd[1]: Stopped System Logging Service.
Sep  8 10:31:22 kali systemd[1]: Starting System Logging Service...
Sep  8 10:31:22 kali systemd[1]: Started System Logging Service.
Sep  8 10:31:22 kali rsyslogd: imuxsock: Acquired UNIX socket '/run/systemd/journal/syslog' (fd 3) from systemd.  [v8.2006.0]
Sep  8 10:31:22 kali rsyslogd: [origin software="rsyslogd" swVersion="8.2006.0" x-pid="21805" x-info="https://www.rsyslog.com"] start
````

---


### 4.
Use the `shred` command to shred and delete all your `kern` log files.

---

````shell
root@kali:/home/kali# cat /etc/rsyslog.conf | grep kern
module(load="imklog")   # provides kernel logging support
kern.*                          -/var/log/kern.log
root@kali:/home/kali# shred -f -n 10 /var/log/kern.log
````

---
