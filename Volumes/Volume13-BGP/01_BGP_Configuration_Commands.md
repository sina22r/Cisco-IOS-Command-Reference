# BGP Configuration Commands

---

**Volume:** 13 • Border Gateway Protocol (BGP)

**Estimated Reading Time:** 160 Minutes

---

## Contents

- [router bgp](#router-bgp)
- [bgp router-id](#bgp-router-id)
- [neighbor remote-as](#neighbor-remote-as)
- [neighbor update-source](#neighbor-update-source)
- [neighbor next-hop-self](#neighbor-next-hop-self)
- [neighbor description](#neighbor-description)
- [network](#network)
- [aggregate-address](#aggregate-address)
- [default-information originate](#default-information-originate)
- [redistribute](#redistribute)
- [neighbor route-map](#neighbor-route-map)
- [neighbor prefix-list](#neighbor-prefix-list)
- [neighbor filter-list](#neighbor-filter-list)
- [neighbor maximum-prefix](#neighbor-maximum-prefix)
- [neighbor password](#neighbor-password)
- [neighbor shutdown](#neighbor-shutdown)
- [neighbor activate](#neighbor-activate)
- [address-family ipv4](#address-family-ipv4)
- [address-family ipv6](#address-family-ipv6)
- [exit-address-family](#exit-address-family)
- [bgp log-neighbor-changes](#bgp-log-neighbor-changes)
- [bgp always-compare-med](#bgp-always-compare-med)
- [bgp deterministic-med](#bgp-deterministic-med)
- [maximum-paths](#maximum-paths)
- [bgp bestpath as-path multipath-relax](#bgp-bestpath-as-path-multipath-relax)
- [neighbor send-community](#neighbor-send-community)
- [neighbor soft-reconfiguration inbound](#neighbor-soft-reconfiguration-inbound)
- [neighbor ebgp-multihop](#neighbor-ebgp-multihop)
- [neighbor ttl-security hops](#neighbor-ttl-security-hops)
- [neighbor remove-private-as](#neighbor-remove-private-as)
- [neighbor allowas-in](#neighbor-allowas-in)
- [neighbor local-as](#neighbor-local-as)
- [neighbor default-originate](#neighbor-default-originate)
- [neighbor route-reflector-client](#neighbor-route-reflector-client)
- [neighbor peer-group](#neighbor-peer-group)
- [neighbor inherit peer-policy](#neighbor-inherit-peer-policy)
- [neighbor inherit peer-session](#neighbor-inherit-peer-session)
- [bgp cluster-id](#bgp-cluster-id)
- [bgp confederation identifier](#bgp-confederation-identifier)
- [bgp confederation peers](#bgp-confederation-peers)
- [bgp graceful-restart](#bgp-graceful-restart)
- [bgp enforce-first-as](#bgp-enforce-first-as)
- [bgp fast-external-fallover](#bgp-fast-external-fallover)
- [bgp bestpath compare-routerid](#bgp-bestpath-compare-routerid)
- [bgp bestpath med missing-as-worst](#bgp-bestpath-med-missing-as-worst)
- [bgp bestpath as-path ignore](#bgp-bestpath-as-path-ignore)
- [neighbor capability dynamic](#neighbor-capability-dynamic)
- [bgp listen range](#bgp-listen-range)
  
---

# router bgp

## Syntax

```text
router bgp AS_NUMBER
```

## Example

```text
R1(config)# router bgp 65001
```

## Description

**Starts the BGP routing process using the specified local
Autonomous System number. Every BGP router must belong to an
Autonomous System.**

------------------------------------------------------------

# bgp router-id

## Syntax

```text
bgp router-id A.B.C.D
```

## Example

```text
R1(config-router)# bgp router-id 1.1.1.1
```

## Description

**Manually configures the BGP Router ID. A manually assigned
Router ID provides stable BGP operation and simplifies
troubleshooting.**

------------------------------------------------------------

# neighbor remote-as

## Syntax

```text
neighbor IP_ADDRESS remote-as AS_NUMBER
```

## Example

```text
R1(config-router)# neighbor 192.168.12.2 remote-as 65002
```

## Description

**Defines a BGP neighbor and specifies the Autonomous System
to which the neighbor belongs. This command establishes
either an eBGP or iBGP session depending on the AS number.**

------------------------------------------------------------

# neighbor update-source

## Syntax

```text
neighbor IP_ADDRESS update-source INTERFACE
```

## Example

```text
R1(config-router)# neighbor 2.2.2.2 update-source Loopback0
```

## Description

**Specifies the source interface used to establish BGP
sessions. This command is commonly required for iBGP sessions
that use loopback interfaces.**

------------------------------------------------------------

# neighbor next-hop-self

## Syntax

```text
neighbor IP_ADDRESS next-hop-self
```

## Example

```text
R1(config-router)# neighbor 2.2.2.2 next-hop-self
```

## Description

**Changes the NEXT_HOP attribute to the local router before
advertising routes to the specified neighbor. This command is
commonly used within iBGP environments.**

------------------------------------------------------------

# neighbor description

## Syntax

```text
neighbor IP_ADDRESS description TEXT
```

## Example

```text
R1(config-router)# neighbor 192.168.12.2 description ISP-A
```

## Description

**Assigns an administrative description to the neighbor,
making BGP configurations easier to understand and maintain.**

------------------------------------------------------------

# network

## Syntax

```text
network NETWORK mask SUBNET_MASK
```

## Example

```text
R1(config-router)# network 10.10.10.0 mask 255.255.255.0
```

## Description

**Advertises a network into BGP if an exact matching route
already exists in the routing table. Unlike IGPs, BGP does
not automatically advertise connected networks.**

------------------------------------------------------------


# neighbor shutdown

## Syntax

    neighbor IP_ADDRESS shutdown

## Example

    R1(config-router)# neighbor 192.168.12.2 shutdown

## Description

**Administratively disables a BGP neighbor session without
removing its configuration. This command is useful during
maintenance windows or troubleshooting.**

------------------------------------------------------------

# address-family ipv4

## Syntax

    address-family ipv4

## Example

    R1(config-router)# address-family ipv4

## Description

**Enters the IPv4 Address Family configuration mode. Modern
Cisco IOS versions configure most BGP neighbor parameters
inside the address-family rather than the global BGP process.**

------------------------------------------------------------

# address-family ipv6

## Syntax

    address-family ipv6

## Example

    R1(config-router)# address-family ipv6

## Description

**Enters the IPv6 Address Family configuration mode for
configuring BGP IPv6 neighbors and policies.**

------------------------------------------------------------

# neighbor activate

## Syntax

    neighbor IP_ADDRESS activate

## Example

    R1(config-router-af)# neighbor 192.168.12.2 activate

## Description

**Activates the specified neighbor within the current Address
Family. A neighbor must be activated before exchanging routes
for that address family.**

------------------------------------------------------------

# exit-address-family

## Syntax

    exit-address-family

## Example

    R1(config-router-af)# exit-address-family

## Description

**Exits the current Address Family configuration mode and
returns to the global BGP router configuration mode.**

------------------------------------------------------------

# bgp log-neighbor-changes

## Syntax

    bgp log-neighbor-changes

## Example

    R1(config-router)# bgp log-neighbor-changes

## Description

**Generates syslog messages whenever a BGP neighbor changes
state. This command is considered a best practice for
monitoring and troubleshooting BGP sessions.**

------------------------------------------------------------

# bgp always-compare-med

## Syntax

    bgp always-compare-med

## Example

    R1(config-router)# bgp always-compare-med

## Description

**Allows the MED attribute to be compared even when routes
originate from different neighboring Autonomous Systems.**

------------------------------------------------------------

# bgp deterministic-med

## Syntax

    bgp deterministic-med

## Example

    R1(config-router)# bgp deterministic-med

## Description

**Ensures consistent MED comparison by grouping routes
received from the same neighboring Autonomous System before
selecting the best path.**

------------------------------------------------------------

# maximum-paths

## Syntax

    maximum-paths NUMBER

## Example

    R1(config-router)# maximum-paths 8

## Description

**Allows installation of multiple equal-cost BGP paths into
the routing table for load balancing.**

------------------------------------------------------------

# bgp bestpath as-path multipath-relax

## Syntax

    bgp bestpath as-path multipath-relax

## Example

    R1(config-router)# bgp bestpath as-path multipath-relax

## Description

**Allows multipath load balancing across routes with
different AS_PATH attributes, provided that other best-path
selection requirements are satisfied.**

------------------------------------------------------------

# neighbor send-community

## Syntax

    neighbor IP_ADDRESS send-community

## Example

    R1(config-router-af)# neighbor 192.168.12.2 send-community

## Description

**Allows BGP Community attributes to be advertised to the
specified neighbor. Without this command, Community values
are not propagated.**

------------------------------------------------------------

# neighbor soft-reconfiguration inbound

## Syntax

    neighbor IP_ADDRESS soft-reconfiguration inbound

## Example

    R1(config-router)# neighbor 192.168.12.2 soft-reconfiguration inbound

## Description

**Stores received BGP updates before inbound policy
processing, allowing policy changes without resetting the
BGP session. Although Route Refresh is preferred in modern
networks, this command is still encountered in production
environments.**

------------------------------------------------------------

# neighbor ebgp-multihop

## Syntax

    neighbor IP_ADDRESS ebgp-multihop HOPS

## Example

    R1(config-router)# neighbor 192.168.12.2 ebgp-multihop 5

## Description

**Allows an eBGP session to be established across multiple
Layer 3 hops instead of requiring directly connected
neighbors.**

------------------------------------------------------------

# neighbor ttl-security hops

## Syntax

    neighbor IP_ADDRESS ttl-security hops NUMBER

## Example

    R1(config-router)# neighbor 192.168.12.2 ttl-security hops 1

## Description

**Protects eBGP sessions against spoofed packets by verifying
the incoming packet TTL value. This feature is commonly
referred to as GTSM (Generalized TTL Security Mechanism).**

------------------------------------------------------------

# neighbor remove-private-as

## Syntax

    neighbor IP_ADDRESS remove-private-as

## Example

    R1(config-router)# neighbor 192.168.12.2 remove-private-as

## Description

**Removes private Autonomous System numbers from the AS_PATH
attribute before advertising routes to external peers.**

------------------------------------------------------------

# neighbor allowas-in

## Syntax

    neighbor IP_ADDRESS allowas-in

## Example

    R1(config-router)# neighbor 192.168.12.2 allowas-in

## Description

**Allows routes containing the local Autonomous System number
within the AS_PATH to be accepted, helping avoid routing
issues in specific multihoming scenarios.**

------------------------------------------------------------

# neighbor local-as

## Syntax

    neighbor IP_ADDRESS local-as AS_NUMBER

## Example

    R1(config-router)# neighbor 192.168.12.2 local-as 65100

## Description

**Assigns an alternate local Autonomous System number when
communicating with a specific neighbor. Commonly used during
network migrations and mergers.**

------------------------------------------------------------

# neighbor default-originate

## Syntax

    neighbor IP_ADDRESS default-originate

## Example

    R1(config-router-af)# neighbor 192.168.12.2 default-originate

## Description

**Advertises a default route only to the specified BGP
neighbor regardless of the global BGP policy.**

------------------------------------------------------------

# neighbor route-reflector-client

## Syntax

    neighbor IP_ADDRESS route-reflector-client

## Example

    R1(config-router-af)# neighbor 2.2.2.2 route-reflector-client

## Description

**Configures the specified iBGP neighbor as a Route
Reflector Client, eliminating the need for a full iBGP mesh.**

------------------------------------------------------------

# neighbor peer-group

## Syntax

    neighbor NAME peer-group

## Example

    R1(config-router)# neighbor ISP_PEERS peer-group

## Description

**Creates a BGP Peer Group that allows multiple neighbors to
share common configuration, simplifying administration and
improving scalability.**

------------------------------------------------------------

# neighbor inherit peer-policy

## Syntax

    neighbor IP_ADDRESS inherit peer-policy NAME

## Example

    R1(config-router-af)# neighbor 192.168.12.2 inherit peer-policy ISP_POLICY

## Description

**Applies a predefined peer policy template to the specified
neighbor in modern Cisco IOS implementations.**

------------------------------------------------------------

# neighbor inherit peer-session

## Syntax

    neighbor IP_ADDRESS inherit peer-session NAME

## Example

    R1(config-router-af)# neighbor 192.168.12.2 inherit peer-session ISP_SESSION

## Description

**Applies a predefined peer session template to the specified
neighbor, simplifying large-scale BGP deployments.**

------------------------------------------------------------

# bgp cluster-id

## Syntax

    bgp cluster-id CLUSTER_ID

## Example

    R1(config-router)# bgp cluster-id 1.1.1.1

## Description

**Configures the Cluster ID for a Route Reflector. When
multiple Route Reflectors exist within the same cluster,
they must share the same Cluster ID to prevent routing
loops.**

------------------------------------------------------------

# bgp confederation identifier

## Syntax

    bgp confederation identifier AS_NUMBER

## Example

    R1(config-router)# bgp confederation identifier 65000

## Description

**Defines the public Autonomous System number representing
the entire BGP Confederation. External peers see only this
AS number rather than the internal member AS numbers.**

------------------------------------------------------------

# bgp confederation peers

## Syntax

    bgp confederation peers AS_NUMBER [AS_NUMBER ...]

## Example

    R1(config-router)# bgp confederation peers 65001 65002 65003

## Description

**Specifies the member Autonomous Systems that belong to the
same BGP Confederation. Routers within the confederation
exchange routing information using special confederation
attributes while appearing as a single AS externally.**

------------------------------------------------------------

# bgp graceful-restart

## Syntax

    bgp graceful-restart

## Example

    R1(config-router)# bgp graceful-restart

## Description

**Enables BGP Graceful Restart. Neighboring routers preserve
forwarding information during a temporary control-plane
restart, reducing traffic disruption while the BGP process
recovers.**

------------------------------------------------------------

# bgp enforce-first-as

## Syntax

    bgp enforce-first-as

## Example

    R1(config-router)# bgp enforce-first-as

## Description

**Verifies that the first Autonomous System listed in the
received AS_PATH matches the configured external neighbor's
AS number. This feature improves security by preventing
incorrect or spoofed advertisements from external peers.**

------------------------------------------------------------

# bgp fast-external-fallover

## Syntax

    bgp fast-external-fallover

## Example

    R1(config-router)# bgp fast-external-fallover

## Description

**Immediately resets an eBGP session when the directly
connected interface goes down, allowing faster convergence
than waiting for the Hold Timer to expire.**

------------------------------------------------------------

# bgp bestpath compare-routerid

## Syntax

    bgp bestpath compare-routerid

## Example

    R1(config-router)# bgp bestpath compare-routerid

## Description

**Allows the BGP Router ID to be considered during best-path
selection when other path attributes are equal. This provides
deterministic path selection in certain topologies.**

------------------------------------------------------------

# bgp bestpath med missing-as-worst

## Syntax

    bgp bestpath med missing-as-worst

## Example

    R1(config-router)# bgp bestpath med missing-as-worst

## Description

**Treats routes that do not include a MED attribute as having
the worst possible MED value, affecting best-path selection
when comparing candidate routes.**

------------------------------------------------------------

# bgp bestpath as-path ignore

## Syntax

    bgp bestpath as-path ignore

## Example

    R1(config-router)# bgp bestpath as-path ignore

## Description

**Instructs BGP to ignore the AS_PATH length during the
best-path selection process. This command is primarily used
in specialized environments and should be deployed with
careful consideration.**

------------------------------------------------------------

# neighbor capability dynamic

## Syntax

    neighbor IP_ADDRESS capability dynamic

## Example

    R1(config-router)# neighbor 192.168.12.2 capability dynamic

## Description

**Enables Dynamic Capability negotiation, allowing certain
BGP capabilities to be modified without resetting the BGP
session, provided both peers support the feature.**

------------------------------------------------------------

# bgp listen range

## Syntax

    bgp listen range PREFIX peer-group NAME

## Example

    R1(config-router)# bgp listen range 10.10.0.0/16 peer-group FABRIC

## Description

**Automatically accepts BGP neighbors whose addresses fall
within the specified prefix and assigns them to the specified
peer group. This command is commonly used in large-scale
data center and service provider deployments.**

------------------------------------------------------------

## BGP Configuration Summary

BGP configuration commonly includes neighbor establishment,
address families, route advertisement, policy control,
aggregation, route filtering, authentication, route
reflection, confederations, graceful restart, best-path
manipulation, and scalability features. Together these
commands provide the flexibility required for enterprise,
service provider, and Internet-scale routing deployments.

------------------------------------------------------------


## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **Part 4**

➡️ Next: **[02_BGP_Verification_Commands.md](02_BGP_Verification_Commands.md)**
