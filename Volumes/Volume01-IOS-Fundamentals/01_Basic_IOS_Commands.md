# Basic IOS Commands

Volume 01 • IOS Fundamentals

Estimated Reading Time

35 Minutes

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
- [enable password](#enable-password)
- [enable secret](#enable-secret)
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

Syntax:

enable

Example:

Router> enable

Router#

What it does:

Enters Privileged EXEC mode, allowing access to advanced monitoring, troubleshooting, and configuration commands.

------------------------------------------------------------

# disable

Syntax:

disable

Example:

Router# disable

Router>

What it does:

Returns from Privileged EXEC mode to User EXEC mode.

------------------------------------------------------------

# exit

Syntax:

exit

Example:

Router(config-if)# exit

Router(config)#

What it does:

Exits the current command mode and returns to the previous mode.

------------------------------------------------------------

# end

Syntax:

end

Example:

Router(config)# end

Router#

What it does:

Immediately exits all configuration modes and returns to Privileged EXEC mode.

------------------------------------------------------------

# logout

Syntax:

logout

Example:

Router> logout

Connection closed by foreign host.

What it does:

Terminates the current CLI session.

------------------------------------------------------------

# quit

Syntax:

quit

Example:

Router# quit

Connection closed by foreign host.

What it does:

Ends the current CLI session. On most Cisco IOS devices, it performs the same function as `logout`.

------------------------------------------------------------

# configure terminal

Syntax:

configure terminal

Example:

Router# configure terminal

Router(config)#

What it does:

Enters Global Configuration mode, where most device configuration tasks are performed.

------------------------------------------------------------

# hostname

Syntax:

hostname R1

Example:

Router(config)# hostname R1

R1(config)#

What it does:

Changes the device hostname. The new hostname immediately appears in the CLI prompt.

------------------------------------------------------------

# banner motd

Syntax:

banner motd #

Example:

Router(config)# banner motd #

Unauthorized access is prohibited.

#

What it does:

Configures the Message of the Day (MOTD) banner displayed before user authentication.

------------------------------------------------------------

# banner login

Syntax:

banner login #

Example:

Router(config)# banner login #

Authorized Personnel Only

#

What it does:

Displays a banner immediately before the login prompt appears.

------------------------------------------------------------

# enable password

Syntax:

enable password PASSWORD

Example:

Router(config)# enable password Cisco123

What it does:

Configures the legacy password for Privileged EXEC mode. This command is maintained for compatibility but is not recommended for secure environments.

------------------------------------------------------------

# enable secret

Syntax:

enable secret PASSWORD

Example:

Router(config)# enable secret Cisco123

What it does:

Configures the encrypted password for Privileged EXEC mode. If both `enable password` and `enable secret` exist, `enable secret` always takes precedence.

------------------------------------------------------------

# service password-encryption

Syntax:

service password-encryption

Example:

R1(config)# service password-encryption

What it does:

Encrypts all plain-text passwords stored in the running configuration using Cisco Type 7 encryption. It does not encrypt passwords protected by the `enable secret` command.

------------------------------------------------------------

# no ip domain-lookup

Syntax:

no ip domain-lookup

Example:

R1(config)# no ip domain-lookup

What it does:

Disables DNS lookups for mistyped commands. This prevents the router or switch from attempting to resolve unknown commands as hostnames, reducing unnecessary delays.

------------------------------------------------------------

# ip domain-name

Syntax:

ip domain-name DOMAIN_NAME

Example:

R1(config)# ip domain-name example.com

What it does:

Configures the device's default domain name. This command is commonly required before generating RSA keys for SSH.

------------------------------------------------------------

# username

Syntax:

username USERNAME secret PASSWORD

Example:

R1(config)# username admin secret Cisco123

What it does:

Creates a local user account for authentication. The `secret` keyword stores the password in encrypted form and is recommended over `password`.

------------------------------------------------------------

# password

Syntax:

password PASSWORD

Example:

R1(config-line)# password Cisco123

What it does:

Assigns a password to console, AUX, or VTY lines. This command is typically used together with the `login` command.

------------------------------------------------------------

# line console 0

Syntax:

line console 0

Example:

R1(config)# line console 0

R1(config-line)#

What it does:

Enters Console Line Configuration mode, allowing you to configure console authentication, timeouts, logging behavior, and other console settings.

------------------------------------------------------------

# line vty 0 4

Syntax:

line vty 0 4

Example:

R1(config)# line vty 0 4

R1(config-line)#

What it does:

Enters VTY Line Configuration mode to configure remote access settings such as Telnet, SSH, authentication, and access restrictions.

------------------------------------------------------------

# login

Syntax:

login

Example:

R1(config-line)# login

What it does:

Enables password checking on the selected line. A password must already be configured using the `password` command.

------------------------------------------------------------

# login local

Syntax:

login local

Example:

R1(config-line)# login local

What it does:

Uses the local username database for authentication instead of the line password. This is the recommended method for SSH access.

------------------------------------------------------------

# exec-timeout

Syntax:

exec-timeout MINUTES SECONDS

Example:

R1(config-line)# exec-timeout 10 0

What it does:

Automatically disconnects inactive CLI sessions after the specified period of inactivity.

------------------------------------------------------------

# logging synchronous

Syntax:

logging synchronous

Example:

R1(config-line)# logging synchronous

What it does:

Prevents system log messages from interrupting command-line input by redisplaying the prompt after log messages appear.

------------------------------------------------------------

# transport input

Syntax:

transport input {ssh | telnet | all | none}

Example:

R1(config-line)# transport input ssh

What it does:

Specifies which remote access protocols are permitted on VTY lines. For security reasons, SSH is generally preferred over Telnet.

------------------------------------------------------------

# do

Syntax:

do COMMAND

Example:

R1(config)# do show ip interface brief

What it does:

Executes a Privileged EXEC command without leaving Configuration mode, making verification faster and more convenient.

------------------------------------------------------------

# copy running-config startup-config

Syntax:

copy running-config startup-config

Example:

R1# copy running-config startup-config

Destination filename [startup-config]?

Building configuration...

[OK]

What it does:

Saves the current running configuration to NVRAM so it will be loaded after the device is restarted.

------------------------------------------------------------

# write memory

Syntax:

write memory

Example:

R1# write memory

Building configuration...

[OK]

What it does:

Saves the running configuration to startup configuration. This command is a shortcut equivalent to `copy running-config startup-config`.

------------------------------------------------------------

# erase startup-config

Syntax:

erase startup-config

Example:

R1# erase startup-config

Erasing the nvram filesystem will remove all configuration files!

Continue? [confirm]

What it does:

Deletes the startup configuration stored in NVRAM. The current running configuration remains active until the device is reloaded.

------------------------------------------------------------

# reload

Syntax:

reload

Example:

R1# reload

Proceed with reload? [confirm]

What it does:

Restarts the Cisco device. If the running configuration has not been saved, any unsaved changes will be lost after the reload.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[README.md](README.md)**

➡️ Next: **[02_Verification_Commands.md](02_Verification_Commands.md)**
