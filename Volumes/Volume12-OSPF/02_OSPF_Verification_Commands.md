# OSPF Verification Commands

---

**Volume:** 12 • OSPF

**Estimated Reading Time:** 60 Minutes

---

## Contents

- [show ip ospf](#show-ip-ospf)
- [show ipv6 ospf](#show-ipv6-ospf)
- [show ip ospf neighbor](#show-ip-ospf-neighbor)
- [show ipv6 ospf neighbor](#show-ipv6-ospf-neighbor)
- [show ip ospf interface](#show-ip-ospf-interface)
- [show ipv6 ospf interface](#show-ipv6-ospf-interface)
- [show ip ospf database](#show-ip-ospf-database)
- [show ipv6 ospf database](#show-ipv6-ospf-database)
- [show ip route ospf](#show-ip-route-ospf)
- [show ipv6 route ospf](#show-ipv6-route-ospf)
- [show ip protocols](#show-ip-protocols)
- [show running-config \| section router ospf](#show-running-config--section-router-ospf)
- [ping](#ping)
- [ping ipv6](#ping-ipv6)
- [traceroute](#traceroute)
- [traceroute ipv6](#traceroute-ipv6)
- [debug ip ospf adj](#debug-ip-ospf-adj)
- [debug ip ospf hello](#debug-ip-ospf-hello)
- [debug ip ospf events](#debug-ip-ospf-events)
- [debug ip ospf spf](#debug-ip-ospf-spf)

---

# show ip ospf

## Syntax

    show ip ospf

## Example

    R1# show ip ospf

## Description

**Displays general OSPF process information including the
Router ID, SPF statistics, reference bandwidth, area
configuration, and LSA generation timers.**

------------------------------------------------------------

# show ipv6 ospf

## Syntax

    show ipv6 ospf

## Example

    R1# show ipv6 ospf

## Description

**Displays general information about the OSPFv3 routing
process, including Router ID, configured areas, interfaces,
and SPF calculation statistics.**

------------------------------------------------------------

# show ip ospf neighbor

## Syntax

    show ip ospf neighbor

## Example

    R1# show ip ospf neighbor

## Description

**Displays OSPF neighbor adjacencies, including Router IDs,
neighbor states, priorities, dead timers, designated router
information, and interface associations.**

------------------------------------------------------------

# show ipv6 ospf neighbor

## Syntax

    show ipv6 ospf neighbor

## Example

    R1# show ipv6 ospf neighbor

## Description

**Displays OSPFv3 neighbor relationships established for
IPv6 routing.**

------------------------------------------------------------

# show ip ospf interface

## Syntax

    show ip ospf interface

## Example

    R1# show ip ospf interface

## Description

**Displays OSPF operational parameters for each interface,
including area assignments, network type, Hello and Dead
timers, interface cost, authentication settings, and DR/BDR
status.**

------------------------------------------------------------

# show ipv6 ospf interface

## Syntax

    show ipv6 ospf interface

## Example

    R1# show ipv6 ospf interface

## Description

**Displays OSPFv3 interface information, including area
membership, costs, timers, and adjacency status.**

------------------------------------------------------------

# show ip ospf database

## Syntax

    show ip ospf database

## Example

    R1# show ip ospf database

## Description

**Displays the Link-State Database (LSDB), including Router,
Network, Summary, ASBR Summary, NSSA, and External LSAs used
by the SPF algorithm.**

------------------------------------------------------------

# show ipv6 ospf database

## Syntax

    show ipv6 ospf database

## Example

    R1# show ipv6 ospf database

## Description

**Displays the OSPFv3 Link-State Database used to construct
the IPv6 routing topology.**

------------------------------------------------------------

# show ip route ospf

## Syntax

    show ip route ospf

## Example

    R1# show ip route ospf

## Description

**Displays only routes learned through OSPF. OSPF routes are
identified by route codes such as `O`, `O IA`, `O E1`, `O E2`,
`O N1`, and `O N2`.**

------------------------------------------------------------

# show ipv6 route ospf

## Syntax

    show ipv6 route ospf

## Example

    R1# show ipv6 route ospf

## Description

**Displays only IPv6 routes learned through OSPFv3.**

------------------------------------------------------------

# show ip protocols

## Syntax

    show ip protocols

## Example

    R1# show ip protocols

## Description

**Displays OSPF process information, configured networks,
passive interfaces, route redistribution settings, and
administrative distance values.**

------------------------------------------------------------

# show running-config | section router ospf

## Syntax

    show running-config | section router ospf

## Example

    R1# show running-config | section router ospf

## Description

**Displays the complete OSPF routing process configuration
from the running configuration.**

------------------------------------------------------------

# ping

## Syntax

    ping IP_ADDRESS

## Example

    R1# ping 10.10.20.1

## Description

**Verifies IPv4 connectivity using routes learned through
OSPF.**

------------------------------------------------------------

# ping ipv6

## Syntax

    ping ipv6 IPV6_ADDRESS

## Example

    R1# ping ipv6 2001:DB8:20::1

## Description

**Verifies IPv6 connectivity using OSPFv3-learned routes.**

------------------------------------------------------------

# traceroute

## Syntax

    traceroute IP_ADDRESS

## Example

    R1# traceroute 10.10.20.1

## Description

**Displays the Layer 3 forwarding path selected by the OSPF
routing table.**

------------------------------------------------------------

# traceroute ipv6

## Syntax

    traceroute ipv6 IPV6_ADDRESS

## Example

    R1# traceroute ipv6 2001:DB8:20::1

## Description

**Displays the forwarding path selected by OSPFv3.**

------------------------------------------------------------

# debug ip ospf adj

## Syntax

    debug ip ospf adj

## Example

    R1# debug ip ospf adj

## Description

**Displays neighbor adjacency formation, state transitions,
and adjacency failures during OSPF operation.**

------------------------------------------------------------

# debug ip ospf hello

## Syntax

    debug ip ospf hello

## Example

    R1# debug ip ospf hello

## Description

**Displays transmitted and received Hello packets, allowing
verification of neighbor discovery and timer consistency.**

------------------------------------------------------------

# debug ip ospf events

## Syntax

    debug ip ospf events

## Example

    R1# debug ip ospf events

## Description

**Displays significant OSPF protocol events, including LSA
generation, flooding, SPF recalculations, and neighbor
changes.**

------------------------------------------------------------

# debug ip ospf spf

## Syntax

    debug ip ospf spf

## Example

    R1# debug ip ospf spf

## Description

**Displays Shortest Path First (SPF) calculations performed
after topology changes. This command is valuable when
troubleshooting convergence issues but should be used
carefully on production routers due to CPU utilization.**

------------------------------------------------------------

## OSPF Verification Summary

These commands verify OSPF process status, neighbor
adjacencies, interface parameters, LSDB contents, routing
tables, connectivity, and SPF calculations for both OSPFv2
and OSPFv3 deployments.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[01_OSPF_Configuration_Commands.md](01_OSPF_Configuration_Commands.md)**

➡️ Next: **[03_OSPF_Labs.md](03_OSPF_Labs.md)**
