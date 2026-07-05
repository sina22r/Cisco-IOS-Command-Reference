# IPv6 Verification Commands

---

**Volume:** 08 • IPv6

**Estimated Reading Time:** 50 Minutes

---

## Contents

- [show ipv6 interface brief](#show-ipv6-interface-brief)
- [show ipv6 interface](#show-ipv6-interface)
- [show ipv6 neighbors](#show-ipv6-neighbors)
- [show ipv6 route](#show-ipv6-route)
- [show ipv6 protocols](#show-ipv6-protocols)
- [show ipv6 cef](#show-ipv6-cef)
- [show ipv6 traffic](#show-ipv6-traffic)
- [show ipv6 access-list](#show-ipv6-access-list)
- [show running-config interface](#show-running-config-interface)
- [ping ipv6](#ping-ipv6)
- [traceroute ipv6](#traceroute-ipv6)

---

# show ipv6 interface brief

## Syntax:

    show ipv6 interface brief

## Example:

    R1# show ipv6 interface brief

    GigabitEthernet0/0    [up/up]
        FE80::1
        2001:DB8:10:1::1

    Loopback0             [up/up]
        FE80::2
        2001:DB8:100::1

## Description:

**Displays a summary of all IPv6-enabled interfaces,
including operational status, link-local addresses, and
global unicast addresses.**

------------------------------------------------------------

# show ipv6 interface

## Syntax:

    show ipv6 interface

## Example:

    R1# show ipv6 interface GigabitEthernet0/0

## Description:

**Displays detailed IPv6 information for an interface,
including configured addresses, Neighbor Discovery
parameters, Router Advertisement settings, MTU, and interface
status.**

------------------------------------------------------------

# show ipv6 neighbors

## Syntax:

    show ipv6 neighbors

## Example:

    R1# show ipv6 neighbors

    IPv6 Address                              Age Link-layer Addr State Interface
    FE80::2                                     18 001B.2B11.4401 REACH Gi0/0

## Description:

**Displays the IPv6 Neighbor Cache, showing the mapping
between IPv6 addresses and Layer 2 addresses learned through
Neighbor Discovery Protocol (NDP).**

------------------------------------------------------------

# show ipv6 route

## Syntax:

    show ipv6 route

## Example:

    R1# show ipv6 route

    C   2001:DB8:10:1::/64
         via GigabitEthernet0/0

    L   2001:DB8:10:1::1/128
         via GigabitEthernet0/0

## Description:

**Displays the IPv6 routing table, including connected,
local, static, and dynamically learned routes.**

------------------------------------------------------------

# show ipv6 protocols

## Syntax:

    show ipv6 protocols

## Example:

    R1# show ipv6 protocols

## Description:

**Displays information about active IPv6 routing protocols,
their timers, advertised networks, and interface
participation.**

------------------------------------------------------------

# show ipv6 cef

## Syntax:

    show ipv6 cef

## Example:

    R1# show ipv6 cef

## Description:

**Displays the Cisco Express Forwarding (CEF) table for IPv6,
including forwarding entries and next-hop information used
for hardware-accelerated packet switching.**

------------------------------------------------------------

# show ipv6 traffic

## Syntax:

    show ipv6 traffic

## Example:

    R1# show ipv6 traffic

## Description:

**Displays IPv6 traffic statistics, including transmitted and
received packets, Neighbor Discovery messages, ICMPv6
packets, and forwarding statistics.**

------------------------------------------------------------

# show ipv6 access-list

## Syntax:

    show ipv6 access-list

## Example:

    R1# show ipv6 access-list

## Description:

**Displays configured IPv6 Access Control Lists along with
their sequence numbers, matching rules, and packet counters.**

------------------------------------------------------------

# show running-config interface

## Syntax:

    show running-config interface INTERFACE

## Example:

    R1# show running-config interface GigabitEthernet0/0

## Description:

**Displays the active configuration of the specified
interface, including IPv6 addressing, Neighbor Discovery
settings, Router Advertisement parameters, and applied IPv6
Access Control Lists.**

------------------------------------------------------------

# ping ipv6

## Syntax:

    ping ipv6 IPV6_ADDRESS

## Example:

    R1# ping ipv6 2001:DB8:20:1::1

## Description:

**Tests IPv6 connectivity by sending ICMPv6 Echo Request
packets to a destination host and measuring the responses.**

------------------------------------------------------------

# traceroute ipv6

## Syntax:

    traceroute ipv6 IPV6_ADDRESS

## Example:

    R1# traceroute ipv6 2001:DB8:30:1::1

## Description:

**Displays the Layer 3 path to an IPv6 destination by sending
probe packets with increasing Hop Limit values. This command
helps identify routing paths and locate connectivity issues.**

------------------------------------------------------------

## IPv6 Verification Summary

These commands provide the primary tools for verifying IPv6
addressing, Neighbor Discovery, routing, forwarding,
interface status, and end-to-end connectivity on Cisco IOS
devices.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[01_IPv6_Configuration_Commands.md](01_IPv6_Configuration_Commands.md)**

➡️ Next: **[03_IPv6_Labs.md](03_IPv6_Labs.md)**
