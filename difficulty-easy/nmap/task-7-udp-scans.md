# Task 7 - UDP Scans

## Task 7 <mark style="color:green;background-color:green;">Scan Types</mark> UDP Scans

### If a UDP port doesn't respond to an Nmap scan, what will it be marked as?

> Nmap refers to the port as being open|filtered

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`open|filtered`

</details>

### When a UDP port is closed, by convention the target should send back a "port unreachable" message. Which protocol would it use to do so?

> When a packet is sent to a closed UDP port, the target should respond with an ICMP (ping) packet containing a message that the port is unreachable.

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`ICMP`

</details>
