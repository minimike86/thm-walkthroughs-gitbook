---
description: Learn how to use Repeater to duplicate requests in Burp Suite
---

# 🟧 Burp Suite: Repeater

{% embed url="https://tryhackme.com/room/burpsuiterepeater" %}
[https://tryhackme.com/room/burpsuiterepeater](https://tryhackme.com/room/burpsuiterepeater)
{% endembed %}



| Room Attributes       | Value                                                                   |
| --------------------- | ----------------------------------------------------------------------- |
| Subscription Required |  <mark style="color:green;background-color:green;">False</mark> \[Free] |
| Type                  | Walkthrough                                                             |
| Difficulty            |  <mark style="color:blue;background-color:blue;">Info</mark>            |
| Tags                  | Burp Suite, Repeater, Tutorial, Walkthrough                             |



## Task 1 - <mark style="color:green;background-color:green;">Introduction</mark> Outline

### Deploy the machine (and the AttackBox if you are not using your own attack VM), and let's get started!

{% hint style="info" %}
_**Note:** If you are not using the AttackBox and want to connect to this machine without the VPN, you can do so using this link once the machine has fully loaded and an IP address is displayed:_ `https://LAB_WEB_URL.p.thmlabs.com`_._
{% endhint %}

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 2 - <mark style="color:orange;background-color:orange;">Repeater</mark> What is Repeater?

### Familiarise yourself with the Repeater interface.

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 3 - <mark style="color:orange;background-color:orange;">Repeater</mark> Basic Usage

### Capture a request to `http://MACHINE_IP` in the Proxy and send it to Repeater. Practice modifying and re-sending the request numerous times.

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 4 - <mark style="color:orange;background-color:orange;">Repeater</mark> Views

### Experiment with the available view options.

{% hint style="success" %}
No answer needed
{% endhint %}

### Which view option displays the response in the same format as your browser would?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`Render`

</details>

## Task 5 - <mark style="color:orange;background-color:orange;">Repeater</mark> Inspector

### Get comfortable with Inspector and practice adding/removing items from the various request sections.

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 6 - <mark style="color:orange;background-color:yellow;">Practical</mark> Example

### Capture a request to `http://MACHINE_IP/` in the Proxy and send it to Repeater.

{% hint style="success" %}
No answer needed
{% endhint %}

### Send the request once from Repeater -- you should see the HTML source code for the page you requested in the response tab. Try viewing this in one of the other view options (e.g. Rendered).

{% hint style="success" %}
No answer needed
{% endhint %}

### Using Inspector (or manually, if you prefer), add a header called `FlagAuthorised` and set it to have a value of `True`. e.g.: Headers with FlagAuthorised Added. Send the request. What is the flag you receive?

{% hint style="warning" %}
**HINT:** Make sure you leave the two blank lines at the bottom of the request!
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`THM{Yzg2MWI2ZDhlYzdlNGFiZTUzZTIzMzVi}`

</details>

## Task 7 - <mark style="color:orange;background-color:yellow;">Practical</mark> Challenge

### Capture a request to one of the numeric products endpoints in the Proxy, then forward it to Repeater.

{% hint style="success" %}
No answer needed
{% endhint %}

### See if you can get the server to error out with a "500 Internal Server Error" code by changing the number at the end of the request to extreme inputs. What is the flag you receive when you cause a 500 error in the endpoint?

{% hint style="warning" %}
**HINT:** The idea here is to enter unexpected inputs to see how the server will react. For example, instead of a number you could enter a piece of text, or a symbol. Alternatively, you could try entering a number greater than the number of products available (e.g. 1000), or a number less than or equal to 0.
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`THM{N2MzMzFhMTA1MmZiYjA2YWQ4M2ZmMzhl}`

</details>

## Task 8 - <mark style="color:red;background-color:red;">Extra Mile</mark> SQLi with Repeater

### Once you have captured the request, send it to Repeater with `Ctrl + R` or by right-clicking and choosing "Send to Repeater".

{% hint style="success" %}
No answer needed
{% endhint %}

### You should see that the server responds with a "500 Internal Server Error", indicating that we successfully broke the query.

{% hint style="success" %}
No answer needed
{% endhint %}

### With this information, we can skip over the query column number and table name enumeration steps.

{% hint style="success" %}
No answer needed
{% endhint %}

### Looking through the returned response, we can see that the first column name (`id`) has been inserted into the page title.

{% hint style="success" %}
No answer needed
{% endhint %}

### This process is shown in below

{% hint style="success" %}
No answer needed
{% endhint %}

### Hey presto, we have a flag!

{% hint style="success" %}
No answer needed
{% endhint %}

### Exploit the union SQL injection vulnerability in the site. What is the flag?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`THM{ZGE3OTUyZGMyMzkwNjJmZjg3Mzk1NjJh}`

</details>

## Task 9 - <mark style="color:green;background-color:green;">Conclusion</mark> Room Conclusion

### I can use Burp Suite Repeater!

{% hint style="success" %}
No answer needed
{% endhint %}

