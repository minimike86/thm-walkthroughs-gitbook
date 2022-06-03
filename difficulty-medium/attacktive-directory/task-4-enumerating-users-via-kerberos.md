# Task 4 - Enumerating Users via Kerberos

## Task 4 <mark style="color:blue;background-color:blue;">Enumeration</mark> Enumerating Users via Kerberos

In order to use [Kerbrute](https://github.com/ropnop/kerbrute) to enumerate the users, you will also need to download the provided [User List](https://raw.githubusercontent.com/Sq00ky/attacktive-directory-tools/master/userlist.txt) and [Password List](https://raw.githubusercontent.com/Sq00ky/attacktive-directory-tools/master/passwordlist.txt) which you can get from [Sq00ky](https://tryhackme.com/p/Sq00ky)'s repo [attacktive-directory-tools](https://github.com/Sq00ky/attacktive-directory-tools).

### What command within [Kerbrute](https://github.com/ropnop/kerbrute) will allow us to enumerate valid usernames?

{% hint style="warning" %}
**HINT:** ./kerbrute -h may help you
{% endhint %}

[Kerbrute](https://github.com/ropnop/kerbrute) bruteforces and enumerates valid Active Directory accounts through Kerberos Pre-Authentication. The [following command](https://wadcoms.github.io/wadcoms/Kerbrute-UserEnum/) will attempt to enumerate valid usernames given a list of usernames to try:

{% code title="kerbrute" %}
```
kerbrute userenum -d domain.tld usernames.txt
```
{% endcode %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`userenum`&#x20;

</details>

### What notable account is discovered?

> _(These should jump out at you)_

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`svc-admin`

</details>

### What is the other notable account is discovered?

> _(These should jump out at you)_

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`backup`

</details>

##
