# IPv6 Labs

---

**Volume:** 08 • IPv6

**Estimated Reading Time:** 50 Minutes

---

## Contents

- [Lab 01 - Configure a Global IPv6 Address](#lab-01---configure-a-global-ipv6-address)
- [Lab 02 - Configure an EUI-64 Address](#lab-02---configure-an-eui-64-address)
- [Lab 03 - Configure a Link-Local Address](#lab-03---configure-a-link-local-address)
- [Lab 04 - Configure SLAAC](#lab-04---configure-slaac)

---

# Lab 01 - Configure a Global IPv6 Address

## Objective

Configure IPv6 routing and assign a global unicast IPv6
address to an interface.

## Topology

    R1 -------- PC1
     Gi0/0

## Tasks

1. Enable IPv6 routing.
2. Configure a global IPv6 address.
3. Enable the interface.
4. Verify connectivity.

## Configuration

    R1(config)# ipv6 unicast-routing

    R1(config)# interface GigabitEthernet0/0

    R1(config-if)# ipv6 address 2001:DB8:10:1::1/64

    R1(config-if)# no shutdown

## Verification

    R1# show ipv6 interface brief

    R1# ping ipv6 2001:DB8:10:1::2

## Expected Result

The interface successfully forwards IPv6 traffic and responds
to ICMPv6 Echo Requests.

------------------------------------------------------------

# Lab 02 - Configure an EUI-64 Address

## Objective

Automatically generate the interface identifier using
EUI-64.

## Topology

    R1
     |
    Gi0/0

## Tasks

1. Configure an IPv6 prefix.
2. Enable EUI-64.
3. Verify the generated address.

## Configuration

    R1(config)# interface GigabitEthernet0/0

    R1(config-if)# ipv6 address 2001:DB8:20:1::/64 eui-64

## Verification

    R1# show ipv6 interface GigabitEthernet0/0

## Expected Result

Cisco IOS automatically generates the interface identifier
using the modified EUI-64 algorithm.

------------------------------------------------------------

# Lab 03 - Configure a Link-Local Address

## Objective

Configure a manual link-local IPv6 address.

## Topology

    R1 ---- R2

## Tasks

1. Configure a manual link-local address.
2. Verify neighbor communication.

## Configuration

    R1(config)# interface GigabitEthernet0/0

    R1(config-if)# ipv6 address FE80::1 link-local

## Verification

    R1# show ipv6 interface

    R1# show ipv6 neighbors

## Expected Result

The manually configured link-local address is used for
Neighbor Discovery and next-hop communication.

------------------------------------------------------------

# Lab 04 - Configure SLAAC

## Objective

Allow hosts to automatically configure IPv6 addresses using
Router Advertisements.

## Topology

    PC1 ---- R1

## Tasks

1. Enable IPv6 routing.
2. Configure a global prefix.
3. Verify automatic address assignment.

## Configuration

    R1(config)# ipv6 unicast-routing

    R1(config)# interface GigabitEthernet0/0

    R1(config-if)# ipv6 address 2001:DB8:30:1::1/64

## Verification

    R1# show ipv6 interface

    PC1> ipconfig

## Expected Result

The host automatically receives a valid IPv6 address using
Stateless Address Autoconfiguration (SLAAC).

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[02_IPv6_Verification_Commands.md](02_IPv6_Verification_Commands.md)**

➡️ Next: **[04_CheatSheet.md](04_CheatSheet.md)**
