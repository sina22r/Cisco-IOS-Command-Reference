# IOS Fundamentals Labs

---

**Volume:** 01 • IOS Fundamentals

**Estimated Reading Time:** 30 Minutes

---

## Contents

- [Lab 01 - Basic Device Configuration](#lab-01---basic-device-configuration)
- [Lab 02 - Secure Console Access](#lab-02---secure-console-access)
- [Lab 03 - Configure Remote Access](#lab-03---configure-remote-access)
- [Lab 04 - Save and Restore Configuration](#lab-04---save-and-restore-configuration)

---

# Lab 01 - Basic Device Configuration

## Objective

Configure the basic settings of a Cisco router, including the
hostname, MOTD banner, and privileged EXEC password.

## Topology

    PC -------- R1

## Tasks

1. Change the hostname to **R1**.
2. Configure an MOTD banner.
3. Configure an enable secret password.
4. Disable DNS lookups.
5. Save the configuration.

## Configuration

    Router> enable

    Router# configure terminal

    Router(config)# hostname R1

    R1(config)# banner motd #

    Authorized Access Only

    #

    R1(config)# enable secret Cisco123

    R1(config)# no ip domain-lookup

    R1(config)# end

    R1# copy running-config startup-config

## Verification

    R1# show running-config

    R1# show startup-config

## Expected Result

The hostname changes to **R1**, the MOTD banner is displayed,
DNS lookup is disabled, and the configuration is successfully
saved to NVRAM.

------------------------------------------------------------

# Lab 02 - Secure Console Access

## Objective

Protect console access with a password and configure
automatic session timeout.

## Topology

    PC -------- R1

## Tasks

1. Configure the console password.
2. Enable console login.
3. Configure an EXEC timeout of 10 minutes.
4. Enable synchronous logging.

## Configuration

    R1(config)# line console 0

    R1(config-line)# password Cisco123

    R1(config-line)# login

    R1(config-line)# exec-timeout 10 0

    R1(config-line)# logging synchronous

## Verification

    R1# show running-config

## Expected Result

Console access requires a password, idle sessions expire
after ten minutes, and system log messages no longer interrupt
command entry.

------------------------------------------------------------

# Lab 03 - Configure Remote Access

## Objective

Configure secure remote access using the local user database
and SSH.

## Topology

    PC -------- R1

## Tasks

1. Configure a domain name.
2. Create a local administrator account.
3. Generate RSA keys.
4. Configure the VTY lines.
5. Allow SSH connections only.
6. Save the configuration.

## Configuration

    R1(config)# ip domain-name example.com

    R1(config)# username admin secret Cisco123

    R1(config)# crypto key generate rsa modulus 2048

    R1(config)# line vty 0 4

    R1(config-line)# login local

    R1(config-line)# transport input ssh

    R1(config-line)# end

    R1# copy running-config startup-config

## Verification

    R1# show running-config

    R1# show ip ssh

## Expected Result

Remote management is available using SSH only. Users are
authenticated through the local user database, and Telnet
access is disabled.

------------------------------------------------------------

# Lab 04 - Save and Restore Configuration

## Objective

Practice saving, erasing, and restoring device
configurations.

## Topology

    PC -------- R1

## Tasks

1. Display the running configuration.
2. Save the configuration.
3. Verify the startup configuration.
4. Erase the startup configuration.
5. Reload the router.
6. Observe the boot process.

## Configuration

    R1# show running-config

    R1# copy running-config startup-config

    R1# show startup-config

    R1# erase startup-config

    R1# reload

## Verification

    R1# show startup-config

## Expected Result

The startup configuration is removed from NVRAM. After the
device reloads, the router starts with the initial
configuration dialog because no startup configuration exists.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[03_Terminal_Commands.md](03_Terminal_Commands.md)**

➡️ Next: **[05_CheatSheet.md](05_CheatSheet.md)**
