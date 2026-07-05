# STP Configuration Commands

---

**Volume:** 05 • Spanning Tree Protocol

**Estimated Reading Time:** 50 Minutes

---

## Contents

- [spanning-tree mode](#spanning-tree-mode)
- [spanning-tree vlan priority](#spanning-tree-vlan-priority)
- [spanning-tree vlan root primary](#spanning-tree-vlan-root-primary)
- [spanning-tree vlan root secondary](#spanning-tree-vlan-root-secondary)
- [spanning-tree cost](#spanning-tree-cost)
- [spanning-tree port-priority](#spanning-tree-port-priority)
- [spanning-tree link-type](#spanning-tree-link-type)

---

# spanning-tree mode

## Syntax:

    spanning-tree mode {pvst | rapid-pvst | mst}

## Example:

    SW1(config)# spanning-tree mode rapid-pvst

## Description:

**Selects the Spanning Tree mode used by the switch. Cisco
supports PVST+, Rapid PVST+, and Multiple Spanning Tree
(MST), depending on the platform and IOS version.**

------------------------------------------------------------

# spanning-tree vlan priority

## Syntax:

    spanning-tree vlan VLAN_ID priority VALUE

## Example:

    SW1(config)# spanning-tree vlan 10 priority 4096

## Description:

**Sets the bridge priority for a VLAN. Lower priority values
increase the likelihood that the switch will become the Root
Bridge for that VLAN.**

------------------------------------------------------------

# spanning-tree vlan root primary

## Syntax:

    spanning-tree vlan VLAN_ID root primary

## Example:

    SW1(config)# spanning-tree vlan 10 root primary

## Description:

**Automatically adjusts the bridge priority to make the switch
the preferred Root Bridge for the specified VLAN whenever
possible.**

------------------------------------------------------------

# spanning-tree vlan root secondary

## Syntax:

    spanning-tree vlan VLAN_ID root secondary

## Example:

    SW1(config)# spanning-tree vlan 10 root secondary

## Description:

**Configures the switch as the secondary Root Bridge for the
specified VLAN. This switch becomes the backup Root Bridge if
the primary Root Bridge becomes unavailable.**

------------------------------------------------------------

# spanning-tree cost

## Syntax:

    spanning-tree cost COST

## Example:

    SW1(config-if)# spanning-tree cost 19

## Description:

**Manually assigns the STP path cost of an interface. Lower
cost paths are preferred when calculating the shortest path
to the Root Bridge.**

------------------------------------------------------------

# spanning-tree port-priority

## Syntax:

    spanning-tree port-priority PRIORITY

## Example:

    SW1(config-if)# spanning-tree port-priority 64

## Description:

**Configures the STP port priority. Lower values increase the
likelihood that the interface will become the designated port
when multiple equal-cost paths exist.**

------------------------------------------------------------

# spanning-tree link-type

## Syntax:

    spanning-tree link-type {point-to-point | shared}

## Example:

    SW1(config-if)# spanning-tree link-type point-to-point

## Description:

**Specifies the link type used by Rapid Spanning Tree. Point-
to-point links provide faster convergence between switches,
while shared links are typically connected through hubs.**

------------------------------------------------------------

# spanning-tree vlan forward-time

## Syntax:

    spanning-tree vlan VLAN_ID forward-time SECONDS

## Example:

    SW1(config)# spanning-tree vlan 10 forward-time 15

## Description:

**Configures the STP Forward Delay timer for the specified
VLAN. This timer controls how long a port remains in the
Listening and Learning states before forwarding traffic.**

------------------------------------------------------------

# spanning-tree vlan hello-time

## Syntax:

    spanning-tree vlan VLAN_ID hello-time SECONDS

## Example:

    SW1(config)# spanning-tree vlan 10 hello-time 2

## Description:

**Configures the Hello timer used by the Root Bridge to send
Bridge Protocol Data Units (BPDUs).**

------------------------------------------------------------

# spanning-tree vlan max-age

## Syntax:

    spanning-tree vlan VLAN_ID max-age SECONDS

## Example:

    SW1(config)# spanning-tree vlan 10 max-age 20

## Description:

**Configures the Maximum Age timer. This timer determines how
long STP retains BPDU information before considering it
invalid.**

------------------------------------------------------------

# spanning-tree extend system-id

## Syntax:

    spanning-tree extend system-id

## Example:

    SW1(config)# spanning-tree extend system-id

## Description:

**Enables the Extended System ID feature, allowing the VLAN
ID to be incorporated into the Bridge ID. This feature is
enabled by default on modern Cisco switches.**

------------------------------------------------------------

# spanning-tree backbonefast

## Syntax:

    spanning-tree backbonefast

## Example:

    SW1(config)# spanning-tree backbonefast

## Description:

**Enables BackboneFast to improve recovery time when indirect
link failures occur. This feature is primarily found on
legacy STP implementations.**

------------------------------------------------------------

# spanning-tree uplinkfast

## Syntax:

    spanning-tree uplinkfast

## Example:

    SW1(config)# spanning-tree uplinkfast

## Description:

**Enables UplinkFast to speed up convergence when an uplink
fails. This feature is available on legacy Cisco STP
implementations and has been replaced by Rapid STP on modern
networks.**

------------------------------------------------------------

## STP Summary

Spanning Tree Protocol prevents Layer 2 switching loops by
electing a Root Bridge and placing redundant links into a
blocking state. It provides redundancy while maintaining a
loop-free topology.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[README.md](README.md)**

➡️ Next: **[02_STP_Verification_Commands.md](02_STP_Verification_Commands.md)**
