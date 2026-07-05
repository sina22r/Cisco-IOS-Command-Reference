# Trunk Configuration Commands

---

**Volume:** 04 • Trunk Configuration

**Estimated Reading Time:** 45 Minutes

---

## Contents

- [switchport mode trunk](#switchport-mode-trunk)
- [switchport trunk encapsulation](#switchport-trunk-encapsulation)
- [switchport trunk native vlan](#switchport-trunk-native-vlan)
- [switchport trunk allowed vlan](#switchport-trunk-allowed-vlan)
- [switchport trunk allowed vlan add](#switchport-trunk-allowed-vlan-add)
- [switchport trunk allowed vlan remove](#switchport-trunk-allowed-vlan-remove)
- [switchport nonegotiate](#switchport-nonegotiate)

---

# switchport mode trunk

## Syntax:

    switchport mode trunk

## Example:

    SW1(config-if)# switchport mode trunk

## Description:

**Configures the interface as a trunk port. A trunk port
carries traffic for multiple VLANs across a single physical
link using IEEE 802.1Q encapsulation.**

------------------------------------------------------------

# switchport trunk encapsulation

## Syntax:

    switchport trunk encapsulation dot1q

## Example:

    SW1(config-if)# switchport trunk encapsulation dot1q

## Description:

**Specifies the trunk encapsulation method. On platforms that
support multiple encapsulation types, IEEE 802.1Q is the
standard method used for VLAN tagging.**

------------------------------------------------------------

# switchport trunk native vlan

## Syntax:

    switchport trunk native vlan VLAN_ID

## Example:

    SW1(config-if)# switchport trunk native vlan 99

## Description:

**Assigns the native VLAN for the trunk link. Frames that are
sent without an IEEE 802.1Q tag are associated with the
configured native VLAN.**

------------------------------------------------------------

# switchport trunk allowed vlan

## Syntax:

    switchport trunk allowed vlan VLAN_LIST

## Example:

    SW1(config-if)# switchport trunk allowed vlan 10,20,30

## Description:

**Specifies which VLANs are permitted to traverse the trunk
link. Only the configured VLANs are allowed to pass through
the trunk interface.**

------------------------------------------------------------

# switchport trunk allowed vlan add

## Syntax:

    switchport trunk allowed vlan add VLAN_LIST

## Example:

    SW1(config-if)# switchport trunk allowed vlan add 40

## Description:

**Adds one or more VLANs to the existing list of allowed
VLANs on the trunk without removing the current
configuration.**

------------------------------------------------------------

# switchport trunk allowed vlan remove

## Syntax:

    switchport trunk allowed vlan remove VLAN_LIST

## Example:

    SW1(config-if)# switchport trunk allowed vlan remove 20

## Description:

**Removes one or more VLANs from the allowed VLAN list on a
trunk interface while leaving the remaining VLANs
unchanged.**

------------------------------------------------------------

# switchport nonegotiate

## Syntax:

    switchport nonegotiate

## Example:

    SW1(config-if)# switchport nonegotiate

## Description:

**Disables Dynamic Trunking Protocol (DTP) negotiation on
the interface. This command is commonly used when the trunk
is configured manually or when connecting to devices that do
not support DTP.**

------------------------------------------------------------

## Trunk Summary

A trunk link carries traffic for multiple VLANs over a
single physical interface. IEEE 802.1Q tagging identifies
the VLAN membership of each frame, while the native VLAN
handles untagged traffic.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[README.md](README.md)**

➡️ Next: **[02_Trunk_Verification_Commands.md](02_Trunk_Verification_Commands.md)**
