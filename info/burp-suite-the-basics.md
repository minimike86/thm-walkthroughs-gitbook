---
description: An introduction to using Burp Suite for Web Application pentesting
---

# 🟧 Burp Suite: The Basics

## Task 1 <mark style="color:green;background-color:green;">Introduction</mark> Outline

Deploy the machine attached to the task by pressing the green "Start Machine" button, as well as the AttackBox (using the "Start AttackBox" button at the top of the page) if you are not using your own machine.

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 2 <mark style="color:purple;background-color:purple;">Getting Started</mark> What is Burp Suite?

### Which edition of Burp Suite will we be using in this module?

{% hint style="warning" %}
**HINT:** The task above contains the answer in bold text. Paragraph Three.
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Burp Suite Community`

</details>

### Which edition of Burp Suite runs on a server and provides constant scanning for target web apps?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Burp Suite Enterprise`

</details>

### Burp Suite is frequently used when attacking web applications and \_\_\_\_\_\_ applications.

{% hint style="warning" %}
**HINT:** Fill in the blank
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Mobile`

</details>



## Task 3 <mark style="color:purple;background-color:purple;">Getting Started</mark> Features of Burp Community

### Which Burp Suite feature allows us to intercept requests between ourselves and the target?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Proxy`

</details>

### Which Burp tool would we use if we wanted to bruteforce a login form?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Intruder`

</details>



## Task 4 <mark style="color:purple;background-color:purple;">Getting Started</mark> Installation

### If you have chosen not to use the AttackBox, make sure that you have a copy of Burp Suite installed before proceeding.

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 5 <mark style="color:purple;background-color:purple;">Getting Started</mark> The Dashboard

### Open Burp Suite and have a look around the dashboard. Make sure that you are comfortable with it before moving on.

{% hint style="success" %}
No answer needed
{% endhint %}



## Task 6 <mark style="color:purple;background-color:purple;">Getting Started</mark> Navigation

### Get comfortable navigating around the top menu bars.

{% hint style="success" %}
No answer needed
{% endhint %}



## Task 7 <mark style="color:purple;background-color:purple;">Getting Started</mark> Options

### Change the Burp Suite theme to dark mode

{% hint style="success" %}
No answer needed
{% endhint %}

### In which _Project options_ sub-tab can you find reference to a "Cookie jar"?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Sessions`

</details>

### In which _User options_ sub-tab can you change the Burp Suite update behaviour?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Misc`

</details>

### What is the name of the section within the _User options_ "Misc" sub-tab which allows you to change the Burp Suite keybindings?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Hotkeys`

</details>

### If we have uploaded Client-Side TLS certificates in the _User options_ tab, can we override these on a per-project basis (Aye/Nay)?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Aye`

</details>

### There are many more configuration options available. Take the time to read through them. In the next section, we will cover the Burp Proxy -- a much more hands-on aspect of the room.

{% hint style="success" %}
No answer needed
{% endhint %}



## Task 8 <mark style="color:orange;background-color:orange;">Proxy</mark> Introduction to the Burp Proxy

### Which button would we choose to send an intercepted request to the target in Burp Proxy?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Forward`

</details>

### **\[Research]** What is the default keybind for this?

_**Note:** Assume you are using Windows or Linux (i.e. swap Cmd for Ctrl)._

{% hint style="warning" %}
**HINT:** Use what you learnt in a previous task to look up the keybindings used in Burp Suite, then find a keybinding related to forwarding intercepted proxy messages.
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Ctrl+F`

</details>



## Task 9 <mark style="color:orange;background-color:orange;">Proxy</mark> Connecting through the Proxy (FoxyProxy)

### Read through the options in the right-click menu. There is one particularly useful option that allows you to intercept and modify the _response_ to your request. What is this option?

_**Note:** The option is in a dropdown sub-menu._

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Response to this request`

</details>

