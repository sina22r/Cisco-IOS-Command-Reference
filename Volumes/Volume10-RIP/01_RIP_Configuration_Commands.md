# RIP Configuration Commands

---

**Volume:** 10 • RIP

**Estimated Reading Time:** 70 Minutes

---

## Contents

- [router rip](#router-rip)
- [version](#version)
- [network](#network)
- [no auto-summary](#no-auto-summary)
- [auto-summary](#auto-summary)
- [passive-interface](#passive-interface)
- [default-information originate](#default-information-originate)
- [timers basic](#timers-basic)
- [offset-list](#offset-list)
- [distance](#distance)
- [redistribute static](#redistribute-static)
- [ipv6 router rip](#ipv6-router-rip)
- [ipv6 rip enable](#ipv6-rip-enable)

---

# router rip

## Syntax:

    router rip

## Example:

    R1(config)# router rip

## Description:

**Starts the RIP routing process and enters RIP router
configuration mode. All RIP-specific configuration commands
are entered from this mode.**

------------------------------------------------------------

# version

## Syntax:

    version {1 | 2}

## Example:

    R1(config-router)# version 2

## Description:

**Specifies the RIP version used by the router. Version 2 is
recommended because it supports classless routing, VLSM,
CIDR, route authentication, and multicast updates.**

------------------------------------------------------------

# network

## Syntax:

    network NETWORK_ADDRESS

## Example:

    R1(config-router)# network 192.168.10.0

    R1(config-router)# network 10.0.0.0

## Description:

**Enables RIP on interfaces whose primary addresses belong to
the specified network. Matching interfaces begin sending and
receiving RIP updates automatically.**

------------------------------------------------------------

# no auto-summary

## Syntax:

    no auto-summary

## Example:

    R1(config-router)# no auto-summary

## Description:

**Disables automatic classful route summarization at major
network boundaries. This command should be used in almost all
modern RIP deployments.**

------------------------------------------------------------

# auto-summary

## Syntax:

    auto-summary

## Example:

    R1(config-router)# auto-summary

## Description:

**Enables automatic classful route summarization. This
behavior is maintained primarily for compatibility with
legacy RIP networks.**

------------------------------------------------------------

# passive-interface

## Syntax:

    passive-interface INTERFACE

## Example:

    R1(config-router)# passive-interface GigabitEthernet0/1

## Description:

**Prevents RIP update packets from being sent out of the
specified interface while continuing to advertise the
connected network. This command is commonly used on LAN
interfaces where no RIP neighbors exist, improving security
and reducing unnecessary routing traffic.**

------------------------------------------------------------

# no passive-interface

## Syntax:

    no passive-interface INTERFACE

## Example:

    R1(config-router)# no passive-interface GigabitEthernet0/0

## Description:

**Re-enables RIP update transmission on the specified
interface after it has been configured as passive.**

------------------------------------------------------------

# default-information originate

## Syntax:

    default-information originate

## Example:

    R1(config-router)# default-information originate

## Description:

**Advertises a default route (0.0.0.0/0) to RIP neighbors,
provided that a default route already exists in the routing
table. This command is commonly used on edge routers that
connect to an ISP or another upstream network.**

------------------------------------------------------------

# timers basic

## Syntax:

    timers basic UPDATE INVALID HOLDDOWN FLUSH

## Example:

    R1(config-router)# timers basic 30 180 180 240

## Description:

**Modifies the RIP update, invalid, holddown, and flush
timers. The default values are 30, 180, 180, and 240 seconds,
respectively. Changing these timers affects route convergence
and stability.**

------------------------------------------------------------

# offset-list

## Syntax:

    offset-list ACL_NUMBER {in | out} OFFSET [INTERFACE]

## Example:

    R1(config-router)# offset-list 10 in 2 GigabitEthernet0/0

## Description:

**Adjusts the hop count metric of selected RIP routes as they
enter or leave an interface. Offset lists are commonly used
to influence route selection without changing the network
topology.**

------------------------------------------------------------

# distance

## Syntax:

    distance ADMINISTRATIVE_DISTANCE

## Example:

    R1(config-router)# distance 90

## Description:

**Changes the administrative distance assigned to RIP routes.
This affects the preference of RIP routes compared to routes
learned from other routing sources.**

------------------------------------------------------------

# maximum-paths

## Syntax:

    maximum-paths NUMBER

## Example:

    R1(config-router)# maximum-paths 4

## Description:

**Specifies the maximum number of equal-cost RIP routes that
can be installed in the routing table for load balancing.**

------------------------------------------------------------

# neighbor

## Syntax:

    neighbor IP_ADDRESS

## Example:

    R1(config-router)# neighbor 192.168.10.2

## Description:

**Configures RIP to exchange routing updates with a specific
neighbor using unicast instead of the default multicast or
broadcast behavior. This command is primarily used in
specialized network environments.**

------------------------------------------------------------

# redistribute static

## Syntax:

    redistribute static

## Example:

    R1(config-router)# redistribute static

## Description:

**Redistributes static routes into the RIP routing process.
This command is commonly used when static routes should be
advertised dynamically to neighboring RIP routers.**

------------------------------------------------------------

# default-metric

## Syntax:

    default-metric HOP_COUNT

## Example:

    R1(config-router)# default-metric 2

## Description:

**Specifies the default hop count assigned to redistributed
routes when they are injected into the RIP routing domain.**

------------------------------------------------------------

# ipv6 router rip

## Syntax:

    ipv6 router rip PROCESS_NAME

## Example:

    R1(config)# ipv6 router rip ENTERPRISE

## Description:

**Creates an RIPng routing process for IPv6. Unlike IPv4 RIP,
RIPng identifies the routing process by name instead of using
a numeric process ID.**

------------------------------------------------------------

# ipv6 rip enable

## Syntax:

    ipv6 rip PROCESS_NAME enable

## Example:

    R1(config)# interface GigabitEthernet0/0

    R1(config-if)# ipv6 rip ENTERPRISE enable

## Description:

**Enables RIPng on the specified interface and associates it
with the named RIPng routing process. RIPng operates on an
interface basis rather than using network statements.**

------------------------------------------------------------

# ip rip send version

## Syntax:

    ip rip send version {1 | 2 | 1 2}

## Example:

    R1(config-if)# ip rip send version 2

## Description:

**Specifies the RIP version used when sending routing updates
out of the interface. This command allows interoperability
with mixed RIP environments.**

------------------------------------------------------------

# ip rip receive version

## Syntax:

    ip rip receive version {1 | 2 | 1 2}

## Example:

    R1(config-if)# ip rip receive version 2

## Description:

**Specifies which RIP versions are accepted on the interface.
This command is useful when migrating between RIP version 1
and RIP version 2.**

------------------------------------------------------------

# ip rip authentication mode

## Syntax:

    ip rip authentication mode {text | md5}

## Example:

    R1(config-if)# ip rip authentication mode md5

## Description:

**Configures the authentication method used for RIP version 2
updates. MD5 authentication is recommended because it
provides significantly better protection than plain text
authentication.**

------------------------------------------------------------

# ip rip authentication key-chain

## Syntax:

    ip rip authentication key-chain KEY_CHAIN

## Example:

    R1(config-if)# ip rip authentication key-chain RIP_KEYS

## Description:

**Associates a key chain with the interface for RIP version 2
authentication. All neighboring routers must use compatible
key chains for successful route exchange.**

------------------------------------------------------------

## RIP Configuration Summary

RIP configuration consists of enabling the routing process,
advertising networks, selecting the appropriate RIP version,
disabling automatic summarization where appropriate,
configuring passive interfaces, tuning timers, and enabling
authentication. For IPv6, RIPng is configured per interface
using a named routing process.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[README.md](README.md)**

➡️ Next: **[02_RIP_Verification_Commands.md](02_RIP_Verification_Commands.md)**
