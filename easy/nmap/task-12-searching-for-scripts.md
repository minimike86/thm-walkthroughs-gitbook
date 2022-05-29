# Task 12 - Searching for Scripts

## Task 12 <mark style="color:orange;background-color:orange;">NSE Scripts</mark> Searching for Scripts

### Search for "smb" scripts in the <mark style="color:red;background-color:red;">/usr/share/nmap/scripts/</mark> directory using either of the demonstrated methods. What is the filename of the script which determines the underlying OS of the SMB server?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`smb-os-discovery.nse`

</details>

### Read through this script. What does it depend on?

{% code title="smb-os-discovery.nse line:81" %}
```lua
dependencies = {"smb-brute"}
```
{% endcode %}

{% hint style="warning" %}
**HINT:** Look for `dependencies = {}` in the Lua script.
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`smb-brute`

</details>
