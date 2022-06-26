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



<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`/internal/`

</details>

## Task 4 - Compromise the webserver

### Try upload a few file types to the server, what common extension seems to be blocked?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:

</details>

### To identify which extensions are not blocked, we're going to fuzz the upload form. To do this, we're going to use **BurpSuite.** If you are unsure to what BurpSuite is, or how to set it up please complete our [BurpSuite room](https://tryhackme.com/room/rpburpsuite) first.

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:``

</details>

### Run this attack, what extension is allowed?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:``

</details>

### Upload your shell and navigate to **http://\<ip>:3333/internal/uploads/php-reverse-shell.phtml.** You should see a connection on your netcat session

{% hint style="success" %}
No answer needed
{% endhint %}

### What is the name of the user who manages the webserver?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:``

</details>

### What is the user flag?

{% hint style="warning" %}
**HINT:** The contents of the file /home/bill/user.txt
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:``

</details>

## Task 5 - Privilege Escalation

### On the system, search for all SUID files. What file stands out?

{% hint style="warning" %}
**HINT:** Use the command: find / -user root -perm -4000 -exec ls -ldb {} ;
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:``

</details>

### Its challenge time! We have guided you through this far, are you able to exploit this system further to escalate your privileges and get the final answer? Become root and get the last flag (/root/root.txt)

{% hint style="warning" %}
**HINT:** /bin/systemctl
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:``

</details>

