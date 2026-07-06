# OSPF Configuration Commands

---

**Volume:** 12 • OSPF

**Estimated Reading Time:** 120 Minutes

---

## Contents

- [router ospf](#router-ospf)
- [router-id](#router-id)
- [network](#network)
- [passive-interface](#passive-interface)
- [no passive-interface](#no-passive-interface)
- [ip ospf area](#ip-ospf-area)
- [ipv6 ospf](#ipv6-ospf)
- [auto-cost reference-bandwidth](#auto-cost-reference-bandwidth)
- [ip ospf cost](#ip-ospf-cost)
- [default-information originate](#default-information-originate)
- [area range](#area-range)
- [summary-address](#summary-address)
- [area stub](#area-stub)
- [area nssa](#area-nssa)
- [area virtual-link](#area-virtual-link)
- [redistribute](#redistribute)
- [ip ospf authentication](#ip-ospf-authentication)
- [ip ospf authentication-key](#ip-ospf-authentication-key)
- [ip ospf message-digest-key](#ip-ospf-message-digest-key)
- [maximum-paths](#maximum-paths)

---

# router ospf

## Syntax

```
router ospf PROCESS_ID
```

## Example

```text
R1(config)# router ospf 10
```

## Description

**Starts an OSPFv2 routing process using the specified
process ID. The process ID is locally significant and does
not have to match between neighboring routers.**

------------------------------------------------------------

# router-id

## Syntax

```
router-id A.B.C.D
```

## Example

```text
R1(config-router)# router-id 1.1.1.1
```

## Description

**Manually configures the OSPF Router ID. If not specified,
Cisco IOS selects the highest loopback address or the
highest active physical interface address. Using a manually
configured Router ID is considered a best practice in
enterprise networks.**

------------------------------------------------------------

# network

## Syntax

```
network NETWORK WILDCARD area AREA_ID
```

## Example

```text
R1(config-router)# network 10.1.0.0 0.0.255.255 area 0
```

## Description

**Enables OSPF on interfaces matching the specified network
statement and assigns those interfaces to the specified
OSPF area.**

------------------------------------------------------------

# passive-interface

## Syntax

```
passive-interface INTERFACE
```

## Example

```text
R1(config-router)# passive-interface GigabitEthernet0/1
```

## Description

**Stops OSPF Hello packets from being transmitted on the
specified interface while continuing to advertise the
connected network through OSPF.**

------------------------------------------------------------

# no passive-interface

## Syntax

```
no passive-interface INTERFACE
```

## Example

```text
R1(config-router)# no passive-interface GigabitEthernet0/0
```

## Description

**Re-enables OSPF neighbor discovery and Hello packet
transmission on the specified interface.**

------------------------------------------------------------

# ip ospf area

## Syntax

```
ip ospf PROCESS_ID area AREA_ID
```

## Example

```text
R1(config-if)# ip ospf 10 area 0
```

## Description

**Enables OSPF directly on an interface without using network
statements. This interface-based configuration method is
commonly used in modern Cisco IOS deployments.**

------------------------------------------------------------

# ipv6 ospf

## Syntax

    ipv6 ospf PROCESS_ID area AREA_ID

## Example

    R1(config-if)# ipv6 ospf 10 area 0

## Description

**Enables OSPFv3 on the interface and assigns it to the
specified OSPF area. Unlike OSPFv2, OSPFv3 is configured
directly on interfaces instead of using network statements.**

------------------------------------------------------------

# auto-cost reference-bandwidth

## Syntax

    auto-cost reference-bandwidth BANDWIDTH_MBPS

## Example

    R1(config-router)# auto-cost reference-bandwidth 100000

## Description

**Changes the reference bandwidth used when calculating OSPF
interface costs. In modern networks this value should be
increased beyond the default 100 Mbps to accurately
differentiate high-speed interfaces such as Gigabit,
10-Gigabit, and faster Ethernet links.**

------------------------------------------------------------

# ip ospf cost

## Syntax

    ip ospf cost COST

## Example

    R1(config-if)# ip ospf cost 50

## Description

**Manually assigns the OSPF interface cost. Lower values are
preferred by the SPF algorithm when selecting the best path.**

------------------------------------------------------------

# default-information originate

## Syntax

    default-information originate

## Example

    R1(config-router)# default-information originate

## Description

**Injects a default route into the OSPF domain, provided a
default route exists in the routing table. Commonly used on
edge routers connected to the Internet or another upstream
network.**

------------------------------------------------------------

# area range

## Syntax

    area AREA_ID range NETWORK MASK

## Example

    R1(config-router)# area 1 range 10.10.0.0 255.255.0.0

## Description

**Configures route summarization on an Area Border Router
(ABR). Summarization reduces routing table size and limits
the number of LSAs exchanged between areas.**

------------------------------------------------------------

# summary-address

## Syntax

    summary-address NETWORK MASK

## Example

    R1(config-router)# summary-address 172.16.0.0 255.255.0.0

## Description

**Summarizes redistributed external routes on an Autonomous
System Boundary Router (ASBR). Unlike area range, this
command applies only to external LSAs.**

------------------------------------------------------------

# area stub

## Syntax

    area AREA_ID stub

## Example

    R1(config-router)# area 10 stub

## Description

**Configures the specified area as a Stub Area. Stub Areas
block Type 5 External LSAs and receive a default route from
the ABR instead.**

------------------------------------------------------------

# area nssa

## Syntax

    area AREA_ID nssa

## Example

    R1(config-router)# area 20 nssa

## Description

**Configures the specified area as a Not-So-Stubby Area
(NSSA). NSSAs allow redistribution of external routes while
still restricting Type 5 LSAs inside the area.**

------------------------------------------------------------

# area virtual-link

## Syntax

    area TRANSIT_AREA virtual-link ROUTER_ID

## Example

    R1(config-router)# area 1 virtual-link 2.2.2.2

## Description

**Creates an OSPF Virtual Link through a transit area in
order to logically reconnect an Area Border Router to Area
0. Virtual Links should generally be avoided unless required
by network design constraints.**

------------------------------------------------------------

# redistribute

## Syntax

    redistribute PROTOCOL

## Example

    R1(config-router)# redistribute static subnets

## Description

**Imports routes from another routing source into OSPF.
Redistribution should be carefully planned to prevent routing
loops and inconsistent path selection.**

------------------------------------------------------------

# ip ospf authentication

## Syntax

    ip ospf authentication

## Example

    R1(config-if)# ip ospf authentication

## Description

**Enables simple password authentication on the interface for
OSPF packets exchanged with neighboring routers.**

------------------------------------------------------------

# ip ospf authentication-key

## Syntax

    ip ospf authentication-key PASSWORD

## Example

    R1(config-if)# ip ospf authentication-key Cisco123

## Description

**Configures the plain-text authentication password used by
simple OSPF authentication.**

------------------------------------------------------------

# ip ospf message-digest-key

## Syntax

    ip ospf message-digest-key KEY_ID md5 PASSWORD

## Example

    R1(config-if)# ip ospf message-digest-key 1 md5 Cisco123

## Description

**Configures MD5 authentication for OSPF packets exchanged on
the interface. MD5 authentication provides stronger security
than simple password authentication and is recommended for
production environments.**

------------------------------------------------------------

# maximum-paths

## Syntax

    maximum-paths NUMBER

## Example

    R1(config-router)# maximum-paths 8

## Description

**Specifies the maximum number of equal-cost OSPF routes that
may be installed into the routing table for load balancing.**

------------------------------------------------------------

# log-adjacency-changes

## Syntax

    log-adjacency-changes

## Example

    R1(config-router)# log-adjacency-changes

## Description

**Generates syslog messages whenever an OSPF neighbor
adjacency changes state. This command is useful for
monitoring and troubleshooting OSPF stability.**

------------------------------------------------------------

# distance ospf

## Syntax

    distance ospf intra-area inter-area external

## Example

    R1(config-router)# distance ospf 110 115 120

## Description

**Changes the administrative distance for intra-area,
inter-area, and external OSPF routes independently.**

------------------------------------------------------------

# neighbor

## Syntax

    neighbor IP_ADDRESS

## Example

    R1(config-router)# neighbor 192.168.10.2

## Description

**Configures a manually defined OSPF neighbor. This command
is primarily required on NBMA networks such as Frame Relay
or ATM where multicast neighbor discovery is unavailable.**

------------------------------------------------------------

## OSPF Configuration Summary

OSPF deployments typically include Router IDs, Area
configuration, passive interfaces, authentication, cost
optimization, summarization, stub or NSSA areas, default
route injection, redistribution, and interface-based OSPFv3
configuration. Together these features provide scalable,
hierarchical, and highly resilient enterprise routing.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[README.md](README.md)**

➡️ Next: **[02_OSPF_Verification_Commands.md](02_OSPF_Verification_Commands.md)**
