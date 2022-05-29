# Task 3 - Nmap Switches

### What is the first switch listed in the help menu for a 'Syn Scan' (more on this later!)?

{% embed url="https://nmap.org/book/synscan.html" %}
[https://nmap.org/book/synscan.html](https://nmap.org/book/synscan.html)
{% endembed %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`-sS`

</details>

### Which switch would you use for a "UDP scan"?

{% embed url="https://nmap.org/book/scan-methods-udp-scan.html" %}
[https://nmap.org/book/scan-methods-udp-scan.html](https://nmap.org/book/scan-methods-udp-scan.html)
{% endembed %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`-sU`

</details>

### If you wanted to detect which operating system the target is running on, which switch would you use?

{% embed url="https://nmap.org/book/osdetect-usage.html#osdetect-ex-scanme1" %}
[https://nmap.org/book/osdetect-usage.html#osdetect-ex-scanme1](https://nmap.org/book/osdetect-usage.html#osdetect-ex-scanme1)
{% endembed %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`-O`

</details>

### Nmap provides a switch to detect the version of the services running on the target. What is this switch?

{% embed url="https://nmap.org/book/man-version-detection.html" %}
[https://nmap.org/book/man-version-detection.html](https://nmap.org/book/man-version-detection.html)
{% endembed %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`-sV`

</details>

### The default output provided by nmap often does not provide enough information for a pentester. How would you increase the verbosity?

{% embed url="https://nmap.org/book/man-output.html" %}
[https://nmap.org/book/man-output.html](https://nmap.org/book/man-output.html)
{% endembed %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`-v`

</details>

### Verbosity level one is good, but verbosity level two is better! How would you set the verbosity level to two? (Note: it's highly advisable to always use at least this option)

{% embed url="https://nmap.org/book/output-formats-commandline-flags.html#output-formats-flags-verbosity" %}
[https://nmap.org/book/output-formats-commandline-flags.html#output-formats-flags-verbosity](https://nmap.org/book/output-formats-commandline-flags.html#output-formats-flags-verbosity)
{% endembed %}

#### Verbosity and debugging options

\-v (Increase verbosity level) , -v (Set verbosity level)

> Increases the verbosity level, causing Nmap to print more information about the scan in progress. Open ports are shown as they are found and completion time estimates are provided when Nmap thinks a scan will take more than a few minutes. Use it twice or more for even greater verbosity: -vv, or give a verbosity level directly, for example -v3.

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`-vv`

</details>

**We should always save the output of our scans -- this means that we only need to run the scan once (reducing network traffic and thus chance of detection), and gives us a reference to use when writing reports for clients.**

### What switch would you use to save the nmap results in three major formats?

{% embed url="https://nmap.org/book/output-formats-commandline-flags.html#output-formats-flags-verbosity" %}
[https://nmap.org/book/output-formats-commandline-flags.html#output-formats-flags-verbosity](https://nmap.org/book/output-formats-commandline-flags.html#output-formats-flags-verbosity)
{% endembed %}

> As a convenience, you may specify -oA to store scan results in normal, XML, and grepable formats at once. They are stored in .nmap, .xml, and .gnmap, respectively.

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`-oA`

</details>

### What switch would you use to save the nmap results in a "normal" format?

{% embed url="https://nmap.org/book/output-formats-normal-output.html" %}
[https://nmap.org/book/output-formats-normal-output.html](https://nmap.org/book/output-formats-normal-output.html)
{% endembed %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`-oN`

</details>

### A very useful output format: how would you save results in a "grepable" format?

{% embed url="https://nmap.org/book/output-formats-grepable-output.html" %}
[https://nmap.org/book/output-formats-grepable-output.html](https://nmap.org/book/output-formats-grepable-output.html)
{% endembed %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`-oG`

</details>

**Sometimes the results we're getting just aren't enough. If we don't care about how loud we are, we can enable "aggressive" mode. This is a shorthand switch that activates service detection, operating system detection, a traceroute and common script scanning.**

### How would you activate this setting?

{% embed url="https://linux.die.net/man/1/nmap" %}
[https://linux.die.net/man/1/nmap](https://linux.die.net/man/1/nmap)
{% endembed %}

> \-A: Enable OS detection, version detection, script scanning, and traceroute

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`-A`

</details>

**Nmap offers five levels of "timing" template. These are essentially used to increase the speed your scan runs at. Be careful though: higher speeds are noisier, and can incur errors!**

### How would you set the timing template to level 5?

{% embed url="https://nmap.org/book/performance-timing-templates.html" %}
[https://nmap.org/book/performance-timing-templates.html](https://nmap.org/book/performance-timing-templates.html)
{% endembed %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`-T5`

</details>

**We can also choose which port(s) to scan.**

### How would you tell nmap to only scan port 80?

{% embed url="https://nmap.org/book/man-port-specification.html" %}
[https://nmap.org/book/man-port-specification.html](https://nmap.org/book/man-port-specification.html)
{% endembed %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`-p 80`

</details>

### How would you tell nmap to scan ports 1000-1500?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`-p 1000-1500`

</details>

**A very useful option that should not be ignored:**

### How would you tell nmap to scan all ports?

{% embed url="https://nmap.org/book/man-port-specification.html" %}
[https://nmap.org/book/man-port-specification.html](https://nmap.org/book/man-port-specification.html)
{% endembed %}

> So you can specify -p- to scan ports from 1 through 65535.

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`-p-`

</details>

### How would you activate a script from the nmap scripting library (lots more on this later!)?

{% embed url="https://nmap.org/book/man-nse.html" %}
[https://nmap.org/book/man-nse.html](https://nmap.org/book/man-nse.html)
{% endembed %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`--script`

</details>

### How would you activate all of the scripts in the "vuln" category?

{% embed url="https://nmap.org/book/nse-usage.html#nse-category-vuln" %}
[https://nmap.org/book/nse-usage.html#nse-category-vuln](https://nmap.org/book/nse-usage.html#nse-category-vuln)
{% endembed %}

> These scripts check for specific known vulnerabilities and generally only report results if they are found. Examples include realvnc-auth-bypass and afp-path-vuln.

{% hint style="warning" %}
**HINT:** There are two variants of this switch. One with a space, one with the equals sign. Look at the asterisks in the answer field to see which one it is.
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`--script=vuln`

</details>
