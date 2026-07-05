# STP Labs

---

**Volume:** 05 • Spanning Tree Protocol

**Estimated Reading Time:** 50 Minutes

---

## Contents

- [Lab 01 - Configure the Root Bridge](#lab-01---configure-the-root-bridge)
- [Lab 02 - Configure the Secondary Root Bridge](#lab-02---configure-the-secondary-root-bridge)
- [Lab 03 - Configure PortFast](#lab-03---configure-portfast)
- [Lab 04 - Configure BPDU Guard](#lab-04---configure-bpdu-guard)

---

# Lab 01 - Configure the Root Bridge

## Objective

Configure a switch as the Root Bridge for VLAN 10.

## Topology

    SW1 -------- SW2
      \          /
        \      /
          SW3

## Tasks

1. Configure SW1 as the Root Bridge for VLAN 10.
2. Verify the Root Bridge election.
3. Verify the port roles.

## Configuration

    SW1(config)# spanning-tree vlan 10 root primary

## Verification

    SW1# show spanning-tree vlan 10

    SW1# show spanning-tree root

## Expected Result

SW1 becomes the Root Bridge for VLAN 10 and all port roles
are recalculated accordingly.

------------------------------------------------------------

# Lab 02 - Configure the Secondary Root Bridge

## Objective

Configure a backup Root Bridge for VLAN 10.

## Topology

    SW1 -------- SW2
      \          /
        \      /
          SW3

## Tasks

1. Configure SW2 as the secondary Root Bridge.
2. Verify the configuration.

## Configuration

    SW2(config)# spanning-tree vlan 10 root secondary

## Verification

    SW2# show spanning-tree root

    SW2# show spanning-tree vlan 10

## Expected Result

SW2 is prepared to become the Root Bridge if SW1 becomes
unavailable.

------------------------------------------------------------

# Lab 03 - Configure PortFast

## Objective

Enable PortFast on an access interface connected to an end
device.

## Topology

    PC -------- SW1

## Tasks

1. Select an access interface.
2. Enable PortFast.
3. Verify the configuration.

## Configuration

    SW1(config)# interface GigabitEthernet0/10

    SW1(config-if)# spanning-tree portfast

## Verification

    SW1# show spanning-tree interface GigabitEthernet0/10

## Expected Result

The interface transitions immediately to the Forwarding
state when it comes online.

------------------------------------------------------------

# Lab 04 - Configure BPDU Guard

## Objective

Protect an access port from receiving unexpected BPDUs.

## Topology

    PC -------- SW1

## Tasks

1. Enable BPDU Guard on the interface.
2. Verify the configuration.
3. Observe the interface behavior if a BPDU is received.

## Configuration

    SW1(config)# interface GigabitEthernet0/10

    SW1(config-if)# spanning-tree bpduguard enable

## Verification

    SW1# show spanning-tree summary

    SW1# show running-config interface GigabitEthernet0/10

## Expected Result

If the interface receives a BPDU, it immediately enters the
err-disabled state to protect the network from accidental
switching loops.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[04_STP_Protection_Features.md](04_STP_Protection_Features.md)**

➡️ Next: **[06_CheatSheet.md](06_CheatSheet.md)**
