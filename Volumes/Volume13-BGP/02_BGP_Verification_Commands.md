# BGP Verification Commands

---

**Volume:** 13 • Border Gateway Protocol (BGP)

**Estimated Reading Time:** 90 Minutes

---

## Contents

- [show ip bgp](#show-ip-bgp)
- [show bgp ipv4 unicast](#show-bgp-ipv4-unicast)
- [show bgp ipv6 unicast](#show-bgp-ipv6-unicast)
- [show ip bgp summary](#show-ip-bgp-summary)
- [show bgp ipv4 unicast summary](#show-bgp-ipv4-unicast-summary)
- [show bgp ipv6 unicast summary](#show-bgp-ipv6-unicast-summary)
- [show ip bgp neighbors](#show-ip-bgp-neighbors)
- [show bgp ipv4 unicast neighbors](#show-bgp-ipv4-unicast-neighbors)
- [show bgp ipv6 unicast neighbors](#show-bgp-ipv6-unicast-neighbors)
- [show ip bgp neighbors received-routes](#show-ip-bgp-neighbors-received-routes)
- [show ip bgp neighbors advertised-routes](#show-ip-bgp-neighbors-advertised-routes)
- [show ip bgp neighbors routes](#show-ip-bgp-neighbors-routes)
- [show ip bgp regexp](#show-ip-bgp-regexp)
- [show ip bgp community](#show-ip-bgp-community)
- [show ip bgp flap-statistics](#show-ip-bgp-flap-statistics)
- [show ip bgp dampening parameters](#show-ip-bgp-dampening-parameters)
- [show ip bgp path-attributes](#show-ip-bgp-path-attributes)
- [show ip bgp cidr-only](#show-ip-bgp-cidr-only)
- [show ip bgp inconsistent-as](#show-ip-bgp-inconsistent-as)
- [show ip bgp peer-group](#show-ip-bgp-peer-group)
- [show ip bgp vpnv4 all](#show-ip-bgp-vpnv4-all)
- [show ip route bgp](#show-ip-route-bgp)
- [show ipv6 route bgp](#show-ipv6-route-bgp)
- [show ip protocols](#show-ip-protocols)
- [show running-config \| section router bgp](#show-running-config--section-router-bgp)
- [ping](#ping)
- [ping ipv6](#ping-ipv6)
- [traceroute](#traceroute)
- [traceroute ipv6](#traceroute-ipv6)
- [debug ip bgp](#debug-ip-bgp)
- [debug ip bgp updates](#debug-ip-bgp-updates)
- [debug ip bgp events](#debug-ip-bgp-events)
- [debug ip bgp keepalives](#debug-ip-bgp-keepalives)
- [debug ip bgp filters](#debug-ip-bgp-filters)
- [debug ip bgp dampening](#debug-ip-bgp-dampening)
- [clear ip bgp *](#clear-ip-bgp)
- [clear ip bgp soft in](#clear-ip-bgp-soft-in)
- [clear ip bgp soft out](#clear-ip-bgp-soft-out)
- [clear ip bgp ipv4 unicast](#clear-ip-bgp-ipv4-unicast)
- [clear bgp ipv6 unicast](#clear-bgp-ipv6-unicast)
  

---

# show ip bgp

## Syntax

    show ip bgp

## Example

    R1# show ip bgp

## Description

**Displays the IPv4 BGP table, including all known prefixes,
path attributes, next-hop information, best-path selection,
and route status codes.**

------------------------------------------------------------

# show bgp ipv4 unicast

## Syntax

    show bgp ipv4 unicast

## Example

    R1# show bgp ipv4 unicast

## Description

**Displays the IPv4 Unicast BGP table using the modern
Address Family syntax. This command is preferred on recent
Cisco IOS releases.**

------------------------------------------------------------

# show bgp ipv6 unicast

## Syntax

    show bgp ipv6 unicast

## Example

    R1# show bgp ipv6 unicast

## Description

**Displays the IPv6 Unicast BGP table, including all learned
IPv6 prefixes and their path attributes.**

------------------------------------------------------------

# show ip bgp summary

## Syntax

    show ip bgp summary

## Example

    R1# show ip bgp summary

## Description

**Displays the status of all BGP neighbors, including remote
AS numbers, message counters, uptime, and current session
state. This is one of the most frequently used BGP
verification commands.**

------------------------------------------------------------

# show bgp ipv4 unicast summary

## Syntax

    show bgp ipv4 unicast summary

## Example

    R1# show bgp ipv4 unicast summary

## Description

**Displays a summary of IPv4 Unicast BGP neighbors using the
Address Family configuration model.**

------------------------------------------------------------

# show bgp ipv6 unicast summary

## Syntax

    show bgp ipv6 unicast summary

## Example

    R1# show bgp ipv6 unicast summary

## Description

**Displays a summary of IPv6 Unicast BGP neighbors and their
current operational state.**

------------------------------------------------------------

# show ip bgp neighbors

## Syntax

    show ip bgp neighbors

## Example

    R1# show ip bgp neighbors

## Description

**Displays detailed information for all configured BGP
neighbors, including timers, negotiated capabilities,
message statistics, transport information, and session
parameters.**

------------------------------------------------------------

# show bgp ipv4 unicast neighbors

## Syntax

    show bgp ipv4 unicast neighbors

## Example

    R1# show bgp ipv4 unicast neighbors

## Description

**Displays detailed IPv4 Unicast neighbor information using
the Address Family syntax.**

------------------------------------------------------------

# show bgp ipv6 unicast neighbors

## Syntax

    show bgp ipv6 unicast neighbors

## Example

    R1# show bgp ipv6 unicast neighbors

## Description

**Displays detailed IPv6 Unicast BGP neighbor information.**

------------------------------------------------------------

# show ip bgp neighbors received-routes

## Syntax

```text
show ip bgp neighbors IP_ADDRESS received-routes
```

## Example

```text
R1# show ip bgp neighbors 192.168.12.2 received-routes
```

## Description

**Displays all routes received from the specified BGP
neighbor before outbound policy processing. This command is
primarily used to verify inbound routing information and
troubleshoot routing policies.**

------------------------------------------------------------

# show ip bgp neighbors advertised-routes

## Syntax

```text
show ip bgp neighbors IP_ADDRESS advertised-routes
```

## Example

```text
R1# show ip bgp neighbors 192.168.12.2 advertised-routes
```

## Description

**Displays all routes currently being advertised to the
specified BGP neighbor. Useful for verifying outbound route
filtering and routing policies.**

------------------------------------------------------------

# show ip bgp neighbors routes

## Syntax

```text
show ip bgp neighbors IP_ADDRESS routes
```

## Example

```text
R1# show ip bgp neighbors 192.168.12.2 routes
```

## Description

**Displays the routes installed in the local BGP table that
were learned from the specified neighbor after inbound
policy processing.**

------------------------------------------------------------

# show ip bgp regexp

## Syntax

```text
show ip bgp regexp REGULAR_EXPRESSION
```

## Example

```text
R1# show ip bgp regexp ^65001$
```

## Description

**Displays BGP routes whose AS_PATH attribute matches the
specified regular expression. Frequently used for
troubleshooting routing policies and AS path filtering.**

------------------------------------------------------------

# show ip bgp community

## Syntax

```text
show ip bgp community COMMUNITY

```

## Example

```text
R1# show ip bgp community 65001:100
```

## Description

**Displays all BGP routes containing the specified Community
attribute. Useful when troubleshooting community-based
routing policies.**

------------------------------------------------------------

# show ip bgp flap-statistics

## Syntax

```text
show ip bgp flap-statistics
```

## Example

```text
R1# show ip bgp flap-statistics
```

## Description

**Displays statistics for unstable BGP routes that have
experienced frequent changes. Useful when identifying route
flapping.**

------------------------------------------------------------

# show ip bgp dampening parameters

## Syntax

```text
show ip bgp dampening parameters
```

## Example

```text
R1# show ip bgp dampening parameters
```

## Description

**Displays the currently configured route dampening
parameters, including suppress, reuse, and decay values.**

------------------------------------------------------------

# show ip bgp path-attributes

## Syntax

```text
show ip bgp path-attributes
```

## Example

```text
R1# show ip bgp path-attributes
```

## Description

**Displays the BGP path attributes currently used during the
best-path selection process. Useful when troubleshooting
routing decisions.**

------------------------------------------------------------

# show ip bgp cidr-only

## Syntax

```text
show ip bgp cidr-only
```

## Example

```text
R1# show ip bgp cidr-only
```

## Description

**Displays only classless (CIDR) routes contained within the
local BGP table.**

------------------------------------------------------------

# show ip bgp inconsistent-as

## Syntax

```text
show ip bgp inconsistent-as
```

## Example

```text
R1# show ip bgp inconsistent-as
```

## Description

**Displays routes with inconsistent Autonomous System
information that may indicate configuration problems or
routing policy errors.**

------------------------------------------------------------

# show ip bgp peer-group

## Syntax

```text
show ip bgp peer-group
```

## Example

```text
R1# show ip bgp peer-group
```

## Description

**Displays all configured BGP Peer Groups and the neighbors
associated with each group.**

------------------------------------------------------------

# show ip bgp vpnv4 all

## Syntax

```text
show ip bgp vpnv4 all
```

## Example

```text
R1# show ip bgp vpnv4 all
```

## Description

**Displays all VPNv4 routes maintained by Multiprotocol BGP.
This command is commonly used in MPLS Layer 3 VPN
environments.**

------------------------------------------------------------

# show ip route bgp

## Syntax

```text
show ip route bgp
```

## Example

```text
R1# show ip route bgp
```

## Description

**Displays all BGP routes currently installed in the IPv4
routing table.**

------------------------------------------------------------

# show ipv6 route bgp

## Syntax

```text
show ipv6 route bgp
```

## Example

```text
R1# show ipv6 route bgp
```

## Description

**Displays all IPv6 routes learned through Multiprotocol
BGP.**

------------------------------------------------------------

# show ip protocols

## Syntax

```text
show ip protocols
```

## Example

```text
R1# show ip protocols
```

## Description

**Displays routing protocol configuration, including BGP
administrative information and redistribution settings.**

------------------------------------------------------------

# show running-config | section router bgp

## Syntax

```text
show running-config | section router bgp
```

## Example

```text
R1# show running-config | section router bgp
```

## Description

**Displays only the BGP-related configuration from the
running configuration, simplifying verification and
troubleshooting.**

------------------------------------------------------------

# ping

## Syntax

```text
ping IP_ADDRESS
```

## Example

```text
R1# ping 192.168.12.2
```

## Description

**Tests IPv4 connectivity to a BGP neighbor or next-hop
address.**

------------------------------------------------------------

# ping ipv6

## Syntax

```text
ping ipv6 IPV6_ADDRESS
```

## Example

```text
R1# ping ipv6 2001:DB8:12::2
```

## Description

**Tests IPv6 connectivity for MP-BGP deployments.**

------------------------------------------------------------

# traceroute

## Syntax

```text
traceroute IP_ADDRESS
```

## Example

```text
R1# traceroute 192.168.12.2
```

## Description

**Displays the Layer 3 path taken to reach a BGP neighbor or
destination network. Useful when troubleshooting routing
reachability problems.**

------------------------------------------------------------

# traceroute ipv6

## Syntax

```text
traceroute ipv6 IPV6_ADDRESS
```

## Example

```text
R1# traceroute ipv6 2001:DB8:12::2
```

## Description

**Displays the IPv6 forwarding path to the destination.
Commonly used when troubleshooting MP-BGP deployments.**

------------------------------------------------------------

# debug ip bgp

## Syntax

```text
debug ip bgp
```

## Example

```text
R1# debug ip bgp
```

## Description

**Enables general debugging for the BGP process. This command
should be used carefully because it may generate a large
amount of output on busy routers.**

------------------------------------------------------------

# debug ip bgp updates

## Syntax

```text
debug ip bgp updates
```

## Example

```text
R1# debug ip bgp updates
```

## Description

**Displays BGP Update messages exchanged between neighbors.
Useful for troubleshooting route advertisement problems.**

------------------------------------------------------------

# debug ip bgp events

## Syntax

```text
debug ip bgp events
```

## Example

```text
R1# debug ip bgp events
```

## Description

**Displays BGP session state transitions, neighbor events,
and protocol operations.**

------------------------------------------------------------

# debug ip bgp keepalives

## Syntax

```text
debug ip bgp keepalives
```

## Example

```text
R1# debug ip bgp keepalives
```

## Description

**Displays BGP Keepalive messages exchanged between peers,
allowing verification of session maintenance.**

------------------------------------------------------------

# debug ip bgp filters

## Syntax

```text
debug ip bgp filters
```

## Example

```text
R1# debug ip bgp filters
```

## Description

**Displays the operation of route filtering mechanisms,
including Prefix Lists, AS Path Filters, and Route Maps.**

------------------------------------------------------------

# debug ip bgp dampening

## Syntax

```text
debug ip bgp dampening
```

## Example

```text
R1# debug ip bgp dampening
```

## Description

**Displays route dampening events including suppression and
reuse of unstable prefixes.**

------------------------------------------------------------

# clear ip bgp *

## Syntax

```text
clear ip bgp *
```

## Example

```text
R1# clear ip bgp *
```

## Description

**Resets all IPv4 BGP neighbor sessions. This command should
be used with caution because it interrupts routing
adjacencies.**

------------------------------------------------------------

# clear ip bgp soft in

## Syntax

```text
clear ip bgp IP_ADDRESS soft in
```

## Example

```text
R1# clear ip bgp 192.168.12.2 soft in
```

## Description

**Performs an inbound soft reset without resetting the BGP
TCP session. This command reapplies inbound routing policies.**

------------------------------------------------------------

# clear ip bgp soft out

## Syntax

```text
clear ip bgp IP_ADDRESS soft out
```

## Example

```text
R1# clear ip bgp 192.168.12.2 soft out
```

## Description

**Performs an outbound soft reset and retransmits routing
updates without tearing down the BGP session.**

------------------------------------------------------------

# clear ip bgp ipv4 unicast

## Syntax

```text
clear ip bgp ipv4 unicast *
```

## Example

```text
R1# clear ip bgp ipv4 unicast *
```

## Description

**Resets all IPv4 Unicast Address Family neighbor sessions
using the modern Address Family syntax.**

------------------------------------------------------------

# clear bgp ipv6 unicast

## Syntax

```text
clear bgp ipv6 unicast *
```

## Example

```text
R1# clear bgp ipv6 unicast *
```

## Description

**Resets all IPv6 Unicast BGP neighbor sessions.**

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[01_BGP_Configuration_Commands.md](01_BGP_Configuration_Commands.md)**

➡️ Next: **[03_BGP_Labs.md](03_BGP_Labs.md)**
