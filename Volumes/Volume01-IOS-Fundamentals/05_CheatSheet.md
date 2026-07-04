# IOS Fundamentals Cheat Sheet

---

**Volume:** 01 • IOS Fundamentals

**Estimated Reading Time:** 10 Minutes

---

## EXEC Mode Commands

| Command | Purpose |
|---------|---------|
| `enable` | Enter Privileged EXEC mode |
| `disable` | Return to User EXEC mode |
| `exit` | Exit the current mode |
| `end` | Return directly to Privileged EXEC mode |
| `logout` | Close the current session |
| `quit` | Close the current session |

---

## Configuration Commands

| Command | Purpose |
|---------|---------|
| `configure terminal` | Enter Global Configuration mode |
| `hostname NAME` | Configure the device hostname |
| `banner motd` | Configure the Message of the Day banner |
| `banner login` | Configure the login banner |
| `enable secret` | Configure the encrypted enable password |
| `enable password` | Configure the legacy enable password |
| `service password-encryption` | Encrypt plain-text passwords |
| `no ip domain-lookup` | Disable DNS lookup for invalid commands |
| `ip domain-name NAME` | Configure the default domain name |

---

## User Authentication

| Command | Purpose |
|---------|---------|
| `username USER secret PASS` | Create a local user |
| `password PASS` | Configure a line password |
| `login` | Enable password authentication |
| `login local` | Use the local user database |
| `line console 0` | Configure the console line |
| `line vty 0 4` | Configure VTY lines |
| `transport input ssh` | Allow SSH only |
| `exec-timeout` | Configure session timeout |
| `logging synchronous` | Prevent log messages from interrupting CLI |

---

## Configuration Management

| Command | Purpose |
|---------|---------|
| `copy running-config startup-config` | Save the running configuration |
| `write memory` | Save the running configuration |
| `erase startup-config` | Delete the startup configuration |
| `reload` | Restart the device |

---

## Verification Commands

| Command | Purpose |
|---------|---------|
| `show running-config` | Display the active configuration |
| `show startup-config` | Display the startup configuration |
| `show version` | Display system information |
| `show inventory` | Display hardware inventory |
| `show clock` | Display the system clock |
| `show users` | Display logged-in users |
| `show history` | Display command history |
| `show interfaces` | Display interface details |
| `show ip interface brief` | Display interface summary |
| `show ip route` | Display the routing table |
| `show arp` | Display the ARP table |
| `show mac address-table` | Display the MAC address table |
| `show cdp neighbors` | Display CDP neighbors |
| `show cdp neighbors detail` | Display detailed CDP information |
| `show lldp neighbors` | Display LLDP neighbors |
| `show lldp neighbors detail` | Display detailed LLDP information |
| `show processes cpu` | Display CPU utilization |
| `show memory statistics` | Display memory usage |
| `show logging` | Display system logs |
| `show flash` | Display flash memory contents |

---

## Terminal Commands

| Command | Purpose |
|---------|---------|
| `terminal length 0` | Disable output paging |
| `terminal width 132` | Set terminal width |
| `terminal history size 100` | Configure command history size |
| `terminal monitor` | Display log messages in remote sessions |
| `no terminal monitor` | Disable remote log messages |
| `show terminal` | Display terminal settings |
| `terminal editing` | Enable command-line editing |
| `terminal no editing` | Disable command-line editing |
| `terminal exec prompt timestamp` | Display timestamps in the prompt |
| `terminal datadump` | Disable paging and terminal formatting |

---

## Navigation

⬅️ Previous: **[04_Labs.md](04_Labs.md)**

➡️ Next: **[Volume 02 – Interface Configuration](../Volume02-Interface-Configuration/README.md)**
