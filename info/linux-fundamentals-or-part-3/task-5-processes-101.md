# Task 5 - Processes 101

## Task 5 Processes 101

### Read me!

{% hint style="success" %}
No answer needed
{% endhint %}

### If we were to launch a process where the previous ID was "300", what would the ID of this new process be?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`301`

</details>

### If we wanted to **cleanly** kill a process, what signal would we send it?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`SIGTERM`

</details>

### Locate the process that is running on the deployed instance (MACHINE\_IP). What flag is given?

{% hint style="warning" %}
**HINT:** Use ps aux to list all running processes. We're looking for a process that seems "out of the ordinary"
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`THM{PROCESSES}`

</details>

### What command would we use to stop the service "myservice"?

{% hint style="warning" %}
**HINT:** systemctl \[option] \[service]
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`systemctl stop myservice`

</details>

### What command would we use to start the same service on the boot-up of the system?

{% hint style="warning" %}
**HINT:** systemctl \[option] \[service]
{% endhint %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`systemctl enable myservice`

</details>

### What command would we use to bring a previously backgrounded process back to the foreground?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`fg`

</details>
