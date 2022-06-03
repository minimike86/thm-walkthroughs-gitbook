# Task 11 - Working with the NSE

## Task 11 <mark style="color:orange;background-color:orange;">NSE Scripts</mark> Working with the NSE

### What optional argument can the <mark style="color:red;background-color:red;">ftp-anon.nse</mark> script take?

{% code title="ftp-anon.nse | line:19-22" %}
```lua
-- @args ftp-anon.maxlist The maximum number of files to return in the
-- directory listing. By default it is 20, or unlimited if verbosity is
-- enabled. Use a negative number to disable the limit, or
-- <code>0</code> to disable the listing entirely.
```
{% endcode %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`maxlist`

</details>
