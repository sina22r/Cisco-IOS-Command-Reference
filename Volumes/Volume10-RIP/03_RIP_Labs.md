# RIP Labs

---

**Volume:** 10 • RIP

**Estimated Reading Time:** 60 Minutes

---

## Contents

- [Lab 01 - Configure Basic RIP Version 2](#lab-01---configure-basic-rip-version-2)
- [Lab 02 - Disable Automatic Summarization](#lab-02---disable-automatic-summarization)
- [Lab 03 - Configure Passive Interfaces](#lab-03---configure-passive-interfaces)
- [Lab 04 - Advertise a Default Route](#lab-04---advertise-a-default-route)
- [Lab 05 - Configure RIPng](#lab-05---configure-ripng)

---

# Lab 01 - Configure Basic RIP Version 2

## Objective

Configure RIP Version 2 between three routers and verify
dynamic route exchange.

## Topology

```
              192.168.12.0/30
        +---------------------------+
        |                           |
    +--------+                 +--------+
    |   R1   |-----------------|   R2   |
    +--------+                 +--------+
         |                          |
         |                          |
         |                     192.168.23.0/30
         |                          |
         |                     +--------+
         +---------------------|   R3   |
                               +--------+
```

## Tasks

1. Enable RIP.
2. Configure Version 2.
3. Advertise all connected networks.
4. Verify learned routes.

## Configuration

```
R1(config)# router rip
R1(config-router)# version 2
R1(config-router)# no auto-summary
R1(config-router)# network 192.168.12.0
R1(config-router)# network 10.1.1.0
```

## Verification

```
R1# show ip route rip

R1# show ip protocols

R1# ping 10.3.3.1
```

## Expected Result

All routers successfully exchange routing information and
learn remote networks dynamically.

------------------------------------------------------------

# Lab 02 - Disable Automatic Summarization

## Objective

Configure RIP Version 2 in a discontiguous network and
disable automatic summarization.

## Topology

```
LAN A ---- R1 ===== R2 ===== R3 ---- LAN B
```

## Tasks

1. Configure RIP Version 2.
2. Disable auto summarization.
3. Verify routing table entries.

## Configuration

```
R2(config-router)# no auto-summary
```

## Verification

```
R2# show ip protocols

R2# show ip route rip
```

## Expected Result

Subnet routes are advertised without being summarized at
classful boundaries.

------------------------------------------------------------

# Lab 03 - Configure Passive Interfaces

## Objective

Prevent RIP updates from being sent toward user LANs while
continuing to advertise the connected networks.

## Topology

```
            User LAN
               |
           Gi0/1
               |
            +------+
WAN --------| R1   |
            +------+
               |
            Gi0/0
               |
            R2
```

## Tasks

1. Configure RIP.
2. Make the LAN interface passive.
3. Verify routing operation.

## Configuration

```
R1(config-router)# passive-interface GigabitEthernet0/1
```

## Verification

```
R1# show ip protocols
```

## Expected Result

RIP updates are no longer transmitted toward the user LAN,
while routing information continues to be advertised to RIP
neighbors.

------------------------------------------------------------

# Lab 04 - Advertise a Default Route

## Objective

Advertise a default route from an edge router connected to
an ISP.

## Topology

```
             ISP
              |
          +-------+
          |  R1   |
          +-------+
               |
          Enterprise
```

## Tasks

1. Configure a static default route.
2. Advertise it through RIP.
3. Verify remote routers receive the default route.

## Configuration

```
R1(config)# ip route 0.0.0.0 0.0.0.0 203.0.113.1

R1(config)# router rip

R1(config-router)# default-information originate
```

## Verification

```
show ip route

show ip route rip
```

## Expected Result

Neighboring routers install a dynamically learned default
route pointing toward the enterprise edge router.

------------------------------------------------------------

# Lab 05 - Configure RIPng

## Objective

Deploy RIPng between IPv6 routers.

## Topology

```
LAN ---- R1 ===== R2 ---- LAN
```

## Tasks

1. Enable IPv6 routing.
2. Create an RIPng process.
3. Enable RIPng on interfaces.
4. Verify IPv6 route exchange.

## Configuration

```
R1(config)# ipv6 unicast-routing

R1(config)# ipv6 router rip ENTERPRISE

R1(config)# interface GigabitEthernet0/0

R1(config-if)# ipv6 rip ENTERPRISE enable
```

## Verification

```
show ipv6 route rip

show ipv6 protocols

ping ipv6 2001:DB8:30::1
```

## Expected Result

All IPv6 routers successfully exchange routing information
through RIPng.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[02_RIP_Verification_Commands.md](02_RIP_Verification_Commands.md)**

➡️ Next: **[04_CheatSheet.md](04_CheatSheet.md)**
