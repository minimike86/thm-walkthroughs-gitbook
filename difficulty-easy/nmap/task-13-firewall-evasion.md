# Task 13 - Firewall Evasion

### Which simple (and frequently relied upon) protocol is often blocked, requiring the use of the <mark style="color:red;background-color:red;">-Pn</mark> switch?

> Fortunately Nmap provides an option for this: -Pn, which tells Nmap to not bother pinging the host before scanning it. This means that Nmap will always treat the target host(s) as being alive, effectively bypassing the ICMP block;

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`ICMP`

</details>

### \[Research] Which Nmap switch allows you to append an arbitrary length of random data to the end of packets?

{% embed url="https://nmap.org/book/man-bypass-firewalls-ids.html" %}
[https://nmap.org/book/man-bypass-firewalls-ids.html](https://nmap.org/book/man-bypass-firewalls-ids.html)
{% endembed %}

> \--data-length (Append random data to sent packets)\
> _Normally Nmap sends minimalist packets containing only a header. So its TCP packets are generally 40 bytes and ICMP echo requests are just 28. Some UDP ports and IP protocols get a custom payload by default. This option tells Nmap to append the given number of random bytes to most of the packets it sends, and not to use any protocol-specific payloads. (Use --data-length 0 for no random or protocol-specific payloads. OS detection (-O) packets are not affected because accuracy there requires probe consistency, but most pinging and portscan packets support this. It slows things down a little, but can make a scan slightly less conspicuous._

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`--data-length`

</details>
