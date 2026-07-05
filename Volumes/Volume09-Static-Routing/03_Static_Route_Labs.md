# Static Route Labs

---

**Volume:** 09 • Static Routing

**Estimated Reading Time:** 60 Minutes

---

## Contents

- [Lab 01 - Configure an IPv4 Static Route](#lab-01---configure-an-ipv4-static-route)
- [Lab 02 - Configure a Default Route](#lab-02---configure-a-default-route)
- [Lab 03 - Configure a Floating Static Route](#lab-03---configure-a-floating-static-route)
- [Lab 04 - Configure an IPv6 Static Route](#lab-04---configure-an-ipv6-static-route)
- [Lab 05 - Configure a Null Route](#lab-05---configure-a-null-route)

---

# Lab 01 - Configure an IPv4 Static Route

## Objective

Configure a basic IPv4 static route between two routers.

## Topology

    LAN1 ----- R1 ===== R2 ----- LAN2

## Tasks

1. Configure interface IP addresses.
2. Configure an IPv4 static route.
3. Verify routing.
4. Test end-to-end connectivity.

## Configuration

    R1(config)# ip route 10.2.2.0 255.255.255.0 192.168.12.2

## Verification

    R1# show ip route

    R1# ping 10.2.2.1

## Expected Result

Traffic destined for the remote network is forwarded through
the configured next-hop router.

------------------------------------------------------------

# Lab 02 - Configure a Default Route

## Objective

Configure a default route toward an upstream router or ISP.

## Topology

    LAN ----- R1 ===== ISP

## Tasks

1. Configure the WAN link.
2. Configure the default route.
3. Verify Internet reachability.

## Configuration

    R1(config)# ip route 0.0.0.0 0.0.0.0 192.168.100.1

## Verification

    R1# show ip route

    R1# ping 8.8.8.8

## Expected Result

Unknown destinations are forwarded through the configured
default gateway.

------------------------------------------------------------

# Lab 03 - Configure a Floating Static Route

## Objective

Configure a backup static route using Administrative Distance.

## Topology

               Primary
          R1 ========= R2
           \          /
            \ Backup /
             \      /
              R3

## Tasks

1. Configure the primary route.
2. Configure the backup route.
3. Verify failover behavior.

## Configuration

    R1(config)# ip route 10.10.10.0 255.255.255.0 192.168.12.2

    R1(config)# ip route 10.10.10.0 255.255.255.0 192.168.13.2 200

## Verification

    R1# show ip route

## Expected Result

The backup route remains inactive until the preferred route
is removed or becomes unavailable.

------------------------------------------------------------

# Lab 04 - Configure an IPv6 Static Route

## Objective

Configure a static IPv6 route between two routers.

## Topology

    LAN ----- R1 ===== R2 ----- LAN

## Tasks

1. Configure IPv6 addressing.
2. Configure an IPv6 static route.
3. Verify connectivity.

## Configuration

    R1(config)# ipv6 route 2001:DB8:2::/64 FE80::2 GigabitEthernet0/0

## Verification

    R1# show ipv6 route

    R1# ping ipv6 2001:DB8:2::1

## Expected Result

IPv6 traffic successfully reaches the remote network using
the configured static route.

------------------------------------------------------------

# Lab 05 - Configure a Null Route

## Objective

Configure a Null0 route for summarized traffic.

## Topology

    R1

## Tasks

1. Configure a summary route.
2. Point the summary to Null0.
3. Verify the routing table.

## Configuration

    R1(config)# ip route 172.16.0.0 255.240.0.0 Null0

## Verification

    R1# show ip route

## Expected Result

Traffic matching the summary route is discarded by the Null0
interface, preventing routing loops and unwanted forwarding.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[02_Static_Route_Verification_Commands.md](02_Static_Route_Verification_Commands.md)**

➡️ Next: **[04_CheatSheet.md](04_CheatSheet.md)**
