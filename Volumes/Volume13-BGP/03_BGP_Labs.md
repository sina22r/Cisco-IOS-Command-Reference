# BGP Labs

---

**Volume:** 13 • Border Gateway Protocol (BGP)

---

## Lab 1 — Basic eBGP Neighbor

### Objective

Configure a basic External BGP (eBGP) session between two Autonomous Systems.

---

### Topology

```

AS65001 R1 ---------------- R2 AS65002
192.168.12.1      192.168.12.2

```

---

### Initial Configuration

Router interfaces are already configured.

---

### Tasks

- Configure BGP on both routers.
- Establish an eBGP session.
- Advertise Loopback0.
- Verify neighbor establishment.

---

### Solution

R1

```cisco
router bgp 65001
 bgp router-id 1.1.1.1

 neighbor 192.168.12.2 remote-as 65002

 network 1.1.1.1 mask 255.255.255.255
```

R2

```cisco
router bgp 65002
 bgp router-id 2.2.2.2

 neighbor 192.168.12.1 remote-as 65001

 network 2.2.2.2 mask 255.255.255.255
```

---

### Verification

```cisco
show ip bgp summary

show ip bgp

show ip route bgp
```

---

### Expected Result

- Neighbor state Established
- Prefix exchanged
- Route installed in Routing Table

---

### Related Commands

```
router bgp
neighbor remote-as
network
show ip bgp summary
```

---

# Lab 2 — eBGP Multi-Hop

### Objective

Configure eBGP across multiple routed hops.

---

### Topology

```

AS65001 R1 ---- R3 ---- R2 AS65002

```

---

### Tasks

- Configure eBGP.
- Use Loopback interfaces.
- Configure Multi-Hop.
- Verify adjacency.

---

### Solution

```cisco
neighbor 2.2.2.2 remote-as 65002

neighbor 2.2.2.2 update-source Loopback0

neighbor 2.2.2.2 ebgp-multihop 5
```

---

### Verification

```cisco
show ip bgp summary

show ip bgp neighbors
```

---

### Expected Result

eBGP session reaches Established despite not being directly connected.

---

### Related Commands

```
neighbor ebgp-multihop

neighbor update-source
```

---

# Lab 3 — Basic iBGP

### Objective

Configure Internal BGP between routers in the same Autonomous System.

---

### Topology

```

AS65001

R1 ---------- R2

```

---

### Tasks

- Configure iBGP.
- Use Loopback interfaces.
- Verify route exchange.

---

### Solution

```cisco
router bgp 65001

neighbor 2.2.2.2 remote-as 65001

neighbor 2.2.2.2 update-source Loopback0
```

---

### Verification

```cisco
show ip bgp summary

show ip bgp neighbors
```

---

### Expected Result

Neighbor reaches Established.

---

### Related Commands

```
neighbor remote-as

neighbor update-source
```

---

# Lab 4 — Full Mesh iBGP

### Objective

Build a complete iBGP Full Mesh.

---

### Topology

```

      R2

    /     \

R1 ------- R3

```

---

### Tasks

- Configure Full Mesh.
- Verify all adjacencies.
- Confirm route propagation.

---

### Verification

```cisco
show ip bgp summary

show ip bgp
```

---

### Expected Result

All routers have Established sessions with every other router.

---

### Related Commands

```
neighbor remote-as

neighbor update-source
```

---

# Lab 5 — Route Reflector

### Objective

Replace Full Mesh using a Route Reflector.

---

### Topology

```

      RR

     /   \

   C1     C2

```

---

### Tasks

- Configure Route Reflector.
- Configure Clients.
- Verify reflected routes.

---

### Solution

```cisco
router bgp 65001

neighbor 2.2.2.2 route-reflector-client

neighbor 3.3.3.3 route-reflector-client
```

---

### Verification

```cisco
show ip bgp

show ip bgp summary
```

---

### Expected Result

Clients exchange routes without a Full Mesh.

---

### Related Commands

```
neighbor route-reflector-client

show ip bgp
```

# Lab 6 — BGP Confederation

