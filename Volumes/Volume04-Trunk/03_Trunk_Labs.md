# Trunk Configuration Labs

---

**Volume:** 04 • Trunk Configuration

**Estimated Reading Time:** 40 Minutes

---

## Contents

- [Lab 01 - Configure a Trunk Link](#lab-01---configure-a-trunk-link)
- [Lab 02 - Configure Allowed VLANs](#lab-02---configure-allowed-vlans)
- [Lab 03 - Configure a Native VLAN](#lab-03---configure-a-native-vlan)
- [Lab 04 - Disable DTP Negotiation](#lab-04---disable-dtp-negotiation)

---

# Lab 01 - Configure a Trunk Link

## Objective

Configure a trunk link between two Cisco switches using
IEEE 802.1Q encapsulation.

## Topology

    SW1 ---------------- SW2

## Tasks

1. Select the trunk interface.
2. Configure the interface as a trunk.
3. Verify trunk operation.

## Configuration

    SW1(config)# interface GigabitEthernet0/1

    SW1(config-if)# switchport mode trunk

## Verification

    SW1# show interfaces trunk

    SW1# show interfaces switchport

## Expected Result

The interface operates as a trunk link and is capable of
carrying traffic for multiple VLANs.

------------------------------------------------------------

# Lab 02 - Configure Allowed VLANs

## Objective

Restrict the VLANs that are permitted to cross a trunk
interface.

## Topology

    SW1 ---------------- SW2

## Tasks

1. Configure the trunk interface.
2. Allow only VLANs 10, 20, and 30.
3. Verify the configuration.

## Configuration

    SW1(config)# interface GigabitEthernet0/1

    SW1(config-if)# switchport trunk allowed vlan 10,20,30

## Verification

    SW1# show interfaces trunk

    SW1# show running-config interface GigabitEthernet0/1

## Expected Result

Only VLANs 10, 20, and 30 are allowed to pass through the
trunk interface.

------------------------------------------------------------

# Lab 03 - Configure a Native VLAN

## Objective

Configure a native VLAN for a trunk interface and verify the
configuration.

## Topology

    SW1 ---------------- SW2

## Tasks

1. Select the trunk interface.
2. Configure VLAN 99 as the native VLAN.
3. Verify the configuration.

## Configuration

    SW1(config)# interface GigabitEthernet0/1

    SW1(config-if)# switchport trunk native vlan 99

## Verification

    SW1# show interfaces trunk

    SW1# show interfaces switchport

## Expected Result

The trunk interface uses VLAN 99 as the native VLAN for
untagged traffic.

------------------------------------------------------------

# Lab 04 - Disable DTP Negotiation

## Objective

Disable Dynamic Trunking Protocol (DTP) negotiation on a
manually configured trunk interface.

## Topology

    SW1 ---------------- SW2

## Tasks

1. Configure the interface as a trunk.
2. Disable DTP negotiation.
3. Verify the interface configuration.

## Configuration

    SW1(config)# interface GigabitEthernet0/1

    SW1(config-if)# switchport mode trunk

    SW1(config-if)# switchport nonegotiate

## Verification

    SW1# show interfaces switchport

    SW1# show running-config interface GigabitEthernet0/1

## Expected Result

The interface remains in trunk mode and DTP negotiation is
disabled.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[02_Trunk_Verification_Commands.md](02_Trunk_Verification_Commands.md)**

➡️ Next: **[04_CheatSheet.md](04_CheatSheet.md)**
