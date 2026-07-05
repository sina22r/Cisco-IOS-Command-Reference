# VLAN Configuration Labs

---

**Volume:** 03 • VLAN Configuration

**Estimated Reading Time:** 40 Minutes

---

## Contents

- [Lab 01 - Create a VLAN](#lab-01---create-a-vlan)
- [Lab 02 - Configure an Access Port](#lab-02---configure-an-access-port)
- [Lab 03 - Configure a Trunk Link](#lab-03---configure-a-trunk-link)
- [Lab 04 - Configure a Voice VLAN](#lab-04---configure-a-voice-vlan)

---

# Lab 01 - Create a VLAN

## Objective

Create a new VLAN on a Cisco switch and verify that it has
been successfully added to the VLAN database.

## Topology

    PC -------- SW1

## Tasks

1. Create VLAN 10.
2. Assign the name SALES.
3. Verify the VLAN configuration.

## Configuration

    SW1(config)# vlan 10

    SW1(config-vlan)# name SALES

## Verification

    SW1# show vlan brief

    SW1# show vlan id 10

## Expected Result

VLAN 10 is successfully created, named SALES, and appears in
the VLAN database.

------------------------------------------------------------

# Lab 02 - Configure an Access Port

## Objective

Configure a switch interface as an access port and assign it
to a specific VLAN.

## Topology

    PC -------- SW1

## Tasks

1. Select interface GigabitEthernet0/1.
2. Configure the interface as an access port.
3. Assign VLAN 10.
4. Verify the configuration.

## Configuration

    SW1(config)# interface GigabitEthernet0/1

    SW1(config-if)# switchport mode access

    SW1(config-if)# switchport access vlan 10

## Verification

    SW1# show interfaces switchport

    SW1# show vlan brief

## Expected Result

The interface operates as an access port and is assigned to
VLAN 10.

------------------------------------------------------------

# Lab 03 - Configure a Trunk Link

## Objective

Configure a trunk link between two Cisco switches and verify
that multiple VLANs can traverse the link.

## Topology

    SW1 ---------------- SW2

## Tasks

1. Select the trunk interface on both switches.
2. Configure the interface as a trunk port.
3. Allow VLANs 10, 20, and 30.
4. Configure the native VLAN as VLAN 99.
5. Verify the trunk configuration.

## Configuration

    SW1(config)# interface GigabitEthernet0/1

    SW1(config-if)# switchport mode trunk

    SW1(config-if)# switchport trunk allowed vlan 10,20,30

    SW1(config-if)# switchport trunk native vlan 99

## Verification

    SW1# show interfaces trunk

    SW1# show interfaces switchport

## Expected Result

The interface operates as a trunk port, VLANs 10, 20, and 30
are allowed across the trunk, and VLAN 99 is configured as
the native VLAN.

------------------------------------------------------------

# Lab 04 - Configure a Voice VLAN

## Objective

Configure a voice VLAN for an IP phone connected to a switch
port while keeping data traffic in a separate access VLAN.

## Topology

    IP Phone
        |
       SW1
        |
        PC

## Tasks

1. Configure the interface as an access port.
2. Assign the data VLAN.
3. Configure the voice VLAN.
4. Verify the interface configuration.

## Configuration

    SW1(config)# interface GigabitEthernet0/10

    SW1(config-if)# switchport mode access

    SW1(config-if)# switchport access vlan 10

    SW1(config-if)# switchport voice vlan 50

## Verification

    SW1# show interfaces switchport

    SW1# show running-config interface GigabitEthernet0/10

## Expected Result

The interface is configured as an access port in VLAN 10,
while voice traffic is assigned to VLAN 50 for the connected
IP phone.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[02_VLAN_Verification_Commands.md](02_VLAN_Verification_Commands.md)**

➡️ Next: **[04_CheatSheet.md](04_CheatSheet.md)**
