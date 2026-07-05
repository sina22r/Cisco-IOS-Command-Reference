# IPv4 Labs

---

**Volume:** 07 • IPv4

**Estimated Reading Time:** 45 Minutes

---

## Contents

- [Lab 01 - Configure an IPv4 Address](#lab-01---configure-an-ipv4-address)
- [Lab 02 - Configure a Secondary IPv4 Address](#lab-02---configure-a-secondary-ipv4-address)
- [Lab 03 - Configure an Unnumbered Interface](#lab-03---configure-an-unnumbered-interface)
- [Lab 04 - Configure an IP Helper Address](#lab-04---configure-an-ip-helper-address)

---

# Lab 01 - Configure an IPv4 Address

## Objective

Assign an IPv4 address to a router interface and verify
connectivity.

## Topology

    R1 ---------------- PC1
     Gi0/0

## Tasks

1. Configure the IPv4 address.
2. Enable the interface.
3. Verify the configuration.
4. Test connectivity.

## Configuration

    R1(config)# interface GigabitEthernet0/0

    R1(config-if)# ip address 192.168.10.1 255.255.255.0

    R1(config-if)# no shutdown

## Verification

    R1# show ip interface brief

    R1# show ip interface GigabitEthernet0/0

    PC1> ping 192.168.10.1

## Expected Result

The interface is operational, has the correct IPv4 address,
and responds successfully to ICMP Echo Requests.

------------------------------------------------------------

# Lab 02 - Configure a Secondary IPv4 Address

## Objective

Configure an additional IPv4 address on an interface.

## Topology

    R1
     |
    Gi0/0

## Tasks

1. Configure the primary IPv4 address.
2. Configure the secondary IPv4 address.
3. Verify both addresses.

## Configuration

    R1(config)# interface GigabitEthernet0/0

    R1(config-if)# ip address 192.168.10.1 255.255.255.0

    R1(config-if)# ip address 192.168.20.1 255.255.255.0 secondary

## Verification

    R1# show running-config interface GigabitEthernet0/0

    R1# show ip interface GigabitEthernet0/0

## Expected Result

The interface successfully operates with both IPv4 networks.

------------------------------------------------------------

# Lab 03 - Configure an Unnumbered Interface

## Objective

Configure an interface to use the IPv4 address of another
local interface.

## Topology

    R1
   /  \
Lo0   S0/0/0

## Tasks

1. Configure Loopback0.
2. Configure the serial interface as unnumbered.
3. Verify the configuration.

## Configuration

    R1(config)# interface Loopback0

    R1(config-if)# ip address 10.10.10.1 255.255.255.255

    R1(config)# interface Serial0/0/0

    R1(config-if)# ip unnumbered Loopback0

    R1(config-if)# no shutdown

## Verification

    R1# show ip interface Serial0/0/0

    R1# show ip route

## Expected Result

The serial interface uses the IPv4 address assigned to
Loopback0 while maintaining Layer 3 connectivity.

------------------------------------------------------------

# Lab 04 - Configure an IP Helper Address

## Objective

Configure a router to relay DHCP broadcast requests to a
remote DHCP server.

## Topology

    PC1 ---- R1 ---- DHCP Server

## Tasks

1. Configure the client-facing interface.
2. Configure the helper address.
3. Verify DHCP relay operation.

## Configuration

    R1(config)# interface GigabitEthernet0/0

    R1(config-if)# ip helper-address 192.168.100.10

## Verification

    R1# show ip interface GigabitEthernet0/0

    R1# show running-config interface GigabitEthernet0/0

## Expected Result

DHCP broadcast requests received on the interface are
forwarded as unicast packets to the configured DHCP server.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[02_IPv4_Verification_Commands.md](02_IPv4_Verification_Commands.md)**

➡️ Next: **[04_CheatSheet.md](04_CheatSheet.md)**
