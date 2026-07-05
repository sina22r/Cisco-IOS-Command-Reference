# EtherChannel Labs

---

**Volume:** 06 • EtherChannel

**Estimated Reading Time:** 45 Minutes

---

## Contents

- [Lab 01 - Configure a Static EtherChannel](#lab-01---configure-a-static-etherchannel)
- [Lab 02 - Configure an LACP EtherChannel](#lab-02---configure-an-lacp-etherchannel)
- [Lab 03 - Configure a PAgP EtherChannel](#lab-03---configure-a-pagp-etherchannel)
- [Lab 04 - Configure a Layer 3 EtherChannel](#lab-04---configure-a-layer-3-etherchannel)

---

# Lab 01 - Configure a Static EtherChannel

## Objective

Configure a static EtherChannel between two switches without
using a negotiation protocol.

## Topology

    SW1 ================= SW2
      Gi0/1           Gi0/1
      Gi0/2           Gi0/2

## Tasks

1. Configure the member interfaces.
2. Create Port-Channel 1.
3. Verify the EtherChannel status.

## Configuration

    SW1(config)# interface range GigabitEthernet0/1-2

    SW1(config-if-range)# channel-group 1 mode on

    SW1(config-if-range)# exit

    SW1(config)# interface port-channel 1

    SW1(config-if)# switchport mode trunk

## Verification

    SW1# show etherchannel summary

    SW1# show interfaces port-channel 1

## Expected Result

Both physical interfaces are bundled into Port-Channel 1 and
operate as a single logical interface.

------------------------------------------------------------

# Lab 02 - Configure an LACP EtherChannel

## Objective

Configure an EtherChannel using the IEEE LACP negotiation
protocol.

## Topology

    SW1 ================= SW2
      Gi0/1           Gi0/1
      Gi0/2           Gi0/2

## Tasks

1. Configure LACP on both switches.
2. Verify successful negotiation.
3. Verify the Port-Channel interface.

## Configuration

    SW1(config)# interface range GigabitEthernet0/1-2

    SW1(config-if-range)# channel-protocol lacp

    SW1(config-if-range)# channel-group 1 mode active

## Verification

    SW1# show etherchannel summary

    SW1# show lacp neighbor

## Expected Result

The EtherChannel is established using LACP and both
interfaces participate in the bundle.

------------------------------------------------------------

# Lab 03 - Configure a PAgP EtherChannel

## Objective

Configure an EtherChannel using Cisco PAgP.

## Topology

    SW1 ================= SW2
      Gi0/1           Gi0/1
      Gi0/2           Gi0/2

## Tasks

1. Configure PAgP on both switches.
2. Verify neighbor discovery.
3. Verify the Port-Channel status.

## Configuration

    SW1(config)# interface range GigabitEthernet0/1-2

    SW1(config-if-range)# channel-protocol pagp

    SW1(config-if-range)# channel-group 1 mode desirable

## Verification

    SW1# show etherchannel summary

    SW1# show pagp neighbor

## Expected Result

The EtherChannel is established using PAgP and all member
interfaces operate correctly.

------------------------------------------------------------

# Lab 04 - Configure a Layer 3 EtherChannel

## Objective

Configure a routed EtherChannel between two Layer 3 switches.

## Topology

    SW1 ================= SW2
      Gi0/1           Gi0/1
      Gi0/2           Gi0/2

## Tasks

1. Remove Layer 2 switching.
2. Configure the Port-Channel as a routed interface.
3. Assign IP addresses.
4. Verify Layer 3 connectivity.

## Configuration

    SW1(config)# interface range GigabitEthernet0/1-2

    SW1(config-if-range)# no switchport

    SW1(config-if-range)# channel-group 10 mode active

    SW1(config)# interface port-channel 10

    SW1(config-if)# no switchport

    SW1(config-if)# ip address 10.10.10.1 255.255.255.252

## Verification

    SW1# show etherchannel summary

    SW1# show interfaces port-channel 10

    SW1# ping 10.10.10.2

## Expected Result

The routed Port-Channel is operational, member interfaces are
bundled correctly, and IP connectivity between the switches
is successful.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[02_EtherChannel_Verification_Commands.md](02_EtherChannel_Verification_Commands.md)**

➡️ Next: **[04_CheatSheet.md](04_CheatSheet.md)**
