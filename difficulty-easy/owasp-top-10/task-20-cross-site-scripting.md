# Task 20 - Cross-site Scripting

## Task 20 <mark style="color:blue;background-color:blue;">\[Severity 7]</mark> Cross-site Scripting

### Deploy the VM

{% hint style="success" %}
No answer needed
{% endhint %}

### Navigate to http://MACHINE\_IP/ in your browser and click on the "Reflected XSS" tab on the navbar; craft a reflected XSS payload that will cause a popup saying "Hello".

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`ThereIsMoreToXSSThanYouThink`

</details>

### On the same reflective page, craft a reflected XSS payload that will cause a popup with your machines IP address.

{% hint style="warning" %}
In Javascript window.location.hostname will show your hostname, in this case your deployed machine's hostname will be its IP.
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`ReflectiveXss4TheWin`

</details>

### Now navigate to http://MACHINE\_IP/ in your browser and click on the "Stored XSS" tab on the navbar; make an account. Then add a comment and see if you can insert some of your own HTML.

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`HTML_T4gs`

</details>

### On the same page, create an alert popup box appear on the page with your document cookies.

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`W3LL_D0N3_LVL2`

</details>

### Change "XSS Playground" to "I am a hacker" by adding a comment and using Javascript.

{% hint style="warning" %}
**HINT:** \<script>document.querySelector('#thm-title').textContent = 'I am a hacker'\</script>
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`websites_can_be_easily_defaced_with_xss`

</details>
