# Task 7 - Scanning Time!

## Task 7 - Scanning Time!

### Try running the scan for all ports.

```bash
rustscan -a MACHINE_IP --range 1-65535
```

{% hint style="warning" %}
**HINT:** 65535 ports are there!
{% endhint %}

{% hint style="success" %}
No answer needed
{% endhint %}

### After scanning this, how many ports do we find open under 1000?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`2`

</details>

### Perform a service version detection scan, what is the version of the software running on port 22?

```bash
rustscan -a MACHINE_IP --range 1-65535 -- -sV
```

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`6.6.1p1`

</details>

### Perform an aggressive scan, what flag isn't set under the results for port 80?

```bash
rustscan -a MACHINE_IP -p 80 -- -A
```

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`httponly`

</details>

### Using this tool in scanning can save a lot of time! Make sure to use it in your pentest.

{% hint style="success" %}
No answer needed
{% endhint %}
