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

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[README.md](README.md)**

➡️ Next: **[02_BGP_Verification_Commands.md](02_BGP_Verification_Commands.md)**
