# Task 9 - ICMP Network Scanning

## Task 9 <mark style="color:green;background-color:green;">Scan Types</mark> ICMP Network Scanning

### How would you perform a ping sweep on the 172.16.x.x network (Netmask: 255.255.0.0) using Nmap? (CIDR notation)

{% embed url="https://nmap.org/book/host-discovery-controls.html#host-discovery-sn" %}
[https://nmap.org/book/host-discovery-controls.html#host-discovery-sn](https://nmap.org/book/host-discovery-controls.html#host-discovery-sn)
{% endembed %}

{% embed url="https://www.aelius.com/njh/subnet_sheet.html" %}
[https://www.aelius.com/njh/subnet\_sheet.html](https://www.aelius.com/njh/subnet\_sheet.html)
{% endembed %}

| CIDR | Addresses | Hosts | Netmask     | Amount of a Class C |
| ---- | --------- | ----- | ----------- | ------------------- |
| /16  | 65536     | 65534 | 255.255.0.0 | 256                 |

{% hint style="warning" %}
**HINT:** The CIDR notation for a Class B network with a default netmask is /16
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`nmap -sn 172.16.0.0/16`

</details>
