# Task 3 - Welcome to Attacktive Directory

## Task 3 <mark style="color:blue;background-color:blue;">Enumeration</mark> **Welcome to Attacktive Directory**

### What tool will allow us to enumerate port 139/445?

{% hint style="info" %}
The guide doesn't make it particularly clear what tool you need to use other than [nmap](https://nmap.org/) so to save you from acquiring mild brain ache just go over to kali tools to read up on [enum4linux](https://www.kali.org/tools/enum4linux/).
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`enum4linux`

</details>

### What is the [NetBIOS-Domain Name](https://docs.microsoft.com/en-us/troubleshoot/windows-server/identity/naming-conventions-for-computer-domain-site-ou) of the machine?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`THM-AD`

</details>

### What invalid [TLD](https://en.wikipedia.org/wiki/Top-level\_domain) do people commonly use for their Active Directory Domain?

Generic TLDs like `.local`, `.lan`, `.corp`, etc, are now being sold by [ICANN](https://www.icann.org/), so the domain you’re using internally today – `company.local` could potentially become another company’s property tomorrow.

{% hint style="warning" %}
**HINT:** The full AD domain is spookysec.local
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`.local`

</details>

##
