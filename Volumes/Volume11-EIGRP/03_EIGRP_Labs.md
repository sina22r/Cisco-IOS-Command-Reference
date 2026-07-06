# EIGRP Labs

---

**Volume:** 11 • EIGRP

**Estimated Reading Time:** 70 Minutes

---

## Contents

- [Lab 01 - Configure Basic EIGRP](#lab-01---configure-basic-eigrp)
- [Lab 02 - Configure Passive Interfaces](#lab-02---configure-passive-interfaces)
- [Lab 03 - Configure Manual Summarization](#lab-03---configure-manual-summarization)
- [Lab 04 - Configure EIGRP Stub](#lab-04---configure-eigrp-stub)
- [Lab 05 - Configure MD5 Authentication](#lab-05---configure-md5-authentication)
- [Lab 06 - Configure Named EIGRP](#lab-06---configure-named-eigrp)
- [Lab 07 - Configure EIGRP for IPv6](#lab-07---configure-eigrp-for-ipv6)

---

# Lab 01 - Configure Basic EIGRP

## Objective

Deploy basic IPv4 EIGRP routing between three enterprise
routers.

## Topology

```
             LAN A
               |
           +--------+
           |   R1   |
           +--------+
              ||
==============||==============
              ||
           +--------+
           |   R2   |
           +--------+
              ||
==============||==============
              ||
           +--------+
           |   R3   |
           +--------+
               |
             LAN B
```

## Tasks

1. Enable EIGRP AS 100.
2. Advertise all connected networks.
3. Disable automatic summarization.
4. Verify neighbor relationships.
5. Verify learned routes.

## Configuration

```text
R1(config)# router eigrp 100
R1(config-router)# network 10.0.0.0 0.255.255.255
R1(config-router)# no auto-summary
```

## Verification

```text
show ip eigrp neighbors

show ip route eigrp

show ip protocols
```

## Expected Result

All routers establish EIGRP adjacencies and dynamically learn
remote networks.

------------------------------------------------------------

# Lab 02 - Configure Passive Interfaces

## Objective

Prevent EIGRP Hellos from being transmitted toward user LANs.

## Tasks

1. Configure EIGRP.
2. Configure passive interfaces.
3. Verify neighbors remain active on WAN links.

## Configuration

```text
R1(config-router)# passive-interface GigabitEthernet0/1
```

## Verification

```text
show ip protocols
```

## Expected Result

No Hellos are transmitted toward user networks while routing
information remains available.

------------------------------------------------------------

# Lab 03 - Configure Manual Summarization

## Objective

Reduce routing table size by summarizing routes.

## Tasks

1. Configure interface summarization.
2. Verify summarized routes.

## Configuration

```text
interface GigabitEthernet0/0

ip summary-address eigrp 100 10.10.0.0 255.255.0.0
```

## Verification

```text
show ip route

show ip eigrp topology
```

## Expected Result

Neighbor routers receive only the summarized route.

------------------------------------------------------------

# Lab 04 - Configure EIGRP Stub

## Objective

Deploy Stub Routing in a hub-and-spoke topology.

## Topology

```
            Headquarters
                 |
            +---------+
            |   R1    |
            +---------+
            /         \
           /           \
      +------+     +------+
      | R2   |     | R3   |
      +------+     +------+
       Branch A     Branch B
```

## Tasks

1. Configure R2 and R3 as Stub routers.
2. Verify query boundaries.

## Configuration

```text
R2(config-router)# eigrp stub connected summary
```

## Verification

```text
show ip protocols
```

## Expected Result

Branch routers do not receive unnecessary EIGRP queries.

------------------------------------------------------------

# Lab 05 - Configure MD5 Authentication

## Objective

Secure EIGRP neighbor relationships.

## Tasks

1. Create a key chain.
2. Apply MD5 authentication.
3. Verify neighbor formation.

## Configuration

```text
key chain EIGRP_KEYS

 key 1

  key-string Cisco123

interface GigabitEthernet0/0

 ip authentication mode eigrp 100 md5

 ip authentication key-chain eigrp 100 EIGRP_KEYS
```

## Verification

```text
show ip eigrp neighbors
```

## Expected Result

Only authenticated routers successfully establish EIGRP
adjacencies.

------------------------------------------------------------

# Lab 06 - Configure Named EIGRP

## Objective

Deploy Named Mode EIGRP.

## Tasks

1. Create a named EIGRP process.
2. Configure IPv4 address family.
3. Enable interfaces.
4. Verify routing.

## Configuration

```text
router eigrp ENTERPRISE

 address-family ipv4 autonomous-system 100
```

## Verification

```text
show running-config | section router eigrp

show ip eigrp neighbors
```

## Expected Result

Named EIGRP operates correctly using address-family
configuration.

------------------------------------------------------------

# Lab 07 - Configure EIGRP for IPv6

## Objective

Deploy EIGRP for IPv6.

## Tasks

1. Enable IPv6 routing.
2. Configure EIGRP IPv6.
3. Verify neighbors.
4. Verify IPv6 routes.

## Configuration

```text
ipv6 unicast-routing

router eigrp ENTERPRISE

 address-family ipv6 autonomous-system 100
```

## Verification

```text
show ipv6 eigrp neighbors

show ipv6 route eigrp
```

## Expected Result

IPv6 routes are exchanged successfully using EIGRP.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[02_EIGRP_Verification_Commands.md](02_EIGRP_Verification_Commands.md)**

➡️ Next: **[04_CheatSheet.md](04_CheatSheet.md)**