**\[Bonus Question -- Optional]** Try installing FoxyProxy standard and have a look at the pattern matching features.

{% hint style="success" %}
No answer needed
{% endhint %}



## Task 10 <mark style="color:orange;background-color:orange;">Proxy</mark> Proxying HTTPS

### If you are not using the AttackBox, configure Firefox (or your browser of choice) to accept the Portswigger CA certificate for TLS communication through the Burp Proxy.

{% hint style="success" %}
No answer needed
{% endhint %}



## Task 11 <mark style="color:orange;background-color:orange;">Proxy</mark> The Burp Suite Browser

### Using the in-built browser, make a request to `http://MACHINE_IP/` and capture it in the proxy.

{% hint style="success" %}
No answer needed
{% endhint %}



## Task 12 <mark style="color:orange;background-color:orange;">Proxy</mark> Scoping and Targeting

### Add `http://MACHINE_IP/` to your scope and change the Proxy settings to only intercept traffic to in-scope targets. See the difference between the amount of traffic getting caught by the proxy before and after limiting the scope.

{% hint style="success" %}
No answer needed
{% endhint %}



## Task 13 <mark style="color:orange;background-color:orange;">Proxy</mark> Site Map and Issue Definitions

### Take a look around the site on `http://MACHINE_IP/` -- we will be using this a lot throughout the module. Visit every page linked to from the homepage, then check your sitemap -- one endpoint should stand out as being very unusual! Visit this in your browser (or use the "Response" section of the site map entry for that endpoint). What is the flag you receive?

{% hint style="warning" %}
**HINT:** You are looking for a suspicious page with a name made up of a series of random letters and numbers.
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`THM{NmNlZTliNGE1MWU1ZTQzMzgzNmFiNWVk}`

</details>



### Look through the Issue Definitions list. What is the typical severity of a Vulnerable JavaScript dependency?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Low`

</details>

\




## Task 14 <mark style="color:orange;background-color:yellow;">Practical</mark> Example Attack

### Try typing: `<script>alert("Succ3ssful XSS")</script>`, into the "Contact Email" field. You should find that there is a client-side filter in place which prevents you from adding any special characters that aren't allowed in email addresses:

{% hint style="success" %}
No answer needed
{% endhint %}

### Fortunately for us, client-side filters are absurdly easy to bypass. There are a variety of ways we could disable the script or just prevent it from loading in the first place. Let's focus on simply bypassing the filter for now. First, make sure that your Burp Proxy is active and that the intercept is on.

{% hint style="success" %}
No answer needed
{% endhint %}

### Now, enter some legitimate data into the support form. For example: "pentester@example.thm" as an email address, and "Test Attack" as a query. Submit the form -- the request should be intercepted by the proxy.

{% hint style="success" %}
No answer needed
{% endhint %}

### With the request captured in the proxy, we can now change the email field to be our very simple payload from above: `<script>alert("Succ3ssful XSS")</script>`. After pasting in the payload, we need to select it, then URL encode it with the `Ctrl + U` shortcut to make it safe to send.&#x20;

{% hint style="success" %}
No answer needed
{% endhint %}

### Finally, press the "Forward" button to send the request. You should find that you get an alert box from the site indicating a successful XSS attack!

{% hint style="success" %}
No answer needed
{% endhint %}

### Congratulations, you bypassed the filter! Don't expect it to be quite so easy in real life, but this should hopefully give you an idea of the kind of situation in which Burp Proxy can be useful.

{% hint style="success" %}
No answer needed
{% endhint %}



## Task 15 <mark style="color:green;background-color:green;">Conclusion</mark> Room Conclusion

{% embed url="https://tryhackme.com/room/burpsuiterepeater" %}
[https://tryhackme.com/room/burpsuiterepeater](https://tryhackme.com/room/burpsuiterepeater)
{% endembed %}

### I understand the fundamentals of using Burp Suite!

{% hint style="success" %}
No answer needed
{% endhint %}

