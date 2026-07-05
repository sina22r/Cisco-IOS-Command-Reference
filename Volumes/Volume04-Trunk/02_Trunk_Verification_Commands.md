# Trunk Verification Commands

---

**Volume:** 04 • Trunk Configuration

**Estimated Reading Time:** 30 Minutes

---

## Contents

- [show interfaces trunk](#show-interfaces-trunk)
- [show interfaces switchport](#show-interfaces-switchport)
- [show interfaces status](#show-interfaces-status)
- [show vlan brief](#show-vlan-brief)
- [show spanning-tree interface](#show-spanning-tree-interface)
- [show cdp neighbors](#show-cdp-neighbors)
- [show running-config interface](#show-running-config-interface)

---

# show interfaces trunk

## Syntax:

    show interfaces trunk

## Example:

    SW1# show interfaces trunk

## Description:

**Displays all active trunk interfaces, including the native
VLAN, allowed VLANs, forwarding VLANs, encapsulation type,
and operational trunk status. This is the primary command for
verifying trunk configuration.**

------------------------------------------------------------

# show interfaces switchport

## Syntax:

    show interfaces switchport

## Example:

    SW1# show interfaces switchport

## Description:

**Displays Layer 2 switchport information such as operational
mode, administrative mode, access VLAN, native VLAN, voice
VLAN, trunk status, and DTP negotiation settings.**

------------------------------------------------------------

# show interfaces status

## Syntax:

    show interfaces status

## Example:

    SW1# show interfaces status

## Description:

**Displays a summary of switch interfaces including port
status, VLAN assignment, duplex mode, speed, and interface
type. Useful for quickly identifying interface-related
issues.**

------------------------------------------------------------

# show vlan brief

## Syntax:

    show vlan brief

## Example:

    SW1# show vlan brief

## Description:

**Displays all configured VLANs and the access ports assigned
to each VLAN. This command helps verify that the VLANs used
by the trunk exist on the switch.**

------------------------------------------------------------

# show spanning-tree interface

## Syntax:

    show spanning-tree interface INTERFACE

## Example:

    SW1# show spanning-tree interface GigabitEthernet0/1

## Description:

**Displays the Spanning Tree status of a specific interface,
including its role, state, cost, priority, and participation
in the spanning tree topology.**

------------------------------------------------------------

# show cdp neighbors

## Syntax:

    show cdp neighbors

## Example:

    SW1# show cdp neighbors

## Description:

**Displays directly connected Cisco devices. This command is
useful for verifying that the expected neighboring switch is
connected through the trunk link.**

------------------------------------------------------------

# show running-config interface

## Syntax:

    show running-config interface INTERFACE

## Example:

    SW1# show running-config interface GigabitEthernet0/1

## Description:

**Displays the running configuration of a specific interface,
allowing verification of trunk mode, native VLAN, allowed
VLANs, and other interface-specific settings.**

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[01_Trunk_Configuration_Commands.md](01_Trunk_Configuration_Commands.md)**

➡️ Next: **[03_Trunk_Labs.md](03_Trunk_Labs.md)**
