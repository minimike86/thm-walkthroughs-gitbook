# Task 8 - RustScan Quiz

## Task 8 - RustScan Quiz

### First, how do you access the help menu?&#x20;

```bash
rustscan -h
```

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`-h`

</details>

### Often referred to as "quiet" mode, What switch can do this?

{% hint style="danger" %}
**Since v1.9.0 the "quiet mode" was refactored so this question is out-of-date.**\
`--quiet mode is now renamed to --greppable. And this mode now returns an IP -> list`
{% endhint %}

{% embed url="https://github.com/RustScan/RustScan/releases/tag/1.9.0" %}
[https://github.com/RustScan/RustScan/releases/tag/1.9.0](https://github.com/RustScan/RustScan/releases/tag/1.9.0)
{% endembed %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`-q`

</details>

### Which switch can help us to scan for a particular Range?

> \-r, --range A range of ports with format start-end. Example: 1-1000

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`-r`

</details>

### What switch would you use to find out RustScan's version?

> \-V, --version Prints version information

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`-V`

</details>

### Which switch will help us to select batch size?

> \-b, --batch-size The batch size for port scanning, it increases or slows the speed of scanning. Depends on the open file limit of your OS. If you do 65535 it will do every port at the same time. Although, your OS may not support this \[default: 4500]

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`-b`

</details>

### Which switch can set timeout?

> \-t, --timeout The timeout in milliseconds before a port is assumed to be closed \[default: 1500]

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`-t`

</details>

