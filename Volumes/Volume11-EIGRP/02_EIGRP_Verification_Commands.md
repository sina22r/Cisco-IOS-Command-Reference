# EIGRP Verification Commands

---

**Volume:** 11 • EIGRP

**Estimated Reading Time:** 50 Minutes

---

## Contents

- [show ip eigrp neighbors](#show-ip-eigrp-neighbors)
- [show ipv6 eigrp neighbors](#show-ipv6-eigrp-neighbors)
- [show ip eigrp topology](#show-ip-eigrp-topology)
- [show ipv6 eigrp topology](#show-ipv6-eigrp-topology)
- [show ip protocols](#show-ip-protocols)
- [show ip route eigrp](#show-ip-route-eigrp)
- [show ipv6 route eigrp](#show-ipv6-route-eigrp)
- [show running-config | section router eigrp](#show-running-config--section-router-eigrp)
- [show running-config | section router eigrp NAME](#show-running-config--section-router-eigrp-name)
- [show ip eigrp interfaces](#show-ip-eigrp-interfaces)
- [show ipv6 eigrp interfaces](#show-ipv6-eigrp-interfaces)
- [show ip eigrp traffic](#show-ip-eigrp-traffic)
- [ping](#ping)
- [ping ipv6](#ping-ipv6)
- [traceroute](#traceroute)
- [traceroute ipv6](#traceroute-ipv6)
- [debug eigrp packets](#debug-eigrp-packets)
- [debug eigrp neighbors](#debug-eigrp-neighbors)
- [debug ip eigrp](#debug-ip-eigrp)

---

# show ip eigrp neighbors

## Syntax:

    show ip eigrp neighbors

## Example:

    R1# show ip eigrp neighbors

## Description:

**Displays all IPv4 EIGRP neighbor adjacencies, including
neighbor addresses, hold timers, uptime, sequence numbers,
and the interfaces over which neighbors are reachable.**

------------------------------------------------------------

# show ipv6 eigrp neighbors

## Syntax:

    show ipv6 eigrp neighbors

## Example:

    R1# show ipv6 eigrp neighbors

## Description:

**Displays all IPv6 EIGRP neighbor adjacencies established
through EIGRP for IPv6.**

------------------------------------------------------------

# show ip eigrp topology

## Syntax:

    show ip eigrp topology

## Example:

    R1# show ip eigrp topology

## Description:

**Displays the EIGRP topology table, including successor and
feasible successor routes, reported distances, feasible
distances, and route states maintained by the DUAL
algorithm.**

------------------------------------------------------------

# show ipv6 eigrp topology

## Syntax:

    show ipv6 eigrp topology

## Example:

    R1# show ipv6 eigrp topology

## Description:

**Displays the IPv6 EIGRP topology table used by the DUAL
algorithm for route computation.**

------------------------------------------------------------

# show ip protocols

## Syntax:

    show ip protocols

## Example:

    R1# show ip protocols

## Description:

**Displays EIGRP process information, configured networks,
timers, passive interfaces, administrative distance values,
and route redistribution settings.**

------------------------------------------------------------

# show ip route eigrp

## Syntax:

    show ip route eigrp

## Example:

    R1# show ip route eigrp

## Description:

**Displays only routes learned through EIGRP. EIGRP routes
are identified by the route code `D`.**

------------------------------------------------------------

# show ipv6 route eigrp

## Syntax:

    show ipv6 route eigrp

## Example:

    R1# show ipv6 route eigrp

## Description:

**Displays only IPv6 routes learned through EIGRP for IPv6.**

------------------------------------------------------------

# show running-config | section router eigrp

## Syntax:

    show running-config | section router eigrp

## Example:

    R1# show running-config | section router eigrp

## Description:

**Displays the complete Classic Mode EIGRP configuration from
the running configuration.**

------------------------------------------------------------

# show running-config | section router eigrp NAME

## Syntax:

    show running-config | section router eigrp NAME

## Example:

    R1# show running-config | section router eigrp ENTERPRISE

## Description:

**Displays the complete Named Mode EIGRP configuration,
including address families, topology settings, and interface
configuration.**

------------------------------------------------------------

# show ip eigrp interfaces

## Syntax:

    show ip eigrp interfaces

## Example:

    R1# show ip eigrp interfaces

## Description:

**Displays all IPv4 interfaces participating in EIGRP,
including timers, packet statistics, and interface status.**

------------------------------------------------------------

# show ipv6 eigrp interfaces

## Syntax:

    show ipv6 eigrp interfaces

## Example:

    R1# show ipv6 eigrp interfaces

## Description:

**Displays IPv6 interfaces participating in the EIGRP for
IPv6 process.**

------------------------------------------------------------

# show ip eigrp traffic

## Syntax:

    show ip eigrp traffic

## Example:

    R1# show ip eigrp traffic

## Description:

**Displays EIGRP packet statistics, including Hello,
Update, Query, Reply, SIA Query, and SIA Reply packet
counters.**

------------------------------------------------------------

# ping

## Syntax:

    ping IP_ADDRESS

## Example:

    R1# ping 10.20.20.1

## Description:

**Verifies IPv4 connectivity through routes learned by
EIGRP.**

------------------------------------------------------------

# ping ipv6

## Syntax:

    ping ipv6 IPV6_ADDRESS

## Example:

    R1# ping ipv6 2001:DB8:20::1

## Description:

**Verifies IPv6 connectivity through EIGRP for IPv6.**

------------------------------------------------------------

# traceroute

## Syntax:

    traceroute IP_ADDRESS

## Example:

    R1# traceroute 10.20.20.1

## Description:

**Displays the Layer 3 forwarding path selected through the
EIGRP routing table.**

------------------------------------------------------------

# traceroute ipv6

## Syntax:

    traceroute ipv6 IPV6_ADDRESS

## Example:

    R1# traceroute ipv6 2001:DB8:20::1

## Description:

**Displays the forwarding path selected by EIGRP for IPv6.**

------------------------------------------------------------

# debug eigrp packets

## Syntax:

    debug eigrp packets

## Example:

    R1# debug eigrp packets

## Description:

**Displays EIGRP packet exchanges in real time, including
Hello, Update, Query, Reply, ACK, and SIA packets.**

------------------------------------------------------------

# debug eigrp neighbors

## Syntax:

    debug eigrp neighbors

## Example:

    R1# debug eigrp neighbors

## Description:

**Displays neighbor adjacency events, including neighbor
formation, resets, hold timer expiration, and adjacency
loss.**

------------------------------------------------------------

# debug ip eigrp

## Syntax:

    debug ip eigrp

## Example:

    R1# debug ip eigrp

## Description:

**Displays detailed EIGRP protocol events for IPv4,
including route calculations performed by the DUAL
algorithm. Debug commands should be used carefully in
production environments because they may increase CPU
utilization.**

------------------------------------------------------------

## EIGRP Verification Summary

These commands verify neighbor adjacencies, topology tables,
routing information, interface participation, packet
statistics, and DUAL operation for both IPv4 and IPv6 EIGRP
deployments.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[01_EIGRP_Configuration_Commands.md](01_EIGRP_Configuration_Commands.md)**

➡️ Next: **[03_EIGRP_Labs.md](03_EIGRP_Labs.md)**
