# EIGRP Configuration Commands

---

**Volume:** 11 • EIGRP

**Estimated Reading Time:** 90 Minutes

---

## Contents

- [router eigrp](#router-eigrp)
- [address-family ipv4 autonomous-system](#address-family-ipv4-autonomous-system)
- [address-family ipv6 autonomous-system](#address-family-ipv6-autonomous-system)
- [network](#network)
- [eigrp router-id](#eigrp-router-id)
- [no auto-summary](#no-auto-summary)
- [passive-interface](#passive-interface)
- [no passive-interface](#no-passive-interface)
- [variance](#variance)
- [maximum-paths](#maximum-paths)
- [stub](#stub)
- [redistribute](#redistribute)
- [summary-address](#summary-address)
- [authentication mode eigrp](#authentication-mode-eigrp)
- [authentication key-chain eigrp](#authentication-key-chain-eigrp)
- [af-interface](#af-interface)
- [topology base](#topology-base)

---

# router eigrp

## Syntax:

    router eigrp AUTONOMOUS_SYSTEM

## Example:

    R1(config)# router eigrp 100

## Description:

**Starts the EIGRP routing process in Classic Mode using the
specified autonomous system number. All routers that exchange
EIGRP routes must belong to the same autonomous system unless
route redistribution is configured.**

------------------------------------------------------------

# address-family ipv4 autonomous-system

## Syntax:

    router eigrp NAME

    address-family ipv4 autonomous-system AS_NUMBER

## Example:

    R1(config)# router eigrp ENTERPRISE

    R1(config-router)# address-family ipv4 autonomous-system 100

## Description:

**Enters the IPv4 Address Family configuration mode used by
Named EIGRP. Named Mode provides a modular configuration
structure and is the preferred deployment model in modern
Cisco IOS XE releases.**

------------------------------------------------------------

# address-family ipv6 autonomous-system

## Syntax:

    address-family ipv6 autonomous-system AS_NUMBER

## Example:

    R1(config-router)# address-family ipv6 autonomous-system 100

## Description:

**Enters the IPv6 Address Family configuration mode for Named
EIGRP, allowing IPv6 routing configuration within the named
EIGRP process.**

------------------------------------------------------------

# network

## Syntax:

    network NETWORK [WILDCARD_MASK]

## Example:

    R1(config-router)# network 10.10.10.0 0.0.0.255

## Description:

**Enables EIGRP on interfaces whose addresses match the
specified network statement. Matching interfaces begin
forming EIGRP neighbor relationships and advertising
connected networks.**

------------------------------------------------------------

# eigrp router-id

## Syntax:

    eigrp router-id A.B.C.D

## Example:

    R1(config-router)# eigrp router-id 1.1.1.1

## Description:

**Manually configures the EIGRP Router ID. If not configured,
Cisco IOS selects the highest loopback address or the highest
active physical interface address. Configuring a static
Router ID is considered a best practice in enterprise
deployments.**

------------------------------------------------------------

# no auto-summary

## Syntax:

    no auto-summary

## Example:

    R1(config-router)# no auto-summary

## Description:

**Disables automatic route summarization at classful network
boundaries. This command is recommended in modern networks
that use VLSM or CIDR addressing.**

------------------------------------------------------------

# passive-interface

## Syntax:

    passive-interface INTERFACE

## Example:

    R1(config-router)# passive-interface GigabitEthernet0/1

## Description:

**Stops EIGRP Hello packets from being transmitted on the
specified interface while still advertising the connected
network. This improves security and reduces unnecessary
routing traffic toward user LANs.**

------------------------------------------------------------

# no passive-interface

## Syntax:

    no passive-interface INTERFACE

## Example:

    R1(config-router)# no passive-interface GigabitEthernet0/0

## Description:

**Re-enables EIGRP neighbor discovery and routing updates on
the specified interface after passive mode has been applied.**

------------------------------------------------------------

# variance

## Syntax:

    variance MULTIPLIER

## Example:

    R1(config-router)# variance 2

## Description:

**Enables unequal-cost load balancing by allowing EIGRP to
install feasible successor routes whose metric is within the
configured variance multiplier. This feature is unique to
EIGRP among common interior gateway protocols.**

------------------------------------------------------------

# maximum-paths

## Syntax:

    maximum-paths NUMBER

## Example:

    R1(config-router)# maximum-paths 4

## Description:

**Specifies the maximum number of equal-cost paths that EIGRP
may install into the routing table for load balancing.**

------------------------------------------------------------

# stub

## Syntax:

    eigrp stub [connected] [summary] [static] [redistributed] [receive-only]

## Example:

    R1(config-router)# eigrp stub connected summary

## Description:

**Configures the router as an EIGRP Stub Router. Stub routers
limit query propagation, reduce CPU utilization, and improve
network convergence in hub-and-spoke topologies.**

------------------------------------------------------------

# redistribute

## Syntax:

    redistribute PROTOCOL

## Example:

    R1(config-router)# redistribute static

## Description:

**Imports routes learned from another routing source into the
EIGRP routing domain. Redistribution should be carefully
planned to avoid routing loops and inconsistent path
selection.**

------------------------------------------------------------

# summary-address

## Syntax:

    ip summary-address eigrp AS_NUMBER NETWORK MASK

## Example:

    R1(config)# interface GigabitEthernet0/0

    R1(config-if)# ip summary-address eigrp 100 10.10.0.0 255.255.0.0

## Description:

**Configures manual route summarization on an interface.
Summarization reduces the size of the routing table, limits
query propagation, improves convergence, and automatically
creates a discard route (Null0) to prevent routing loops.**

------------------------------------------------------------

# authentication mode eigrp

## Syntax:

    ip authentication mode eigrp AS_NUMBER md5

## Example:

    R1(config-if)# ip authentication mode eigrp 100 md5

## Description:

**Enables MD5 authentication for EIGRP packets transmitted
through the interface. Authentication prevents unauthorized
routers from forming EIGRP neighbor adjacencies.**

------------------------------------------------------------

# authentication key-chain eigrp

## Syntax:

    ip authentication key-chain eigrp AS_NUMBER KEY_CHAIN

## Example:

    R1(config-if)# ip authentication key-chain eigrp 100 EIGRP_KEYS

## Description:

**Associates an EIGRP key chain with the interface for MD5
authentication. Neighboring routers must use compatible key
chains to establish adjacency successfully.**

------------------------------------------------------------

# af-interface

## Syntax:

    af-interface INTERFACE

## Example:

    R1(config-router-af)# af-interface GigabitEthernet0/0

## Description:

**Enters interface configuration mode within Named EIGRP.
Interface-specific settings such as authentication, timers,
passive-interface behavior, and bandwidth utilization are
configured from this mode.**

------------------------------------------------------------

# topology base

## Syntax:

    topology base

## Example:

    R1(config-router-af)# topology base

## Description:

**Enters the base topology configuration mode in Named EIGRP.
Advanced features such as route redistribution, route
filtering, and administrative distance are configured within
this section.**

------------------------------------------------------------

# eigrp log-neighbor-changes

## Syntax:

    eigrp log-neighbor-changes

## Example:

    R1(config-router)# eigrp log-neighbor-changes

## Description:

**Enables logging of EIGRP neighbor adjacency events.
Whenever a neighbor relationship is established or lost,
Cisco IOS generates a log message. This feature is valuable
for monitoring and troubleshooting EIGRP stability.**

------------------------------------------------------------

# metric weights

## Syntax:

    metric weights TOS K1 K2 K3 K4 K5

## Example:

    R1(config-router)# metric weights 0 1 0 1 0 0

## Description:

**Configures the K-values used by the EIGRP composite metric
calculation. All EIGRP neighbors within the same autonomous
system must use identical K-values; otherwise, neighbor
adjacencies will not form. The default values are K1=1,
K3=1, and K2=K4=K5=0.**

------------------------------------------------------------

# bandwidth-percent

## Syntax:

    ip bandwidth-percent eigrp AS_NUMBER PERCENT

## Example:

    R1(config-if)# ip bandwidth-percent eigrp 100 50

## Description:

**Limits the percentage of interface bandwidth that EIGRP may
use for routing updates. This command is especially useful on
low-bandwidth WAN links where routing traffic must be
controlled.**

------------------------------------------------------------

## EIGRP Configuration Summary

EIGRP supports both Classic Mode and Named Mode for IPv4 and
IPv6 deployments. Enterprise implementations commonly use
passive interfaces, authentication, route summarization,
stub routing, unequal-cost load balancing, and route
redistribution to improve scalability, security, and
convergence performance.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[README.md](README.md)**

➡️ Next: **[02_EIGRP_Verification_Commands.md](02_EIGRP_Verification_Commands.md)**
