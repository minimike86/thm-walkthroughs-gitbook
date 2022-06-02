---
description: Learn about some of the technologies and designs that power private networks
---

# 🔌 Intro to LAN



{% embed url="https://tryhackme.com/room/introtolan" %}
[https://tryhackme.com/room/introtolan](https://tryhackme.com/room/introtolan)
{% endembed %}



| Room Attributes       | Value                                                                   |
| --------------------- | ----------------------------------------------------------------------- |
| Subscription Required |  <mark style="color:green;background-color:green;">False</mark> \[Free] |
| Type                  | Walkthrough                                                             |
| Difficulty            |  <mark style="color:blue;background-color:blue;">Info</mark>            |
| Tags                  | Networking, Networking Fundamentals, DHCP, ARP                          |



## Task 1 - Introducing LAN Topologies

### What does LAN stand for?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Local Area Network`

</details>

### What is the verb given to the job that Routers perform?

{% hint style="warning" %}
**HINT:** This is the term given to deciding what route packets should take
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Routing`

</details>

### What device is used to centrally connect multiple devices on the local network and transmit data to the correct location?

{% hint style="warning" %}
**HINT:** Something smarter than a hub/repeater.
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Switch`

</details>

### What topology is cost-efficient to set up?

{% hint style="warning" %}
**HINT:** \*\*\* Topology
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Bus Topology`

</details>

### What topology is expensive to set up and maintain?

{% hint style="warning" %}
**HINT:** \*\*\*\* Topology
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Star Topology`

</details>

### Complete the interactive lab attached to this task. What is the flag given at the end?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`THM{TOPOLOGY_FLAWS}`

</details>



## Task 2 - A Primer on Subnetting&#x20;

### What is the technical term for dividing a network up into smaller pieces?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Subnetting`

</details>

### How many **bits** are in a subnet mask?

{% hint style="warning" %}
**HINT:** This can be converted into 4 bytes
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`32`

</details>

### What is the range of a section (octet) of a subnet mask?

{% hint style="warning" %}
**HINT:** Smallest to largest
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`0-255`

</details>

### What address is used to identify the start of a network?

{% hint style="warning" %}
**HINT:** \*\*\*\*\*\*\* Address
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Network Address`

</details>

### What address is used to identify devices within a network?

{% hint style="warning" %}
**HINT:** \*\*\*\* Address
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Host Address`

</details>

### What is the name used to identify the device responsible for sending data to another network?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Default Gateway`

</details>



## Task 3 - The ARP Protocol&#x20;

What does ARP stand for?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Address Resolution Protocol`

</details>

What category of ARP Packet asks a device whether or not it has a specific IP address?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Request`

</details>

What address is used as a physical identifier for a device on a network?

{% hint style="warning" %}
**HINT:** \*\*\* Address
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`MAC Address`

</details>

What address is used as a logical identifier for a device on a network?

{% hint style="warning" %}
**HINT:** \*\* Address
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`IP Address`

</details>



## Task 4 - The DHCP Protocol&#x20;

### What type of DHCP packet is used by a device to **retrieve an IP address?**

{% hint style="warning" %}
**HINT:** DHCP \*\*\*\*\*\*\*\*
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`DHCP Discover`

</details>

### What type of DHCP packet does a device **send once it has been** **offered an IP address** by the DHCP server?

{% hint style="warning" %}
**HINT:** DHCP \*\*\*\*\*\*\*
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`DHCP Request`

</details>

### Finally, **what is the last** DHCP packet that is sent to a device from a DHCP server?

{% hint style="warning" %}
**HINT:** DHCP \*\*\*
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`DHCP ACK`

</details>



## Task 5 - Continue Your Learning: OSI Model

{% embed url="https://tryhackme.com/room/osimodelzi" %}
[https://tryhackme.com/room/osimodelzi](https://tryhackme.com/room/osimodelzi) \[SUBSCRIBER ONLY]
{% endembed %}

### Join the "OSI Model" room.

{% hint style="success" %}
No answer needed
{% endhint %}

