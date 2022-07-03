---
description: >-
  Practice your Linux Privilege Escalation skills on an intentionally
  misconfigured Debian VM with multiple ways to get root! SSH is available.
  Credentials: user:password321
---

# 🛗 Linux PrivEsc

{% embed url="https://tryhackme.com/room/linuxprivesc" %}
[https://tryhackme.com/room/linuxprivesc](https://tryhackme.com/room/linuxprivesc)
{% endembed %}

| Room Attributes       | Value                                                                   |
| --------------------- | ----------------------------------------------------------------------- |
| Subscription Required |  <mark style="color:green;background-color:green;">False</mark> \[Free] |
| Type                  | Walkthroughs                                                            |
| Difficulty            |  <mark style="color:orange;background-color:yellow;">Medium</mark>      |
| Tags                  | PrivEsc, Privilege Escalation, Linux, Linux Privilege Escalation        |

## Task 1 Deploy the Vulnerable Debian VM

### Deploy the machine and login to the "user" account using SSH.

{% hint style="success" %}
No answer needed
{% endhint %}

### Run the "id" command. What is the result?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`uid=1000(user) gid=1000(user) groups=1000(user),24(cdrom),25(floppy),29(audio),30(dip),44(video),46(plugdev)`

</details>

## Task 2 Service Exploits

### Read and follow along with the above.

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 3 Weak File Permissions - Readable /etc/shadow

### What is the root user's password hash?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`$6$Tb/euwmK$OXA.dwMeOAcopwBl68boTG5zi65wIHsc84OWAIye5VITLLtVlaXvRDJXET..it8r.jbrlpfZeMdwD3B0fGxJI0`

</details>

### What hashing algorithm was used to produce the root user's password hash?

{% hint style="warning" %}
**HINT:** john the ripper should automatically identify it when cracking!
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`sha512crypt`

</details>

### What is the root user's password?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`password123`

</details>

## Task 4 Weak File Permissions - Writable /etc/shadow

### Read and follow along with the above.

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 5 Weak File Permissions - Writable /etc/passwd

### Run the "id" command as the newroot user. What is the result?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`uid=0(root) gid=0(root) groups=0(root)`

</details>

## Task 6 Sudo - Shell Escape Sequences

### How many programs is "user" allowed to run via sudo?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`11`

</details>

### One program on the list doesn't have a shell escape sequence on GTFOBins. Which is it?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`apache2`

</details>

### Consider how you might use this program with sudo to gain root privileges without a shell escape sequence.

{% hint style="warning" %}
**HINT:** Play around with certain options the program has!
{% endhint %}

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 7 Sudo - Environment Variables

### Read and follow along with the above.

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 8 Cron Jobs - File Permissions

### Read and follow along with the above.

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 9 Cron Jobs - PATH Environment Variable

### What is the value of the PATH variable in /etc/crontab?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`/home/user:/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin`

</details>

## Task 10 Cron Jobs - Wildcards

### Read and follow along with the above.

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 11 SUID / SGID Executables - Known Exploits

### Read and follow along with the above.

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 12 SUID / SGID Executables - Shared Object Injection

### Read and follow along with the above.

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 13 SUID / SGID Executables - Environment Variables

### Read and follow along with the above.

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 14 SUID / SGID Executables - Abusing Shell Features (#1)

### Read and follow along with the above.

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 15 SUID / SGID Executables - Abusing Shell Features (#2)

### Read and follow along with the above.

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 16 Passwords & Keys - History Files

### What is the full mysql command the user executed?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`mysql -h somehost.local -uroot -ppassword123`

</details>

## Task 17 Passwords & Keys - Config Files

### What file did you find the root user's credentials in?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`/etc/openvpn/auth.txt`

</details>

## Task 18 Passwords & Keys - SSH Keys

### Read and follow along with the above.

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 19 NFS

### What is the name of the option that disables root squashing?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`no_root_squash`

</details>

## Task 20 Kernel Exploits

### Read and follow along with the above.

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 21 Privilege Escalation Scripts

### Experiment with all three tools, running them with different options. Do all of them identify the techniques used in this room?

{% hint style="success" %}
No answer needed
{% endhint %}

