# Interface Configuration Labs

---

**Volume:** 02 • Interface Configuration

**Estimated Reading Time:** 35 Minutes

---

## Contents

- [Lab 01 - Configure an IPv4 Interface](#lab-01---configure-an-ipv4-interface)
- [Lab 02 - Configure an IPv6 Interface](#lab-02---configure-an-ipv6-interface)
- [Lab 03 - Configure Interface Speed and Duplex](#lab-03---configure-interface-speed-and-duplex)
- [Lab 04 - Restore an Interface to Default Settings](#lab-04---restore-an-interface-to-default-settings)

---

# Lab 01 - Configure an IPv4 Interface

## Objective

Configure an IPv4 address on a router interface and verify
connectivity.

## Topology

    PC -------- R1

## Tasks

1. Enter Interface Configuration mode.
2. Assign an IPv4 address.
3. Enable the interface.
4. Verify the interface status.
5. Save the configuration.

## Configuration

    R1(config)# interface GigabitEthernet0/0

    R1(config-if)# ip address 192.168.10.1 255.255.255.0

    R1(config-if)# no shutdown

    R1(config-if)# end

    R1# copy running-config startup-config

## Verification

    R1# show ip interface brief

    R1# show interfaces GigabitEthernet0/0

## Expected Result

The interface is in the up/up state with the configured
IPv4 address assigned successfully.

------------------------------------------------------------

# Lab 02 - Configure an IPv6 Interface

## Objective

Configure an IPv6 address on a router interface and verify
the configuration.

## Topology

    PC -------- R1

## Tasks

1. Enter Interface Configuration mode.
2. Assign an IPv6 address.
3. Enable the interface.
4. Verify the IPv6 configuration.

## Configuration

    R1(config)# ipv6 unicast-routing

    R1(config)# interface GigabitEthernet0/0

    R1(config-if)# ipv6 address 2001:DB8:10::1/64

    R1(config-if)# no shutdown

## Verification

    R1# show ipv6 interface

    R1# show ipv6 interface brief

## Expected Result

The interface is operational and the configured IPv6 address
appears in the interface configuration.

------------------------------------------------------------

# Lab 03 - Configure Interface Speed and Duplex

## Objective

Manually configure interface speed and duplex settings and
verify connectivity behavior.

## Topology

    PC -------- SW1 -------- PC

## Tasks

1. Enter interface configuration mode.
2. Disable auto-negotiation (if needed).
3. Configure speed and duplex manually.
4. Verify interface status.

## Configuration

    SW1(config)# interface GigabitEthernet0/1

    SW1(config-if)# speed 100

    SW1(config-if)# duplex full

    SW1(config-if)# end

## Verification

    SW1# show interfaces status

    SW1# show interfaces GigabitEthernet0/1

## Expected Result

The interface operates with manually configured speed and
duplex settings instead of auto-negotiation.

------------------------------------------------------------

# Lab 04 - Restore an Interface to Default Settings

## Objective

Reset an interface to factory default configuration.

## Topology

    PC -------- R1

## Tasks

1. Enter global configuration mode.
2. Reset the interface configuration.
3. Verify default state.

## Configuration

    R1(config)# default interface GigabitEthernet0/0

## Verification

    R1# show running-config interface GigabitEthernet0/0

    R1# show ip interface brief

## Expected Result

All interface-specific configurations are removed and the
interface returns to default administrative state.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[02_Interface_Verification_Commands.md](02_Interface_Verification_Commands.md)**

➡️ Next: **[04_CheatSheet.md](04_CheatSheet.md)**
