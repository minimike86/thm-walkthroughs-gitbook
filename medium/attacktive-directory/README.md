---
description: >-
  99% of Corporate networks run off of AD. But can you exploit a vulnerable
  Domain Controller?
cover: ../../.gitbook/assets/attacktivedirectory.PNG
coverY: 6.5785609397944205
---

# 🪟 Attacktive Directory

{% embed url="https://tryhackme.com/room/attacktivedirectory" %}
[https://tryhackme.com/room/attacktivedirectory](https://tryhackme.com/room/attacktivedirectory)
{% endembed %}

| Room Attributes       | Value                                                                   |
| --------------------- | ----------------------------------------------------------------------- |
| Subscription Required |  <mark style="color:green;background-color:green;">False</mark> \[Free] |
| Type                  | Challenges (CTF)                                                        |
| Difficulty            |  <mark style="color:orange;background-color:orange;">Medium</mark>      |
| Tags                  | Active Directory, AD, Kerberos, SMB                                     |

## Task 1 <mark style="background-color:green;"><mark style="color:blue;"><mark style="color:blue;"></mark> <mark style="color:green;background-color:green;"><mark style="color:green;">Intro<mark style="color:green;"></mark> <mark style="background-color:green;"></mark> Deploy The Machine

The first four questions are part of a mini-walkthrough that cover getting access to the target machine. They all require no answer so just follow the steps to get connected to the VPN, deploy the machine and get hacking!

## Task 2 <mark style="background-color:green;"><mark style="color:blue;"><mark style="color:blue;"></mark> <mark style="color:green;background-color:green;"><mark style="color:green;">Intro<mark style="color:green;"></mark> <mark style="background-color:green;"></mark> Setup

{% tabs %}
{% tab title="Install Impacket" %}
### Install Impacket

[Impacket ](https://github.com/SecureAuthCorp/impacket)is a collection of Python classes for working with network protocols. Enter the following commands into your [kali linux](https://www.kali.org/) terminal to add the repo to your /opt/impacket folder and to install with [python3](https://www.python.org/downloads/):

`sudo git clone` [`https://github.com/SecureAuthCorp/impacket.git`](https://github.com/SecureAuthCorp/impacket.git)`/opt/impacket`

`sudo pip3 install -r /opt/impacket/requirements.txt`&#x20;

`cd /opt/impacket/`&#x20;

`sudo pip3 install .`&#x20;

`sudo python3 setup.py install`
{% endtab %}

{% tab title="Install Bloodhound and Neo4j (Optional)" %}
### Bloodhound and Neo4j

{% hint style="info" %}
This section of the THM walkthrough states that the lab uses [Bloodhound ](https://github.com/BloodHoundAD/BloodHound)to attack the Attacktive Directory target machine but since the May 2021 room renovation is no longer does so you can skip this section if you want.
{% endhint %}

Install [Bloodhound](https://github.com/BloodHoundAD/BloodHound) and its database dependency [neo4j ](https://neo4j.com/developer/)via apt:&#x20;

`apt install bloodhound neo4j`
{% endtab %}
{% endtabs %}

## Task 3 <mark style="color:blue;background-color:blue;">Enumeration</mark> **Welcome to Attacktive Directory**

{% content-ref url="task-3-welcome-to-attacktive-directory.md" %}
[task-3-welcome-to-attacktive-directory.md](task-3-welcome-to-attacktive-directory.md)
{% endcontent-ref %}

## Task 4 <mark style="color:blue;background-color:blue;">Enumeration</mark> Enumerating Users via Kerberos

{% content-ref url="task-4-enumerating-users-via-kerberos.md" %}
[task-4-enumerating-users-via-kerberos.md](task-4-enumerating-users-via-kerberos.md)
{% endcontent-ref %}

## Task 5 <mark style="color:red;background-color:red;">Exploitation</mark> Abusing Kerberos

{% content-ref url="task-5-abusing-kerberos.md" %}
[task-5-abusing-kerberos.md](task-5-abusing-kerberos.md)
{% endcontent-ref %}

## Task 6 <mark style="color:blue;background-color:blue;">Enumeration</mark> Back to the Basics

{% content-ref url="task-6-back-to-the-basics.md" %}
[task-6-back-to-the-basics.md](task-6-back-to-the-basics.md)
{% endcontent-ref %}

## Task 7 <mark style="color:red;background-color:red;">Domain Privilege Escalation</mark> Elevating Privileges within the Domain

{% content-ref url="task-7-elevating-privileges-within-the-domain.md" %}
[task-7-elevating-privileges-within-the-domain.md](task-7-elevating-privileges-within-the-domain.md)
{% endcontent-ref %}

## Task 8 <mark style="color:blue;background-color:blue;">Flag Submission</mark> Flag Submission Panel

{% content-ref url="task-8-flag-submission-panel.md" %}
[task-8-flag-submission-panel.md](task-8-flag-submission-panel.md)
{% endcontent-ref %}
