# IPv4 Verification Commands

---

**Volume:** 07 • IPv4

**Estimated Reading Time:** 45 Minutes

---

## Contents

- [show ip interface brief](#show-ip-interface-brief)
- [show ip interface](#show-ip-interface)
- [show ip protocols](#show-ip-protocols)
- [show ip route](#show-ip-route)
- [show ip arp](#show-ip-arp)
- [show arp](#show-arp)
- [show hosts](#show-hosts)
- [show running-config interface](#show-running-config-interface)

---

# show ip interface brief

## Syntax:

    show ip interface brief

## Example:

    R1# show ip interface brief

    Interface              IP-Address      OK? Method Status                Protocol
    GigabitEthernet0/0     192.168.10.1    YES manual up                    up
    GigabitEthernet0/1     unassigned      YES unset  administratively down down
    Loopback0              10.10.10.1      YES manual up                    up

## Description:

**Displays a concise summary of all Layer 3 interfaces,
including IPv4 addresses, address assignment method,
administrative status, and line protocol state. This is one
of the most frequently used verification commands in Cisco
IOS.**

------------------------------------------------------------

# show ip interface

## Syntax:

    show ip interface

## Example:

    R1# show ip interface

## Description:

**Displays detailed IPv4 information for every Layer 3
interface, including addressing, MTU, helper addresses,
Proxy ARP, ICMP redirects, access lists, and interface
status.**

------------------------------------------------------------

# show ip protocols

## Syntax:

    show ip protocols

## Example:

    R1# show ip protocols

## Description:

**Displays information about all active IPv4 routing
protocols, including timers, routing updates, passive
interfaces, and network advertisements. If no routing
protocol is configured, minimal information is displayed.**

------------------------------------------------------------

# show ip route

## Syntax:

    show ip route

## Example:

    R1# show ip route

## Description:

**Displays the IPv4 routing table, including directly
connected, static, and dynamically learned routes. It also
identifies the routing source and administrative distance
for each route.**

------------------------------------------------------------

# IPv4 Verification Commands

---

**Volume:** 07 • IPv4

**Estimated Reading Time:** 45 Minutes

---

## Contents

- [show ip interface brief](#show-ip-interface-brief)
- [show ip interface](#show-ip-interface)
- [show ip protocols](#show-ip-protocols)
- [show ip route](#show-ip-route)
- [show ip arp](#show-ip-arp)
- [show arp](#show-arp)
- [show hosts](#show-hosts)
- [show running-config interface](#show-running-config-interface)

---

# show ip interface brief

## Syntax:

    show ip interface brief

## Example:

    R1# show ip interface brief

    Interface              IP-Address      OK? Method Status                Protocol
    GigabitEthernet0/0     192.168.10.1    YES manual up                    up
    GigabitEthernet0/1     unassigned      YES unset  administratively down down
    Loopback0              10.10.10.1      YES manual up                    up

## Description:

**Displays a concise summary of all Layer 3 interfaces,
including IPv4 addresses, address assignment method,
administrative status, and line protocol state. This is one
of the most frequently used verification commands in Cisco
IOS.**

------------------------------------------------------------

# show ip interface

## Syntax:

    show ip interface

## Example:

    R1# show ip interface

## Description:

**Displays detailed IPv4 information for every Layer 3
interface, including addressing, MTU, helper addresses,
Proxy ARP, ICMP redirects, access lists, and interface
status.**

------------------------------------------------------------

# show ip protocols

## Syntax:

    show ip protocols

## Example:

    R1# show ip protocols

## Description:

**Displays information about all active IPv4 routing
protocols, including timers, routing updates, passive
interfaces, and network advertisements. If no routing
protocol is configured, minimal information is displayed.**

------------------------------------------------------------

# show ip route

## Syntax:

    show ip route

## Example:

    R1# show ip route

## Description:

**Displays the IPv4 routing table, including directly
connected, static, and dynamically learned routes. It also
identifies the routing source and administrative distance
for each route.**

------------------------------------------------------------

# show ip cef

## Syntax:

    show ip cef

## Example:

    R1# show ip cef

## Description:

**Displays the Cisco Express Forwarding (CEF) table,
including destination prefixes, next-hop information, and
forwarding entries used for high-performance packet
switching.**

------------------------------------------------------------

# show ip cef exact-route

## Syntax:

    show ip cef exact-route SOURCE_IP DESTINATION_IP

## Example:

    R1# show ip cef exact-route 192.168.10.10 10.10.10.10

## Description:

**Displays the exact forwarding decision that Cisco Express
Forwarding (CEF) will use for traffic between a specific
source and destination address.**

------------------------------------------------------------

## IPv4 Verification Summary

The commands in this file provide the primary tools for
verifying IPv4 interface configuration, routing
functionality, address resolution, forwarding behavior, and
end-to-end connectivity on Cisco IOS devices.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[01_IPv4_Configuration_Commands.md](01_IPv4_Configuration_Commands.md)**

➡️ Next: **[03_IPv4_Labs.md](03_IPv4_Labs.md)**
