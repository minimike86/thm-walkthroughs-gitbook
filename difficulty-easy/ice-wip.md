---
description: >-
  Deploy & hack into a Windows machine, exploiting a very poorly secured media
  server.
---

# 🧊 Ice \[WIP]

{% embed url="https://tryhackme.com/room/ice" %}
[https://tryhackme.com/room/ice](https://tryhackme.com/room/ice)
{% endembed %}

| Room Attributes       | Value                                                                                                                  |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| Subscription Required |  <mark style="color:green;background-color:green;">False</mark> \[Free]                                                |
| Type                  | Walkthroughs                                                                                                           |
| Difficulty            |  <mark style="color:green;background-color:green;">Easy</mark>  <mark style="color:red;background-color:red;"></mark>  |
| Tags                  | Windows, Nmap, Mimikatz, Metasploit                                                                                    |

## Video Walkthrough <a href="#task-1-starting-your-first-machine" id="task-1-starting-your-first-machine"></a>

link to video

## Task 1 Connect

### Connect to our network using OpenVPN

{% hint style="success" %}
No answer needed
{% endhint %}

### Use an OpenVPN client to connect

{% hint style="success" %}
No answer needed
{% endhint %}

### Verify you are connected by looking on your access page

{% hint style="success" %}
No answer needed
{% endhint %}

### Now when you deploy material, you will see an internal IP address of your Virtual Machine.

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 2 Recon

Deploy the machine! This may take up to three minutes to start.

{% hint style="success" %}
No answer needed
{% endhint %}

Launch a scan against our target machine, I recommend using a SYN scan set to scan all ports on the machine. The scan command will be provided as a hint, however, it's recommended to complete the room '[Nmap](https://tryhackme.com/room/furthernmap)' prior to this room.

{% hint style="warning" %}
**HINT:** nmap -sS -p- TARGET\_IP
{% endhint %}

{% hint style="success" %}
No answer needed
{% endhint %}

Once the scan completes, we'll see a number of interesting ports open on this machine. As you might have guessed, the firewall has been disabled (with the service completely shutdown), leaving very little to protect this machine. One of the more interesting ports that is open is Microsoft Remote Desktop (MSRDP). What port is this open on?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`???`

</details>

What service did nmap identify as running on port 8000? (First word of this service)

{% hint style="warning" %}
**HINT:** If nmap doesn't show you the service name, try running the scan again possibly with the version enumeration switch on (-sV)
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`???`

</details>

What does Nmap identify as the hostname of the machine? (All caps for the answer)

{% hint style="warning" %}
**HINT:** If nmap doesn't show you the hostname, try running the scan again possibly with the default scripts switch on (-sC)
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`???`

</details>

## Task 3 Gain Access

### What type of vulnerability is it? Use [https://www.cvedetails.com](https://www.cvedetails.com/) for this question and the next.

{% hint style="warning" %}
**HINT:** This type of vulnerability allows for an attacker to execute arbitrary code in an unauthenticated fashion. The name can be found listed at the 'Vulnerability Type' on https://www.cvedetails.com
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`???`

</details>

### What is the CVE number for this vulnerability? This will be in the format: CVE-0000-0000

{% hint style="warning" %}
**HINT:** This CVE was disclosed in 2004. In the case that you get stuck on this question, a link to the manual version of the exploit associated with this service can be found in the final task. This link has some additional details about the CVE we're exploring here. https://www.cvedetails.com is recommended for the completion of this question.
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`???`

</details>

### Now that we've found our vulnerability, let's find our exploit. For this section of the room, we'll use the Metasploit module associated with this exploit. Let's go ahead and start Metasploit using the command \`msfconsole\`

{% hint style="success" %}
No answer needed
{% endhint %}

### What is the full path (starting with exploit) for the exploitation module? This module is also referenced in '[RP: Metasploit](https://tryhackme.com/room/rpmetasploit)' which is recommended to be completed prior to this room, although not entirely necessary.&#x20;

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`???`

</details>

### Let's go ahead and select this module for use. Type either the command \`use icecast\` or \`use 0\` to select our search result.

{% hint style="success" %}
No answer needed
{% endhint %}

### Following selecting our module, we now have to check what options we have to set. Run the command \`show options\`. What is the only required setting which currently is blank?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`???`

</details>

### First let's check that the LHOST option is set to our tun0 IP (which can be found on the [access](https://tryhackme.com/access) page). With that done, let's set that last option to our target IP. Now that we have everything ready to go, let's run our exploit using the command \`exploit\`

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 4 Escalate

Woohoo! We've gained a foothold into our victim machine! What's the name of the shell we have now?

&#x20;Submit HintWhat user was running that Icecast process? The commands used in this question and the next few are taken directly from the '[RP: Metasploit](https://tryhackme.com/room/rpmetasploit)' room. Submit Hint

What build of Windows is the system?

&#x20;Submit Hint

Now that we know some of the finer details of the system we are working with, let's start escalating our privileges. First, what is the architecture of the process we're running?

&#x20;Submit Hint

Now that we know the architecture of the process, let's perform some further recon. While this doesn't work the best on x64 machines, let's now run the following command \`run post/multi/recon/local\_exploit\_suggester\`. \*This can appear to hang as it tests exploits and might take several minutes to complete\*\


&#x20;Completed

Running the local exploit suggester will return quite a few results for potential escalation exploits. What is the full path (starting with exploit/) for the first returned exploit?\


&#x20;Submit HintNow that we have an exploit in mind for elevating our privileges, let's background our current session using the command \`background\` or \`CTRL + z\`. Take note of what session number we have, this will likely be 1 in this case. We can list all of our active sessions using the command \`sessions\` when outside of the meterpreter shell. CompletedGo ahead and select our previously found local exploit for use using the command \`use FULL\_PATH\_FOR\_EXPLOIT\` Completed

Local exploits require a session to be selected (something we can verify with the command \`show options\`), set this now using the command \`set session SESSION\_NUMBER\`\


&#x20;Completed

Now that we've set our session number, further options will be revealed in the options menu. We'll have to set one more as our listener IP isn't correct. What is the name of this option?

&#x20;Submit

Set this option now. You might have to check your IP on the TryHackMe network using the command \`ip addr\`

&#x20;Completed

After we've set this last option, we can now run our privilege escalation exploit. Run this now using the command \`run\`. Note, this might take a few attempts and you may need to relaunch the box and exploit the service in the case that this fails.&#x20;

&#x20;Completed

Following completion of the privilege escalation a new session will be opened. Interact with it now using the command \`sessions SESSION\_NUMBER\`

&#x20;Completed

We can now verify that we have expanded permissions using the command \`getprivs\`. What permission listed allows us to take ownership of files?

\


## Task 5 Looting

Prior to further action, we need to move to a process that actually has the permissions that we need to interact with the lsass service, the service responsible for authentication within Windows. First, let's list the processes using the command \`ps\`. Note, we can see processes being run by NT AUTHORITY\SYSTEM as we have escalated permissions (even though our process doesn't).&#x20;

&#x20;Completed

In order to interact with lsass we need to be 'living in' a process that is the same architecture as the lsass service (x64 in the case of this machine) and a process that has the same permissions as lsass. The printer spool service happens to meet our needs perfectly for this and it'll restart if we crash it! What's the name of the printer service?

Mentioned within this question is the term 'living in' a process. Often when we take over a running program we ultimately load another shared library into the program (a dll) which includes our malicious code. From this, we can spawn a new thread that hosts our shell.&#x20;

&#x20;Submit HintMigrate to this process now with the command \`migrate -N PROCESS\_NAME\` Completed

Let's check what user we are now with the command \`getuid\`. What user is listed?

&#x20;Submit

Now that we've made our way to full administrator permissions we'll set our sights on looting. Mimikatz is a rather infamous password dumping tool that is incredibly useful. Load it now using the command \`load kiwi\` (Kiwi is the updated version of Mimikatz)

&#x20;Completed

Loading kiwi into our meterpreter session will expand our help menu, take a look at the newly added section of the help menu now via the command \`help\`.&#x20;

&#x20;Completed

Which command allows up to retrieve all credentials?

&#x20;Submit

Run this command now. What is Dark's password? Mimikatz allows us to steal this password out of memory even without the user 'Dark' logged in as there is a scheduled task that runs the Icecast as the user 'Dark'. It also helps that Windows Defender isn't running on the box ;) (Take a look again at the ps list, this box isn't in the best shape with both the firewall and defender disabled)

\


## Task 6 Post-Exploitation

Before we start our post-exploitation, let's revisit the help menu one last time in the meterpreter shell. We'll answer the following questions using that menu. Completed

What command allows us to dump all of the password hashes stored on the system? We won't crack the Administrative password in this case as it's pretty strong (this is intentional to avoid password spraying attempts)

&#x20;Submit

While more useful when interacting with a machine being used, what command allows us to watch the remote user's desktop in real time?

&#x20;SubmitHow about if we wanted to record from a microphone attached to the system? Submit

To complicate forensics efforts we can modify timestamps of files on the system. What command allows us to do this? Don't ever do this on a pentest unless you're explicitly allowed to do so! This is not beneficial to the defending team as they try to breakdown the events of the pentest after the fact.

&#x20;Submit

Mimikatz allows us to create what's called a \`golden ticket\`, allowing us to authenticate anywhere with ease. What command allows us to do this?

Golden ticket attacks are a function within Mimikatz which abuses a component to Kerberos (the authentication system in Windows domains), the ticket-granting ticket. In short, golden ticket attacks allow us to maintain persistence and authenticate as any user on the domain.

&#x20;Submit

One last thing to note. As we have the password for the user 'Dark' we can now authenticate to the machine and access it via remote desktop (MSRDP). As this is a workstation, we'd likely kick whatever user is signed onto it off if we connect to it, however, it's always interesting to remote into machines and view them as their users do. If this hasn't already been enabled, we can enable it via the following Metasploit module: \`run post/windows/manage/enable\_rdp\`

\


## Task 7 Extra Credit

### As you advance in your pentesting skills, you will be faced eventually with exploitation without the usage of Metasploit. Provided above is the link to one of the exploits found on Exploit DB for hijacking Icecast for remote code execution.&#x20;

{% hint style="success" %}
No answer needed
{% endhint %}

## Task X (Duplicate For Each Task) <a href="#task-1-starting-your-first-machine" id="task-1-starting-your-first-machine"></a>

### Question Y (Duplicate For Each Question)

.

{% hint style="warning" %}
**HINT:** md5
{% endhint %}

.

{% hint style="success" %}
No answer needed
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`???`

</details>