## Objective

Configure a BGP Confederation to reduce the number of iBGP
peerings while presenting a single Autonomous System to
external neighbors.

---

## Topology

```

           AS65000 (Confederation)

      +---------------------------+

 Sub-AS65001                Sub-AS65002

     R1 ----------------------- R2

```

---

## Tasks

- Configure the Confederation Identifier.
- Configure Confederation Peers.
- Verify external visibility.

---

## Solution

```cisco
router bgp 65001
 bgp confederation identifier 65000
 bgp confederation peers 65002
```

---

## Verification

```cisco
show ip bgp summary
show ip bgp
```

---

## Expected Result

- Confederation neighbors establish successfully.
- External routers see only AS65000.

---

## Related Commands

- bgp confederation identifier
- bgp confederation peers

------------------------------------------------------------

# Lab 7 — Next-Hop Self

## Objective

Configure Next-Hop Self in an iBGP environment.

---

## Topology

```

eBGP ----- R1 ===== R2

           iBGP

```

---

## Tasks

- Learn routes through eBGP.
- Advertise them through iBGP.
- Fix unreachable next-hop.

---

## Solution

```cisco
router bgp 65001

 neighbor 2.2.2.2 next-hop-self
```

---

## Verification

```cisco
show ip bgp

show ip route
```

---

## Expected Result

Next Hop changes to the advertising iBGP router.

---

## Related Commands

- neighbor next-hop-self

------------------------------------------------------------

# Lab 8 — Route Aggregation

## Objective

Advertise summarized prefixes instead of individual routes.

---

## Topology

```

10.1.1.0/24

10.1.2.0/24

10.1.3.0/24

↓

10.1.0.0/16

```

---

## Tasks

- Advertise individual networks.
- Configure aggregation.
- Verify summary route.

---

## Solution

```cisco
aggregate-address 10.1.0.0 255.255.0.0
```

---

## Verification

```cisco
show ip bgp
```

---

## Expected Result

Only the summarized route is advertised.

---

## Related Commands

- aggregate-address

------------------------------------------------------------

# Lab 9 — Local Preference

## Objective

Influence outbound path selection using Local Preference.

---

## Topology

```

ISP1

  \

   R1

  /

ISP2

```

---

## Tasks

- Configure Route Map.
- Set Local Preference.
- Verify best path.

---

## Solution

```cisco
route-map ISP1-IN permit 10

 set local-preference 200

router bgp 65001

 neighbor 192.168.12.2 route-map ISP1-IN in
```

---

## Verification

```cisco
show ip bgp
```

---

## Expected Result

Traffic exits through ISP1.

---

## Related Commands

- route-map
- set local-preference

------------------------------------------------------------

# Lab 10 — MED

## Objective

Influence inbound routing using the MED attribute.

---

## Tasks

- Configure MED.
- Compare advertised paths.
- Verify selected path.

---

## Solution

```cisco
route-map MED permit 10

 set metric 50

router bgp 65001

 neighbor 192.168.12.2 route-map MED out
```

---

## Verification

```cisco
show ip bgp
```

---

## Expected Result

Neighbor prefers the lower MED path.

---

## Related Commands

- set metric
- neighbor route-map

# Lab 11 — Weight

## Objective

Control outbound traffic using Cisco's proprietary Weight
attribute.

------------------------------------------------------------

## Tasks

- Configure Weight.
- Compare path selection.
- Verify best path.

------------------------------------------------------------

## Solution

```cisco
route-map ISP1 permit 10

 set weight 500

router bgp 65001

 neighbor 192.168.12.2 route-map ISP1 in
```

------------------------------------------------------------

## Verification

```cisco
show ip bgp
```

------------------------------------------------------------

## Related Commands

- set weight

------------------------------------------------------------

# Lab 12 — AS Path Prepending

## Objective

Influence inbound traffic by extending the AS_PATH.

------------------------------------------------------------

## Solution

```cisco
route-map PREPEND permit 10

 set as-path prepend 65001 65001 65001

router bgp 65001

 neighbor 192.168.12.2 route-map PREPEND out
```

