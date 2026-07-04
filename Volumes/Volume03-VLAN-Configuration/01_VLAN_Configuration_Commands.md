# VLAN Configuration Commands

---

**Volume:** 03 • VLAN Configuration

**Estimated Reading Time:** 50 Minutes

---
## Contents

- [vlan](#vlan)
- [name](#name)
- [show vlan brief](#show-vlan-brief)
- [show vlan id](#show-vlan-id)
- [switchport mode access](#switchport-mode-access)
- [switchport access vlan](#switchport-access-vlan)
- [switchport mode trunk](#switchport-mode-trunk)
- [switchport nonegotiate](#switchport-nonegotiate)
- [switchport trunk allowed vlan](#switchport-trunk-allowed-vlan)
- [switchport trunk native vlan](#switchport-trunk-native-vlan)
- [switchport voice vlan](#switchport-voice-vlan)
- [show interfaces trunk](#show-interfaces-trunk)
- [show interfaces switchport](#show-interfaces-switchport)
- [vlan summary](#vlan-summary)
---

# vlan

## Syntax

    vlan VLAN_ID

## Example

    SW1(config)# vlan 10

## Description

    Creates a VLAN in the VLAN database. VLANs are used to
    logically segment Layer 2 networks into separate broadcast
    domains.

------------------------------------------------------------

# name

## Syntax

    name VLAN_NAME

## Example

    SW1(config-vlan)# name SALES

## Description

    Assigns a descriptive name to a VLAN to improve
    readability and network management.

------------------------------------------------------------

# show vlan brief

## Syntax

    show vlan brief

## Example

    SW1# show vlan brief

## Description

    Displays a summary of all VLANs on the switch, including
    VLAN ID, name, and associated ports.

------------------------------------------------------------

# show vlan id

## Syntax

    show vlan id VLAN_ID

## Example

    SW1# show vlan id 10

## Description

    Displays detailed information about a specific VLAN,
    including assigned ports and VLAN status.

------------------------------------------------------------

# switchport mode access

## Syntax

    switchport mode access

## Example

    SW1(config-if)# switchport mode access

## Description

    Configures the interface as an access port. An access port
    belongs to a single VLAN and is used for end devices such
    as PCs, printers, and servers.

------------------------------------------------------------

# switchport access vlan

## Syntax

    switchport access vlan VLAN_ID

## Example

    SW1(config-if)# switchport access vlan 10

## Description

    Assigns an access port to a specific VLAN. All traffic
    on this interface will belong to the configured VLAN.

------------------------------------------------------------

# switchport mode trunk

## Syntax

    switchport mode trunk

## Example

    SW1(config-if)# switchport mode trunk

## Description

    Configures the interface as a trunk port. A trunk port
    can carry traffic for multiple VLANs between switches.

------------------------------------------------------------

# switchport nonegotiate

## Syntax

    switchport nonegotiate

## Example

    SW1(config-if)# switchport nonegotiate

## Description

    Disables Dynamic Trunking Protocol (DTP) negotiation.
    Used when manually configuring trunk links for security
    and stability.

------------------------------------------------------------

# switchport trunk allowed vlan

## Syntax

    switchport trunk allowed vlan VLAN_LIST

## Example

    SW1(config-if)# switchport trunk allowed vlan 10,20,30

## Description

    Defines which VLANs are allowed to pass through a trunk
    interface. This helps control and limit VLAN traffic
    between switches.

------------------------------------------------------------

# switchport trunk native vlan

## Syntax

    switchport trunk native vlan VLAN_ID

## Example

    SW1(config-if)# switchport trunk native vlan 99

## Description

    Defines the native VLAN on a trunk link. Untagged traffic
    is assigned to this VLAN.

------------------------------------------------------------

# switchport voice vlan

## Syntax

    switchport voice vlan VLAN_ID

## Example

    SW1(config-if)# switchport voice vlan 50

## Description

    Assigns a separate VLAN for voice traffic (IP phones)
    while keeping data traffic in a different VLAN.

------------------------------------------------------------

# show interfaces trunk

## Syntax

    show interfaces trunk

## Example

    SW1# show interfaces trunk

## Description

    Displays all trunk interfaces and shows allowed VLANs,
    native VLAN, and trunk status.

------------------------------------------------------------

# show interfaces switchport

## Syntax

    show interfaces switchport

## Example

    SW1# show interfaces switchport

## Description

    Shows Layer 2 configuration of switch ports including
    access/trunk mode and VLAN assignment.

------------------------------------------------------------

## VLAN Summary

VLANs are used to logically separate Layer 2 networks into
different broadcast domains. Access ports belong to one VLAN,
while trunk ports carry multiple VLANs between switches.

------------------------------------------------------------

## Navigation

⬅️ Previous: Part 2

➡️ Next: 02_VLAN_Verification_Commands.md
