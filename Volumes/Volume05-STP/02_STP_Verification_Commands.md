# STP Verification Commands

---

**Volume:** 05 • Spanning Tree Protocol

**Estimated Reading Time:** 35 Minutes

---

## Contents

- [show spanning-tree](#show-spanning-tree)
- [show spanning-tree vlan](#show-spanning-tree-vlan)
- [show spanning-tree root](#show-spanning-tree-root)
- [show spanning-tree summary](#show-spanning-tree-summary)
- [show spanning-tree interface](#show-spanning-tree-interface)
- [show spanning-tree blockedports](#show-spanning-tree-blockedports)
- [show spanning-tree detail](#show-spanning-tree-detail)
- [show spanning-tree inconsistentports](#show-spanning-tree-inconsistentports)

---

# show spanning-tree

## Syntax:

    show spanning-tree

## Example:

    SW1# show spanning-tree

## Description:

**Displays complete Spanning Tree information for all VLANs,
including the Root Bridge, Bridge ID, port roles, port
states, path costs, timers, and interface participation.**

------------------------------------------------------------

# show spanning-tree vlan

## Syntax:

    show spanning-tree vlan VLAN_ID

## Example:

    SW1# show spanning-tree vlan 10

## Description:

**Displays Spanning Tree information for a specific VLAN,
including the Root Bridge, designated ports, blocked ports,
and interface roles.**

------------------------------------------------------------

# show spanning-tree root

## Syntax:

    show spanning-tree root

## Example:

    SW1# show spanning-tree root

## Description:

**Displays the Root Bridge information for every VLAN and
indicates whether the local switch is acting as the Root
Bridge.**

------------------------------------------------------------

# show spanning-tree summary

## Syntax:

    show spanning-tree summary

## Example:

    SW1# show spanning-tree summary

## Description:

**Displays a summary of the Spanning Tree configuration,
including the operating mode, protection features, and the
number of interfaces participating in STP.**

------------------------------------------------------------

# show spanning-tree interface

## Syntax:

    show spanning-tree interface INTERFACE

## Example:

    SW1# show spanning-tree interface GigabitEthernet0/1

## Description:

**Displays STP information for a specific interface,
including the port role, port state, path cost, and priority.**

------------------------------------------------------------

# show spanning-tree blockedports

## Syntax:

    show spanning-tree blockedports

## Example:

    SW1# show spanning-tree blockedports

## Description:

**Displays all interfaces currently in a blocking state due
to Spanning Tree. This command is useful for identifying
redundant links that are preventing Layer 2 loops.**

------------------------------------------------------------

# show spanning-tree detail

## Syntax:

    show spanning-tree detail

## Example:

    SW1# show spanning-tree detail

## Description:

**Displays detailed STP information, including topology
changes, BPDU statistics, timers, Root Bridge information,
and interface details.**

------------------------------------------------------------

# show spanning-tree inconsistentports

## Syntax:

    show spanning-tree inconsistentports

## Example:

    SW1# show spanning-tree inconsistentports

## Description:

**Displays interfaces that have been placed into an
inconsistent state due to STP protection features such as
Root Guard or Loop Guard.**

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[01_STP_Configuration_Commands.md](01_STP_Configuration_Commands.md)**

➡️ Next: **[03_RSTP_Commands.md](03_RSTP_Commands.md)**