------------------------------------------------------------

## Verification

```cisco
show ip bgp
```

------------------------------------------------------------

## Related Commands

- set as-path prepend

------------------------------------------------------------

# Lab 13 — Communities

## Objective

Apply Community values for routing policy.

------------------------------------------------------------

## Solution

```cisco
route-map COMMUNITY permit 10

 set community 65001:100

router bgp 65001

 neighbor 192.168.12.2 send-community

 neighbor 192.168.12.2 route-map COMMUNITY out
```

------------------------------------------------------------

## Verification

```cisco
show ip bgp community
```

------------------------------------------------------------

## Related Commands

- send-community
- set community

------------------------------------------------------------

# Lab 14 — Prefix List Filtering

## Objective

Filter advertised prefixes using Prefix Lists.

------------------------------------------------------------

## Solution

```cisco
ip prefix-list CUSTOMER permit 10.10.10.0/24

router bgp 65001

 neighbor 192.168.12.2 prefix-list CUSTOMER out
```

------------------------------------------------------------

## Verification

```cisco
show ip bgp neighbors advertised-routes
```

------------------------------------------------------------

## Related Commands

- ip prefix-list
- neighbor prefix-list

------------------------------------------------------------

# Lab 15 — Route Map Filtering

## Objective

Filter BGP advertisements using Route Maps.

------------------------------------------------------------

## Solution

```cisco
route-map FILTER permit 10

 match ip address prefix-list CUSTOMER

router bgp 65001

 neighbor 192.168.12.2 route-map FILTER out
```

------------------------------------------------------------

## Verification

```cisco
show ip bgp neighbors advertised-routes
```

------------------------------------------------------------

## Related Commands

- route-map
- match ip address

# Lab 16 — Peer Groups

## Objective

Simplify BGP neighbor configuration using Peer Groups.

---

## Topology

```
             ISP

        +------+------+
        |      |      |
       R2     R3     R4
          \    |    /
             R1
```

---

## Tasks

- Create a Peer Group.
- Assign multiple neighbors.
- Verify inherited configuration.

---

## Solution

```cisco
router bgp 65001

 neighbor ISP-PEERS peer-group

 neighbor ISP-PEERS remote-as 65002

 neighbor ISP-PEERS send-community

 neighbor ISP-PEERS next-hop-self

 neighbor 10.0.12.2 peer-group ISP-PEERS

 neighbor 10.0.13.3 peer-group ISP-PEERS

 neighbor 10.0.14.4 peer-group ISP-PEERS
```

---

## Verification

```cisco
show ip bgp peer-group

show ip bgp summary
```

---

## Expected Result

All neighbors inherit the Peer Group configuration.

---

## Related Commands

- neighbor peer-group
- show ip bgp peer-group

------------------------------------------------------------

# Lab 17 — Multipath Load Balancing

## Objective

Configure BGP Equal-Cost Multipath (ECMP).

---

## Topology

```
          ISP1

            |

            |

           R1

          /  \

         /    \

      ISP2    ISP3
```

---

## Tasks

- Learn equal routes.
- Enable Multipath.
- Verify multiple next hops.

---

## Solution

```cisco
router bgp 65001

 maximum-paths 2

 bgp bestpath as-path multipath-relax
```

---

## Verification

```cisco
show ip bgp

show ip route
```

---

## Expected Result

Two equal BGP paths are installed in the routing table.

---

## Related Commands

- maximum-paths
- bgp bestpath as-path multipath-relax

------------------------------------------------------------

# Lab 18 — MP-BGP IPv6

## Objective

Configure Multiprotocol BGP to exchange IPv6 routes between
two Autonomous Systems.

---

## Topology

```
      AS65001                       AS65002

2001:DB8:12::1 ------------- 2001:DB8:12::2

        R1                           R2
```

---

## Initial Configuration

IPv6 connectivity is already established.

---

## Tasks

- Enable IPv6 routing.
- Configure MP-BGP.
- Activate IPv6 neighbors.
- Advertise IPv6 networks.
- Verify IPv6 BGP routes.

