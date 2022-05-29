# Task 8 - NULL, FIN and Xmas

## Task 8 <mark style="color:green;background-color:green;">Scan Types</mark> NULL, FIN and Xmas

### Which of the three shown scan types uses the URG flag?

> It's referred to as an xmas scan as the flags that it sets (PSH, URG and FIN)

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`xmas`

</details>

### Why are NULL, FIN and Xmas scans generally used?

> That said, the goal here is, of course, firewall evasion. Many firewalls are configured to drop incoming TCP packets to blocked ports which have the SYN flag set (thus blocking new connection initiation requests). By sending requests which do not contain the SYN flag, we effectively bypass this kind of firewall.

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Firewall Evasion`

</details>

### Which common OS may respond to a NULL, FIN or Xmas scan with a RST for every port?

> In particular Microsoft Windows (and a lot of Cisco network devices) are known to respond with a RST to any malformed TCP packet -- regardless of whether the port is actually open or not.

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Microsoft Windows`

</details>
