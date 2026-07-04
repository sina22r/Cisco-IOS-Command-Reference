# Verification Commands

---

**Volume:** 01 • IOS Fundamentals

**Estimated Reading Time:** 40 Minutes

---

## Contents

- [show running-config](#show-running-config)
- [show startup-config](#show-startup-config)
- [show version](#show-version)
- [show inventory](#show-inventory)
- [show clock](#show-clock)
- [show users](#show-users)
- [show history](#show-history)
- [show interfaces](#show-interfaces)
- [show ip interface brief](#show-ip-interface-brief)
- [show ip route](#show-ip-route)
- [show arp](#show-arp)
- [show mac address-table](#show-mac-address-table)
- [show cdp neighbors](#show-cdp-neighbors)
- [show cdp neighbors detail](#show-cdp-neighbors-detail)
- [show lldp neighbors](#show-lldp-neighbors)
- [show lldp neighbors detail](#show-lldp-neighbors-detail)
- [show processes cpu](#show-processes-cpu)
- [show memory statistics](#show-memory-statistics)
- [show logging](#show-logging)
- [show flash](#show-flash)

---

# show running-config

## Syntax

    show running-config

## Example

    R1# show running-config

## Description

    Displays the current active configuration stored in RAM.
    Any configuration changes take effect immediately in the
    running configuration.

------------------------------------------------------------

# show startup-config

## Syntax

    show startup-config

## Example

    R1# show startup-config

## Description

    Displays the configuration stored in NVRAM that will be
    loaded during the next device boot.

------------------------------------------------------------

# show version

## Syntax

    show version

## Example

    R1# show version

## Description

    Displays Cisco IOS software version, device model,
    uptime, memory information, configuration register,
    and other system details.

------------------------------------------------------------

# show inventory

## Syntax

    show inventory

## Example

    R1# show inventory

## Description

    Displays hardware inventory information, including
    installed modules, product IDs, serial numbers,
    and hardware descriptions.

------------------------------------------------------------

# show clock

## Syntax

    show clock

## Example

    R1# show clock

    *10:35:42.681 UTC Mon Jul 6 2026

## Description

    Displays the current system date and time configured
    on the device.

------------------------------------------------------------

# show users

## Syntax

    show users

## Example

    R1# show users

## Description

    Displays all users currently connected to the device,
    including the terminal line they are using.

------------------------------------------------------------

# show history

## Syntax

    show history

## Example

    R1# show history

## Description

    Displays the command history for the current CLI session,
    allowing previously entered commands to be reviewed.

------------------------------------------------------------

# show interfaces

## Syntax

    show interfaces

## Example

    R1# show interfaces

## Description

    Displays detailed information about all interfaces,
    including status, bandwidth, errors, counters,
    encapsulation, and traffic statistics.

------------------------------------------------------------

# show ip interface brief

## Syntax

    show ip interface brief

## Example

    R1# show ip interface brief

    Interface              IP-Address      OK? Method Status Protocol
    GigabitEthernet0/0     10.10.10.1      YES manual up     up
    GigabitEthernet0/1     unassigned      YES unset  down   down

## Description

    Displays a summarized list of Layer 3 interfaces,
    including IP addresses, administrative status,
    and line protocol state.

------------------------------------------------------------

# show ip route

## Syntax

    show ip route

## Example

    R1# show ip route

## Description

    Displays the IPv4 routing table, including directly
    connected networks, static routes, and dynamically
    learned routes.

------------------------------------------------------------

# show arp

## Syntax

    show arp

## Example

    R1# show arp

    Protocol  Address          Age (min)  Hardware Addr   Type   Interface
    Internet  10.10.10.2       2          0019.E752.1234  ARPA   GigabitEthernet0/0

## Description

    Displays the Address Resolution Protocol (ARP) table,
    including IPv4-to-MAC address mappings learned by the
    device.

------------------------------------------------------------

# show mac address-table

## Syntax

    show mac address-table

## Example

    SW1# show mac address-table

## Description

    Displays the MAC address table learned by the switch,
    including VLAN information, interface mappings, and
    address types.

------------------------------------------------------------

# show cdp neighbors

## Syntax

    show cdp neighbors

## Example

    R1# show cdp neighbors

## Description

    Displays directly connected Cisco devices discovered
    through Cisco Discovery Protocol (CDP).

------------------------------------------------------------

# show cdp neighbors detail

## Syntax

    show cdp neighbors detail

## Example

    R1# show cdp neighbors detail

## Description

    Displays detailed information about neighboring Cisco
    devices, including IP addresses, platform information,
    software version, and interface details.

------------------------------------------------------------

# show lldp neighbors

## Syntax

    show lldp neighbors

## Example

    SW1# show lldp neighbors

## Description

    Displays neighboring devices discovered through the
    Link Layer Discovery Protocol (LLDP), regardless of
    vendor.

------------------------------------------------------------

# show lldp neighbors detail

## Syntax

    show lldp neighbors detail

## Example

    SW1# show lldp neighbors detail

## Description

    Displays detailed LLDP information about neighboring
    devices, including management addresses, capabilities,
    and interface information.

------------------------------------------------------------

# show processes cpu

## Syntax

    show processes cpu

## Example

    R1# show processes cpu

## Description

    Displays CPU utilization statistics and the processes
    currently consuming processor resources.

------------------------------------------------------------

# show memory statistics

## Syntax

    show memory statistics

## Example

    R1# show memory statistics

## Description

    Displays memory utilization statistics, including used,
    free, and allocated memory information.

------------------------------------------------------------

# show logging

## Syntax

    show logging

## Example

    R1# show logging

## Description

    Displays the device log buffer, including system events,
    warnings, errors, and informational messages.

------------------------------------------------------------

# show flash

## Syntax

    show flash

## Example

    R1# show flash

## Description

    Displays the contents of flash memory, including IOS
    images, configuration files, and available storage
    capacity.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[01_Basic_IOS_Commands.md](01_Basic_IOS_Commands.md)**

➡️ Next: **[03_Terminal_Commands.md](03_Terminal_Commands.md)**
