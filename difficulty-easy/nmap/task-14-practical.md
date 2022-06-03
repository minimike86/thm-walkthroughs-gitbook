# Task 14 - Practical

## Task 14 Practical

### Does the target (<mark style="color:red;background-color:red;">MACHINE\_IP</mark>)respond to ICMP (ping) requests (Y/N)?

```bash
ping MACHINE_IP
```

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`N`

</details>

### Perform an Xmas scan on the first 999 ports of the target -- how many ports are shown to be open or filtered?

{% embed url="https://nmap.org/book/scan-methods-null-fin-xmas-scan.html" %}
[https://nmap.org/book/scan-methods-null-fin-xmas-scan.html](https://nmap.org/book/scan-methods-null-fin-xmas-scan.html)
{% endembed %}

```bash
nmap -sX MACHINE_IP -p 1-999 
```

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`999`

</details>

### There is a reason given for this -- what is it?

**Note: The answer will be in your scan results. Think carefully about which switches to use -- and read the hint before asking for help!**

{% hint style="warning" %}
**HINT:** Run this command with the -vv switch enabled. It's good practice to _always_ increase the verbosity in your scans.
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`No Response`

</details>

### Perform a TCP SYN scan on the first 5000 ports of the target -- how many ports are shown to be open?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`5`

</details>

### Open Wireshark (see Cryillic's Wireshark Room for instructions) and perform a TCP Connect scan against port 80 on the target, monitoring the results. Make sure you understand what's going on.

{% hint style="success" %}
No answer needed
{% endhint %}

### Deploy the <mark style="color:red;background-color:red;">ftp-anon</mark> script against the box. Can Nmap login successfully to the FTP server on port 21? (Y/N)

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Y`

</details>