---

## Solution

R1

```cisco
ipv6 unicast-routing

router bgp 65001

 address-family ipv6

  neighbor 2001:DB8:12::2 remote-as 65002

  neighbor 2001:DB8:12::2 activate

  network 2001:DB8:1::/64
```

R2

```cisco
ipv6 unicast-routing

router bgp 65002

 address-family ipv6

  neighbor 2001:DB8:12::1 remote-as 65001

  neighbor 2001:DB8:12::1 activate

  network 2001:DB8:2::/64
```

---

## Verification

```cisco
show bgp ipv6 unicast

show bgp ipv6 unicast summary

show ipv6 route bgp
```

---

## Expected Result

- IPv6 neighbor reaches Established.
- IPv6 prefixes appear in the BGP table.
- IPv6 routes are installed in the routing table.

---

## Related Commands

- address-family ipv6
- neighbor activate
- show bgp ipv6 unicast

------------------------------------------------------------

# Lab 19 — Soft Reset

## Objective

Apply new routing policies without resetting the BGP TCP
session.

---

## Topology

```
R1 ---------------- R2
```

---

## Tasks

- Configure a Prefix List.
- Apply a Route Map.
- Perform a Soft Reset.
- Verify new routing policy.

---

## Solution

```cisco
ip prefix-list CUSTOMER permit 10.10.10.0/24

route-map FILTER permit 10

 match ip address prefix-list CUSTOMER

router bgp 65001

 neighbor 192.168.12.2 route-map FILTER in
```

Apply the policy without resetting the session:

```cisco
clear ip bgp 192.168.12.2 soft in
```

---

## Verification

```cisco
show ip bgp

show ip bgp neighbors received-routes

show ip bgp neighbors routes
```

---

## Expected Result

- BGP session remains Established.
- Updated routing policy takes effect immediately.

---

## Related Commands

- clear ip bgp soft in
- clear ip bgp soft out
- route-map
- prefix-list

------------------------------------------------------------

# Lab 20 — Enterprise ISP Edge

## Objective

Build a complete Enterprise Internet Edge using BGP best
practices.

---

## Topology

```
                    ISP-A

                      |

                      |

                +-----------+

                |    R1     |

                +-----------+

                 /         \

                /           \

          Internal LAN     ISP-B
```

---

## Requirements

- Configure dual-homed eBGP.
- Configure Local Preference.
- Configure MED.
- Configure Communities.
- Configure Prefix Lists.
- Configure Route Maps.
- Configure Route Aggregation.
- Configure Authentication.
- Enable Multipath.
- Verify all routing policies.

---

## Suggested Configuration

```cisco
router bgp 65001

 bgp log-neighbor-changes

 maximum-paths 2

 neighbor 203.0.113.1 remote-as 65010

 neighbor 198.51.100.1 remote-as 65020

 neighbor 203.0.113.1 password Cisco123

 neighbor 198.51.100.1 password Cisco123

 neighbor 203.0.113.1 send-community

 neighbor 198.51.100.1 send-community
```

(Continue by applying Route Maps, Prefix Lists,
Communities, and Aggregation.)

---

## Verification

```cisco
show ip bgp summary

show ip bgp

show ip route bgp

show ip bgp neighbors

show ip bgp community

show ip bgp neighbors advertised-routes
```

---

## Expected Result

- Both ISPs reach Established.
- Load balancing operates correctly.
- Routing policies function as expected.
- Aggregated routes are advertised.
- Communities are propagated.
- Enterprise Internet Edge operates according to design.

---

## Related Commands

- router bgp
- neighbor remote-as
- neighbor send-community
- aggregate-address
- route-map
- prefix-list
- maximum-paths
- show ip bgp summary
- show ip bgp
- show ip route bgp

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous:
**[02_BGP_Verification_Commands.md](02_BGP_Verification_Commands.md)**

➡️ Next:
**[04_BGP_Cheat_Sheet.md](04_BGP_Cheat_Sheet.md)**
