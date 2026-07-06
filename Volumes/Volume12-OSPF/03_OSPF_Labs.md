# OSPF Labs

---

**Volume:** 12 • OSPF

**Estimated Reading Time:** 90 Minutes

---

## Contents

- [Lab 01 - Configure Single-Area OSPF](#lab-01---configure-single-area-ospf)
- [Lab 02 - Configure Multi-Area OSPF](#lab-02---configure-multi-area-ospf)
- [Lab 03 - Configure Passive Interfaces](#lab-03---configure-passive-interfaces)
- [Lab 04 - Configure Manual Interface Cost](#lab-04---configure-manual-interface-cost)
- [Lab 05 - Configure Route Summarization](#lab-05---configure-route-summarization)
- [Lab 06 - Configure Stub Area](#lab-06---configure-stub-area)
- [Lab 07 - Configure NSSA](#lab-07---configure-nssa)
- [Lab 08 - Configure OSPF Authentication](#lab-08---configure-ospf-authentication)
- [Lab 09 - Configure OSPFv3](#lab-09---configure-ospfv3)

---

# Lab 01 - Configure Single-Area OSPF

## Objective

Deploy OSPF within Area 0.

## Tasks

1. Configure OSPF Process 10.
2. Configure Router IDs.
3. Advertise connected networks.
4. Verify neighbor formation.

## Configuration

```text
router ospf 10

 router-id 1.1.1.1

 network 10.0.0.0 0.255.255.255 area 0
```

## Verification

```text
show ip ospf neighbor

show ip route ospf

show ip ospf
```

## Expected Result

All routers become Full neighbors and exchange LSAs.

------------------------------------------------------------

# Lab 02 - Configure Multi-Area OSPF

## Objective

Deploy a hierarchical OSPF design using Area 0 and Area 10.

## Tasks

1. Configure an Area Border Router.
2. Place branch routers into Area 10.
3. Verify inter-area routes.

## Verification

```text
show ip route ospf

show ip ospf database
```

## Expected Result

Inter-area routes appear with the `O IA` route code.

------------------------------------------------------------

# Lab 03 - Configure Passive Interfaces

## Objective

Prevent Hello packets from being transmitted toward end-user
LANs.

## Configuration

```text
router ospf 10

 passive-interface GigabitEthernet0/1
```

## Verification

```text
show ip protocols
```

## Expected Result

The LAN remains advertised while neighbor discovery is
disabled.

------------------------------------------------------------

# Lab 04 - Configure Manual Interface Cost

## Objective

Influence SPF path selection.

## Configuration

```text
interface GigabitEthernet0/0

 ip ospf cost 25
```

## Verification

```text
show ip ospf interface
```

## Expected Result

The interface uses the manually configured OSPF cost.

------------------------------------------------------------

# Lab 05 - Configure Route Summarization

## Objective

Reduce routing table size on an ABR.

## Configuration

```text
router ospf 10

 area 10 range 10.10.0.0 255.255.0.0
```

## Verification

```text
show ip route

show ip ospf database
```

## Expected Result

A summarized route is advertised into Area 0.

------------------------------------------------------------

# Lab 06 - Configure Stub Area

## Objective

Deploy a Stub Area.

## Configuration

```text
router ospf 10

 area 10 stub
```

## Verification

```text
show ip ospf

show ip route ospf
```

## Expected Result

External LSAs are filtered and a default route is injected by
the ABR.

------------------------------------------------------------

# Lab 07 - Configure NSSA

## Objective

Deploy a Not-So-Stubby Area.

## Configuration

```text
router ospf 10

 area 20 nssa
```

## Verification

```text
show ip ospf database

show ip route ospf
```

## Expected Result

External routes are redistributed as Type 7 LSAs and
translated by the ABR.

------------------------------------------------------------

# Lab 08 - Configure OSPF Authentication

## Objective

Protect OSPF neighbor relationships.

## Configuration

```text
interface GigabitEthernet0/0

 ip ospf authentication

 ip ospf authentication-key Cisco123
```

## Verification

```text
show ip ospf neighbor
```

## Expected Result

Only routers using matching authentication parameters form
adjacencies.

------------------------------------------------------------

# Lab 09 - Configure OSPFv3

## Objective

Deploy OSPF for IPv6.

## Configuration

```text
ipv6 unicast-routing

interface GigabitEthernet0/0

 ipv6 ospf 10 area 0
```

## Verification

```text
show ipv6 ospf neighbor

show ipv6 route ospf
```

## Expected Result

IPv6 routes are exchanged successfully using OSPFv3.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[02_OSPF_Verification_Commands.md](02_OSPF_Verification_Commands.md)**

➡️ Next: **[04_CheatSheet.md](04_CheatSheet.md)**
