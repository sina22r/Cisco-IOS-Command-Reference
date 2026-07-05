# IPv6 Configuration Commands

---

**Volume:** 08 • IPv6

**Estimated Reading Time:** 70 Minutes

---

## Contents

- [ipv6 unicast-routing](#ipv6-unicast-routing)
- [ipv6 enable](#ipv6-enable)
- [ipv6 address](#ipv6-address)
- [ipv6 address eui-64](#ipv6-address-eui-64)
- [ipv6 address link-local](#ipv6-address-link-local)
- [ipv6 address autoconfig](#ipv6-address-autoconfig)
- [no ipv6 address](#no-ipv6-address)
- [ipv6 mtu](#ipv6-mtu)
- [ipv6 nd reachable-time](#ipv6-nd-reachable-time)
- [ipv6 nd ra interval](#ipv6-nd-ra-interval)
- [ipv6 nd other-config-flag](#ipv6-nd-other-config-flag)
- [ipv6 nd managed-config-flag](#ipv6-nd-managed-config-flag)

---

# ipv6 unicast-routing

## Syntax:

    ipv6 unicast-routing

## Example:

    R1(config)# ipv6 unicast-routing

## Description:

**Enables IPv6 packet forwarding globally on the device.
Without this command, the router processes IPv6 packets only
for its own interfaces and does not forward traffic between
IPv6 networks.**

------------------------------------------------------------

# ipv6 enable

## Syntax:

    ipv6 enable

## Example:

    R1(config)# interface GigabitEthernet0/0

    R1(config-if)# ipv6 enable

## Description:

**Enables IPv6 processing on an interface and automatically
creates a link-local IPv6 address if one does not already
exist. This command does not assign a global IPv6 address.**

------------------------------------------------------------

# ipv6 address

## Syntax:

    ipv6 address IPV6_ADDRESS/PREFIX_LENGTH

## Example:

    R1(config)# interface GigabitEthernet0/0

    R1(config-if)# ipv6 address 2001:DB8:10:1::1/64

## Description:

**Assigns a global IPv6 address to an interface. Multiple
IPv6 addresses may be configured on the same interface,
allowing simultaneous communication across different IPv6
networks.**

------------------------------------------------------------

# ipv6 address eui-64

## Syntax:

    ipv6 address IPV6_PREFIX eui-64

## Example:

    R1(config)# interface GigabitEthernet0/0

    R1(config-if)# ipv6 address 2001:DB8:10:1::/64 eui-64

## Description:

**Automatically generates the interface identifier using the
modified EUI-64 algorithm and combines it with the specified
IPv6 prefix to create a global unicast address.**

------------------------------------------------------------

# ipv6 address link-local

## Syntax:

    ipv6 address IPV6_ADDRESS link-local

## Example:

    R1(config-if)# ipv6 address FE80::1 link-local

## Description:

**Configures a manually assigned link-local IPv6 address.
Link-local addresses are used for communication on the local
link and are required for Neighbor Discovery, routing
protocols, and next-hop communication.**

------------------------------------------------------------

# ipv6 address autoconfig

## Syntax:

    ipv6 address autoconfig

## Example:

    R1(config-if)# ipv6 address autoconfig

## Description:

**Automatically configures a global IPv6 address using
Router Advertisements (RA) received from an IPv6 router. The
address is generated through Stateless Address
Autoconfiguration (SLAAC).**

------------------------------------------------------------

# no ipv6 address

## Syntax:

    no ipv6 address IPV6_ADDRESS/PREFIX_LENGTH

## Example:

    R1(config-if)# no ipv6 address 2001:DB8:10:1::1/64

## Description:

**Removes the specified IPv6 address from the interface
without affecting any other configured IPv6 addresses.**

------------------------------------------------------------

# ipv6 mtu

## Syntax:

    ipv6 mtu BYTES

## Example:

    R1(config-if)# ipv6 mtu 1400

## Description:

**Configures the maximum transmission unit for IPv6 packets
on the interface. Packets exceeding this value are handled
according to IPv6 Path MTU Discovery mechanisms.**

------------------------------------------------------------

# ipv6 nd reachable-time

## Syntax:

    ipv6 nd reachable-time MILLISECONDS

## Example:

    R1(config-if)# ipv6 nd reachable-time 30000

## Description:

**Configures the Neighbor Discovery Reachable Time, which
determines how long a neighbor is considered reachable after
successful communication.**

------------------------------------------------------------

# ipv6 nd ra interval

## Syntax:

    ipv6 nd ra interval SECONDS

## Example:

    R1(config-if)# ipv6 nd ra interval 30

## Description:

**Configures the interval between Router Advertisement (RA)
messages sent by the interface. These advertisements are used
by IPv6 hosts for Stateless Address Autoconfiguration
(SLAAC).**

------------------------------------------------------------

# ipv6 nd managed-config-flag

## Syntax:

    ipv6 nd managed-config-flag

## Example:

    R1(config-if)# ipv6 nd managed-config-flag

## Description:

**Sets the Managed (M) flag in Router Advertisement messages,
indicating that hosts should obtain IPv6 addresses from a
DHCPv6 server instead of using SLAAC.**

------------------------------------------------------------

# ipv6 nd other-config-flag

## Syntax:

    ipv6 nd other-config-flag

## Example:

    R1(config-if)# ipv6 nd other-config-flag

## Description:

**Sets the Other Configuration (O) flag in Router
Advertisement messages, indicating that hosts should obtain
additional configuration information, such as DNS servers,
from DHCPv6.**

------------------------------------------------------------

# ipv6 nd prefix

## Syntax:

    ipv6 nd prefix IPV6_PREFIX/PREFIX_LENGTH

## Example:

    R1(config-if)# ipv6 nd prefix 2001:DB8:10:1::/64

## Description:

**Advertises an IPv6 prefix in Router Advertisement messages,
allowing hosts to automatically generate IPv6 addresses using
Stateless Address Autoconfiguration (SLAAC).**

------------------------------------------------------------

# ipv6 nd suppress-ra

## Syntax:

    ipv6 nd suppress-ra

## Example:

    R1(config-if)# ipv6 nd suppress-ra

## Description:

**Disables the transmission of Router Advertisement messages
on the interface. Hosts connected to the interface will no
longer receive automatic IPv6 configuration information.**

------------------------------------------------------------

# ipv6 traffic-filter

## Syntax:

    ipv6 traffic-filter ACL_NAME {in | out}

## Example:

    R1(config-if)# ipv6 traffic-filter IPV6-FILTER in

## Description:

**Applies an IPv6 Access Control List (ACL) to an interface
for inbound or outbound IPv6 traffic filtering.**

------------------------------------------------------------

# ipv6 ospf

## Syntax:

    ipv6 ospf PROCESS_ID area AREA_ID

## Example:

    R1(config-if)# ipv6 ospf 1 area 0

## Description:

**Enables OSPFv3 on the interface and associates it with the
specified OSPF process and area. Detailed OSPFv3 operation is
covered in the OSPF volume.**

------------------------------------------------------------

# ipv6 rip

## Syntax:

    ipv6 rip PROCESS_NAME enable

## Example:

    R1(config-if)# ipv6 rip RIPNG enable

## Description:

**Enables RIPng on the interface. Complete RIPng
configuration and verification are covered in the RIP
volume.**

------------------------------------------------------------

# ipv6 eigrp

## Syntax:

    ipv6 eigrp AS_NUMBER

## Example:

    R1(config-if)# ipv6 eigrp 100

## Description:

**Enables EIGRP for IPv6 on the interface. Advanced EIGRP
configuration is covered in the EIGRP volume.**

------------------------------------------------------------

# ipv6 router isis

## Syntax:

    ipv6 router isis TAG

## Example:

    R1(config-if)# ipv6 router isis CORE

## Description:

**Enables IPv6 routing through IS-IS on the interface.
Advanced IS-IS configuration is beyond the scope of this
volume.**

------------------------------------------------------------

## IPv6 Summary

IPv6 interface configuration enables modern Layer 3
connectivity using global, link-local, and automatically
generated addresses. Cisco IOS supports multiple IPv6
addressing methods, Neighbor Discovery Protocol (NDP), Router
Advertisements (RA), Stateless Address Autoconfiguration
(SLAAC), and integration with IPv6 routing protocols.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[README.md](README.md)**

➡️ Next: **[02_IPv6_Verification_Commands.md](02_IPv6_Verification_Commands.md)**
