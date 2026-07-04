# Interface Configuration Commands

---

**Volume:** 02 • Interface Configuration

**Estimated Reading Time:** 45 Minutes

---

## Contents

- [interface](#interface)
- [description](#description)
- [ip address](#ip-address)
- [ipv6 address](#ipv6-address)
- [shutdown](#shutdown)
- [no shutdown](#no-shutdown)
- [bandwidth](#bandwidth)
- [delay](#delay)
- [mtu](#mtu)
- [load-interval](#load-interval)
- [keepalive](#keepalive)
- [encapsulation](#encapsulation)
- [clock rate](#clock-rate)
- [media type](#media-type)
- [negotiation auto](#negotiation-auto)
- [speed](#speed)
- [duplex](#duplex)
- [no ip address](#no-ip-address)
- [default interface](#default-interface)

---

# interface

## Syntax

    interface GigabitEthernet0/0

## Example

    R1(config)# interface GigabitEthernet0/0

    R1(config-if)#

## Description

    Enters Interface Configuration mode for the selected
    interface. All interface-specific configuration commands
    are entered from this mode.

------------------------------------------------------------

# description

## Syntax

    description TEXT

## Example

    R1(config-if)# description Link to ISP

## Description

    Configures a descriptive label for the interface.
    Interface descriptions simplify administration and
    troubleshooting.

------------------------------------------------------------

# ip address

## Syntax

    ip address IP_ADDRESS SUBNET_MASK

## Example

    R1(config-if)# ip address 192.168.10.1 255.255.255.0

## Description

    Assigns an IPv4 address and subnet mask to the interface.

------------------------------------------------------------

# ipv6 address

## Syntax

    ipv6 address IPV6_ADDRESS/PREFIX

## Example

    R1(config-if)# ipv6 address 2001:DB8:1::1/64

## Description

    Assigns an IPv6 address to the interface using CIDR
    prefix notation.

------------------------------------------------------------

# shutdown

## Syntax

    shutdown

## Example

    R1(config-if)# shutdown

## Description

    Administratively disables the interface. Traffic is no
    longer forwarded until the interface is re-enabled.

------------------------------------------------------------

# no shutdown

## Syntax

    no shutdown

## Example

    R1(config-if)# no shutdown

## Description

    Administratively enables the interface, allowing it to
    transition to the operational state if all physical and
    protocol conditions are met.

------------------------------------------------------------

# bandwidth

## Syntax

    bandwidth KILOBITS

## Example

    R1(config-if)# bandwidth 100000

## Description

    Configures the interface bandwidth value in kilobits per
    second. This command does not change the physical speed of
    the interface but is used by routing protocols and QoS
    calculations.

------------------------------------------------------------

# delay

## Syntax

    delay TENS_OF_MICROSECONDS

## Example

    R1(config-if)# delay 100

## Description

    Configures the interface delay value used by routing
    protocols when calculating routing metrics.

------------------------------------------------------------

# mtu

## Syntax

    mtu BYTES

## Example

    R1(config-if)# mtu 1500

## Description

    Configures the Maximum Transmission Unit (MTU) for the
    interface. Packets larger than the configured MTU may be
    fragmented or dropped depending on the protocol.

------------------------------------------------------------

# load-interval

## Syntax

    load-interval SECONDS

## Example

    R1(config-if)# load-interval 30

## Description

    Specifies how often interface statistics are calculated
    and updated. Lower values provide more responsive traffic
    statistics.

------------------------------------------------------------

# keepalive

## Syntax

    keepalive SECONDS

## Example

    R1(config-if)# keepalive 10

## Description

    Configures the keepalive interval used to verify that the
    interface is operational. If keepalive messages are not
    received, the interface may be marked as down.

------------------------------------------------------------

# encapsulation

## Syntax

    encapsulation TYPE

## Example

    R1(config-if)# encapsulation ppp

## Description

    Configures the encapsulation method used on supported
    interfaces. Common encapsulation types include HDLC and
    PPP on serial links.

------------------------------------------------------------

# clock rate

## Syntax

    clock rate BITS_PER_SECOND

## Example

    R1(config-if)# clock rate 64000

## Description

    Sets the clock rate on the DCE end of a serial connection.
    This command is used only on serial interfaces that provide
    clocking.

------------------------------------------------------------

# media-type

## Syntax

    media-type TYPE

## Example

    R1(config-if)# media-type rj45

## Description

    Selects the media type used by the interface. This command
    is available only on supported hardware platforms.

------------------------------------------------------------

# negotiation auto

## Syntax

    negotiation auto

## Example

    R1(config-if)# negotiation auto

## Description

    Enables automatic negotiation of interface speed and
    duplex settings with the connected device.

------------------------------------------------------------

# speed

## Syntax

    speed VALUE

## Example

    R1(config-if)# speed 1000

## Description

    Configures the interface speed. The available values depend
    on the interface type and hardware capabilities.

------------------------------------------------------------

# duplex

## Syntax

    duplex {auto | full | half}

## Example

    R1(config-if)# duplex full

## Description

    Configures the duplex mode of the interface. Full duplex
    allows simultaneous transmission and reception, while half
    duplex permits only one direction at a time.

------------------------------------------------------------

# no ip address

## Syntax

    no ip address

## Example

    R1(config-if)# no ip address

## Description

    Removes the IPv4 address configured on the interface.

------------------------------------------------------------

# default interface

## Syntax

    default interface INTERFACE

## Example

    R1(config)# default interface GigabitEthernet0/0

## Description

    Restores the selected interface to its factory default
    configuration by removing all interface-specific settings.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[README.md](README.md)**

➡️ Next: **[02_Interface_Verification_Commands.md](02_Interface_Verification_Commands.md)**
