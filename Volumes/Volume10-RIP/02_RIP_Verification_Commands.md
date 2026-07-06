# RIP Verification Commands

---

**Volume:** 10 • RIP

**Estimated Reading Time:** 45 Minutes

---

## Contents

- [show ip protocols](#show-ip-protocols)
- [show ip route rip](#show-ip-route-rip)
- [show ip rip database](#show-ip-rip-database)
- [show ip route](#show-ip-route)
- [show running-config | section router rip](#show-running-config--section-router-rip)
- [show ipv6 protocols](#show-ipv6-protocols)
- [show ipv6 route rip](#show-ipv6-route-rip)
- [show ipv6 rip database](#show-ipv6-rip-database)
- [show ipv6 route](#show-ipv6-route)
- [ping](#ping)
- [ping ipv6](#ping-ipv6)
- [traceroute](#traceroute)
- [traceroute ipv6](#traceroute-ipv6)
- [debug ip rip](#debug-ip-rip)
- [debug ipv6 rip](#debug-ipv6-rip)

---

# show ip protocols

## Syntax:

    show ip protocols

## Example:

    R1# show ip protocols

## Description:

**Displays the active routing protocols on the router,
including RIP version, timers, advertised networks,
redistributed routes, passive interfaces, and administrative
distance values.**

------------------------------------------------------------

# show ip route rip

## Syntax:

    show ip route rip

## Example:

    R1# show ip route rip

## Description:

**Displays only the routes learned through RIP. Routes learned
via RIP are identified with the route code `R`.**

------------------------------------------------------------

# show ip rip database

## Syntax:

    show ip rip database

## Example:

    R1# show ip rip database

## Description:

**Displays the RIP routing database, including learned
networks, metrics, timers, and next-hop information before
routes are installed into the routing table.**

------------------------------------------------------------

# show ip route

## Syntax:

    show ip route

## Example:

    R1# show ip route

## Description:

**Displays the complete IPv4 routing table. RIP-learned routes
appear with the route code `R`.**

------------------------------------------------------------

# show running-config | section router rip

## Syntax:

    show running-config | section router rip

## Example:

    R1# show running-config | section router rip

## Description:

**Displays the complete RIP configuration from the running
configuration, including networks, timers, redistribution,
and passive interfaces.**

------------------------------------------------------------

# show ipv6 protocols

## Syntax:

    show ipv6 protocols

## Example:

    R1# show ipv6 protocols

## Description:

**Displays IPv6 routing protocol information, including
configured RIPng processes and participating interfaces.**

------------------------------------------------------------

# show ipv6 route rip

## Syntax:

    show ipv6 route rip

## Example:

    R1# show ipv6 route rip

## Description:

**Displays only the IPv6 routes learned through RIPng.**

------------------------------------------------------------

# show ipv6 rip database

## Syntax:

    show ipv6 rip database

## Example:

    R1# show ipv6 rip database

## Description:

**Displays the RIPng routing database, including learned IPv6
prefixes, metrics, and timers.**

------------------------------------------------------------

# show ipv6 route

## Syntax:

    show ipv6 route

## Example:

    R1# show ipv6 route

## Description:

**Displays the complete IPv6 routing table, including RIPng
routes, connected routes, static routes, and local prefixes.**

------------------------------------------------------------

# ping

## Syntax:

    ping IP_ADDRESS

## Example:

    R1# ping 10.10.10.1

## Description:

**Verifies end-to-end IPv4 connectivity using routes learned
through RIP.**

------------------------------------------------------------

# ping ipv6

## Syntax:

    ping ipv6 IPV6_ADDRESS

## Example:

    R1# ping ipv6 2001:DB8:10::1

## Description:

**Verifies end-to-end IPv6 connectivity using RIPng-learned
routes.**

------------------------------------------------------------

# traceroute

## Syntax:

    traceroute IP_ADDRESS

## Example:

    R1# traceroute 10.10.10.1

## Description:

**Displays the IPv4 forwarding path and helps verify route
selection and hop-by-hop connectivity.**

------------------------------------------------------------

# traceroute ipv6

## Syntax:

    traceroute ipv6 IPV6_ADDRESS

## Example:

    R1# traceroute ipv6 2001:DB8:10::1

## Description:

**Displays the IPv6 forwarding path toward the destination,
allowing verification of RIPng routing decisions.**

------------------------------------------------------------

# debug ip rip

## Syntax:

    debug ip rip

## Example:

    R1# debug ip rip

## Description:

**Displays RIP update packets in real time, including route
advertisements, received updates, metrics, and timers. This
command should be used carefully because continuous debugging
can increase CPU utilization.**

------------------------------------------------------------

# debug ipv6 rip

## Syntax:

    debug ipv6 rip

## Example:

    R1# debug ipv6 rip

## Description:

**Displays RIPng routing updates and protocol events in real
time for troubleshooting IPv6 routing issues.**

------------------------------------------------------------

## RIP Verification Summary

These commands verify RIP and RIPng operation, routing
information, protocol status, route advertisements,
connectivity, and real-time routing updates.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[01_RIP_Configuration_Commands.md](01_RIP_Configuration_Commands.md)**

➡️ Next: **[03_RIP_Labs.md](03_RIP_Labs.md)**
