# Task 5 - Abusing Kerberos

## Task 5 <mark style="color:red;background-color:red;">Exploitation</mark> Abusing Kerberos

### We have two user accounts that we could potentially query a ticket from. Which user account can you query a ticket from with no password?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`svc-admin`

</details>

### Looking at the Hashcat Examples Wiki page, what type of Kerberos hash did we retrieve from the KDC? (Specify the full name)

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Kerberos 5 AS-REP etype 23`

</details>

### What mode is the hash?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`18200`

</details>

### Now crack the hash with the modified password list provided, what is the user accounts password?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`management2005`

</details>

##
