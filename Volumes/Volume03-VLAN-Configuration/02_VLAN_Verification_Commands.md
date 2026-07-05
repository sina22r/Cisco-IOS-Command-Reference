# VLAN Verification Commands

---

**Volume:** 03 • VLAN Configuration

**Estimated Reading Time:** 30 Minutes

---

## Contents

- [show vlan](#show-vlan)
- [show vlan brief](#show-vlan-brief)
- [show vlan id](#show-vlan-id)
- [show interfaces switchport](#show-interfaces-switchport)
- [show interfaces trunk](#show-interfaces-trunk)
- [show interfaces status](#show-interfaces-status)
- [show mac address-table](#show-mac-address-table)
- [show running-config interface](#show-running-config-interface)

---

# show vlan

## Syntax:

    show vlan

## Example:

    SW1# show vlan

## Description:

**Displays all configured VLANs on the switch, including their
names, status, and associated access ports.**

------------------------------------------------------------

# show vlan brief

## Syntax:

    show vlan brief

## Example:

    SW1# show vlan brief

## Description:

**Displays a summarized list of VLANs, making it easier to
quickly verify VLAN IDs, names, status, and assigned ports.**

------------------------------------------------------------

# show vlan id

## Syntax:

    show vlan id VLAN_ID

## Example:

    SW1# show vlan id 10

## Description:

**Displays detailed information about a specific VLAN,
including its member interfaces and operational status.**

------------------------------------------------------------

# show interfaces switchport

## Syntax:

    show interfaces switchport

## Example:

    SW1# show interfaces switchport

## Description:

**Displays Layer 2 switchport information such as operational
mode, administrative mode, access VLAN, native VLAN, voice
VLAN, and trunk settings.**

------------------------------------------------------------

# show interfaces trunk

## Syntax:

    show interfaces trunk

## Example:

    SW1# show interfaces trunk

## Description:

**Displays all active trunk interfaces, including native VLAN,
allowed VLANs, and forwarding status.**

------------------------------------------------------------

# show interfaces status

## Syntax:

    show interfaces status

## Example:

    SW1# show interfaces status

## Description:

**Displays a summary of all switch interfaces, including port
status, VLAN assignment, duplex mode, speed, and interface
type. This command is useful for quickly identifying interface
and VLAN-related issues.**

------------------------------------------------------------

# show mac address-table

## Syntax:

    show mac address-table

## Example:

    SW1# show mac address-table

## Description:

**Displays the MAC address table of the switch, including
learned MAC addresses, associated VLANs, interface mappings,
and entry types. This command is commonly used to verify
Layer 2 forwarding and VLAN operation.**

------------------------------------------------------------

# show running-config interface

## Syntax:

    show running-config interface INTERFACE

## Example:

    SW1# show running-config interface GigabitEthernet0/1

## Description:

**Displays the running configuration of a specific interface,
allowing you to verify VLAN assignments, switchport mode,
descriptions, and other interface-specific settings.**

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[01_VLAN_Configuration_Commands.md](01_VLAN_Configuration_Commands.md)**

➡️ Next: **[03_VLAN_Labs.md](03_VLAN_Labs.md)**
