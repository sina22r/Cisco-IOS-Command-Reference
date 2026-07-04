# Basic IOS Commands

---

**Volume:** 01 • IOS Fundamentals

**Estimated Reading Time:** 35 Minutes

---

## Contents

- [enable](#enable)
- [disable](#disable)
- [exit](#exit)
- [end](#end)
- [logout](#logout)
- [quit](#quit)
- [configure terminal](#configure-terminal)
- [hostname](#hostname)
- [banner motd](#banner-motd)
- [banner login](#banner-login)
- [enable secret](#enable-secret)
- [enable password](#enable-password)
- [service password-encryption](#service-password-encryption)
- [no ip domain-lookup](#no-ip-domain-lookup)
- [ip domain-name](#ip-domain-name)
- [username](#username)
- [password](#password)
- [line console 0](#line-console-0)
- [line vty 0 4](#line-vty-0-4)
- [login](#login)
- [login local](#login-local)
- [exec-timeout](#exec-timeout)
- [logging synchronous](#logging-synchronous)
- [transport input](#transport-input)
- [do](#do)
- [copy running-config startup-config](#copy-running-config-startup-config)
- [write memory](#write-memory)
- [erase startup-config](#erase-startup-config)
- [reload](#reload)

---

# enable

## Syntax

    enable

## Example

    Router> enable

    Router#

## Description

    Enters Privileged EXEC mode, providing access to configuration,
    monitoring, debugging, and administrative commands.

------------------------------------------------------------

# disable

## Syntax

    disable

## Example

    Router# disable

    Router>

## Description

    Returns from Privileged EXEC mode to User EXEC mode.

------------------------------------------------------------

# exit

## Syntax

    exit

## Example

    Router(config-if)# exit

    Router(config)#

## Description

    Exits the current command mode and returns to the previous mode.

------------------------------------------------------------

# end

## Syntax

    end

## Example

    Router(config)# end

    Router#

## Description

    Immediately exits all configuration modes and returns to
    Privileged EXEC mode.

------------------------------------------------------------

# logout

## Syntax

    logout

## Example

    Router> logout

    Connection closed by foreign host.

## Description

    Terminates the current CLI session.

------------------------------------------------------------

# quit

## Syntax

    quit

## Example

    Router# quit

    Connection closed by foreign host.

## Description

    Terminates the current CLI session. On most Cisco IOS platforms,
    this command behaves the same as the logout command.

------------------------------------------------------------

# configure terminal

## Syntax

    configure terminal

## Example

    Router# configure terminal

    Router(config)#

## Description

    Enters Global Configuration mode, where most device
    configuration tasks are performed.

------------------------------------------------------------

# hostname

## Syntax

    hostname HOSTNAME

## Example

    Router(config)# hostname R1

    R1(config)#

## Description

    Changes the hostname of the Cisco device. The new hostname
    immediately appears in the CLI prompt.

------------------------------------------------------------

# banner motd

## Syntax

    banner motd DELIMITER

## Example

    R1(config)# banner motd #

    ********************************************
    * Unauthorized access is strictly prohibited *
    ********************************************

    #

## Description

    Configures the Message of the Day (MOTD) banner displayed
    before user authentication. This banner is commonly used to
    display legal notices or security warnings.

------------------------------------------------------------

# banner login

## Syntax

    banner login DELIMITER

## Example

    R1(config)# banner login #

    Authorized Personnel Only

    #

## Description

    Displays a banner immediately before the login prompt appears.
    It is commonly used to provide security and access notices.

------------------------------------------------------------

# enable secret

## Syntax

    enable secret PASSWORD

## Example

    R1(config)# enable secret Cisco123

## Description

    Configures an encrypted password for Privileged EXEC mode.
    This is the recommended method for protecting privileged
    access. If both enable password and enable secret are
    configured, enable secret always takes precedence.

------------------------------------------------------------

# enable password

## Syntax

    enable password PASSWORD

## Example

    R1(config)# enable password Cisco123

## Description

    Configures the legacy password for Privileged EXEC mode.
    This command exists for backward compatibility and should
    not be used in modern secure deployments.

------------------------------------------------------------

# service password-encryption

## Syntax

    service password-encryption

## Example

    R1(config)# service password-encryption

## Description

    Encrypts all plain-text passwords stored in the configuration
    using Cisco Type 7 encryption. This feature helps prevent
    casual password exposure but should not be considered a
    strong security mechanism.

------------------------------------------------------------

# no ip domain-lookup

## Syntax

    no ip domain-lookup

## Example

    R1(config)# no ip domain-lookup

## Description

    Disables DNS lookups for mistyped commands. Without this
    command, Cisco IOS attempts to resolve unknown commands
    as hostnames, which can introduce unnecessary delays.

------------------------------------------------------------

# ip domain-name

## Syntax

    ip domain-name DOMAIN_NAME

## Example

    R1(config)# ip domain-name example.com

## Description

    Configures the default domain name of the device. This
    command is required before generating RSA keys for SSH.

------------------------------------------------------------

# username

## Syntax

    username USERNAME secret PASSWORD

## Example

    R1(config)# username admin secret Cisco123

## Description

    Creates a local user account for authentication. Using the
    secret keyword stores the password in encrypted form and
    is recommended over the password keyword.

------------------------------------------------------------

# password

## Syntax

    password PASSWORD

## Example

    R1(config-line)# password Cisco123

## Description

    Assigns a password to the current console, AUX, or VTY
    line. This command is typically used together with the
    login command.

------------------------------------------------------------

# line console 0

## Syntax

    line console 0

## Example

    R1(config)# line console 0

    R1(config-line)#

## Description

    Enters Console Line Configuration mode, where console
    authentication, session timeout, logging behavior, and
    other console parameters can be configured.

------------------------------------------------------------

# line vty 0 4

## Syntax

    line vty 0 4

## Example

    R1(config)# line vty 0 4

    R1(config-line)#

## Description

    Enters VTY Line Configuration mode for configuring remote
    access methods such as SSH and Telnet, authentication,
    and access restrictions.

------------------------------------------------------------

# login

## Syntax

    login

## Example

    R1(config-line)# login

## Description

    Enables password authentication on the selected line. A
    password must already be configured using the password
    command.

------------------------------------------------------------

# login local

## Syntax

    login local

## Example

    R1(config-line)# login local

## Description

    Configures the selected line to authenticate users against
    the local username database instead of using the line
    password. This is the recommended authentication method
    for SSH access.

------------------------------------------------------------

# exec-timeout

## Syntax

    exec-timeout MINUTES SECONDS

## Example

    R1(config-line)# exec-timeout 10 0

## Description

    Automatically terminates inactive EXEC sessions after the
    specified period of inactivity, improving device security.

------------------------------------------------------------

# logging synchronous

## Syntax

    logging synchronous

## Example

    R1(config-line)# logging synchronous

## Description

    Prevents system log messages from interrupting command-line
    input by redisplaying the CLI prompt after each message.

------------------------------------------------------------

# transport input

## Syntax

    transport input {ssh | telnet | all | none}

## Example

    R1(config-line)# transport input ssh

## Description

    Specifies which remote access protocols are permitted on
    VTY lines. SSH is recommended because it provides encrypted
    communication.

------------------------------------------------------------

# do

## Syntax

    do COMMAND

## Example

    R1(config)# do show ip interface brief

## Description

    Executes a Privileged EXEC command without leaving
    Configuration mode.

------------------------------------------------------------

# copy running-config startup-config

## Syntax

    copy running-config startup-config

## Example

    R1# copy running-config startup-config

    Destination filename [startup-config]?

    Building configuration...

    [OK]

## Description

    Saves the running configuration to NVRAM as the startup
    configuration. The saved configuration is loaded the next
    time the device boots.

------------------------------------------------------------

# write memory

## Syntax

    write memory

## Example

    R1# write memory

    Building configuration...

    [OK]

## Description

    Saves the running configuration to startup configuration.
    This command is functionally equivalent to the
    copy running-config startup-config command.

------------------------------------------------------------

# erase startup-config

## Syntax

    erase startup-config

## Example

    R1# erase startup-config

    Erasing the nvram filesystem will remove all configuration files!

    Continue? [confirm]

## Description

    Deletes the startup configuration stored in NVRAM. The
    running configuration remains active until the device is
    reloaded.

------------------------------------------------------------

# reload

## Syntax

    reload

## Example

    R1# reload

    Proceed with reload? [confirm]

## Description

    Restarts the Cisco device. Any unsaved configuration
    changes will be lost unless they are saved before the
    reload operation.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[README.md](README.md)**

➡️ Next: **[02_Verification_Commands.md](02_Verification_Commands.md)**
