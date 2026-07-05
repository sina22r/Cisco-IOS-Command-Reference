# Rapid Spanning Tree (RSTP) Commands

---

**Volume:** 05 • Spanning Tree Protocol

**Estimated Reading Time:** 25 Minutes

---

## Contents

- [spanning-tree mode rapid-pvst](#spanning-tree-mode-rapid-pvst)
- [show spanning-tree summary](#show-spanning-tree-summary)
- [show spanning-tree vlan](#show-spanning-tree-vlan)
- [show spanning-tree interface](#show-spanning-tree-interface)
- [show spanning-tree root](#show-spanning-tree-root)

---

# spanning-tree mode rapid-pvst

## Syntax:

    spanning-tree mode rapid-pvst

## Example:

    SW1(config)# spanning-tree mode rapid-pvst

## Description:

**Enables Rapid PVST+, Cisco's implementation of IEEE 802.1w.
Rapid PVST+ provides significantly faster convergence than
traditional STP while maintaining one spanning tree instance
per VLAN.**

------------------------------------------------------------

# show spanning-tree summary

## Syntax:

    show spanning-tree summary

## Example:

    SW1# show spanning-tree summary

## Description:

**Displays the current spanning-tree mode and confirms whether
Rapid PVST+ is enabled on the switch. It also shows the status
of STP protection features.**

------------------------------------------------------------

# show spanning-tree vlan

## Syntax:

    show spanning-tree vlan VLAN_ID

## Example:

    SW1# show spanning-tree vlan 20

## Description:

**Displays Rapid STP information for the specified VLAN,
including port roles, port states, path cost, and the Root
Bridge.**

------------------------------------------------------------

# show spanning-tree interface

## Syntax:

    show spanning-tree interface INTERFACE

## Example:

    SW1# show spanning-tree interface GigabitEthernet0/1

## Description:

**Displays Rapid STP information for a specific interface,
including the current port role, forwarding state, path cost,
and interface priority.**

------------------------------------------------------------

# show spanning-tree root

## Syntax:

    show spanning-tree root

## Example:

    SW1# show spanning-tree root

## Description:

**Displays the Root Bridge for each VLAN and indicates whether
the local switch is operating as the Root Bridge under Rapid
PVST+.**

------------------------------------------------------------

## RSTP Summary

Rapid Spanning Tree Protocol (IEEE 802.1w) provides much
faster convergence than classic STP by introducing new port
roles and synchronization mechanisms while maintaining
compatibility with existing STP networks.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[02_STP_Verification_Commands.md](02_STP_Verification_Commands.md)**

➡️ Next: **[04_STP_Protection_Features.md](04_STP_Protection_Features.md)**
