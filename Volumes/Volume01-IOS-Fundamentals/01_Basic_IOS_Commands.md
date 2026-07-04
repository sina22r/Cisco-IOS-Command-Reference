# Basic IOS Commands

Volume 01 • IOS Fundamentals

---

## Contents

- enable
- disable
- exit
- end
- logout
- quit
- configure terminal
- hostname
- banner motd
- banner login
- enable password
- enable secret
- service password-encryption
- no ip domain-lookup
- ip domain-name
- username
- password
- line console 0
- line vty 0 4
- login
- login local
- exec-timeout
- logging synchronous
- transport input
- do
- copy running-config startup-config
- write memory
- erase startup-config
- reload

---

# enable

Syntax

enable

Example

Router> enable

Router#

What it does

Enters Privileged EXEC mode, allowing access to monitoring, debugging, and configuration commands.

------------------------------------------------------------

# disable

Syntax

disable

Example

Router# disable

Router>

What it does

Returns from Privileged EXEC mode to User EXEC mode.

------------------------------------------------------------

# exit

Syntax

exit

Example

Router(config-if)# exit

Router(config)#

What it does

Exits the current configuration mode and returns to the previous mode.

------------------------------------------------------------

# end

Syntax

end

Example

Router(config)# end

Router#

What it does

Immediately exits Configuration mode and returns to Privileged EXEC mode.

------------------------------------------------------------

# logout

Syntax

logout

Example

Router> logout

Connection closed.

What it does

Terminates the current CLI session.

------------------------------------------------------------

# quit

Syntax

quit

Example

Router# quit

Connection closed.

What it does

Ends the current CLI session. On most Cisco IOS platforms, it behaves the same as the `logout` command.

------------------------------------------------------------

# configure terminal

Syntax

configure terminal

Example

Router# configure terminal

Router(config)#

What it does

Enters Global Configuration mode, where most device configuration tasks are performed.

------------------------------------------------------------

# hostname

Syntax

hostname R1

Example

Router(config)# hostname R1

R1(config)#

What it does

Changes the device hostname. The new hostname is immediately reflected in the CLI prompt.

------------------------------------------------------------

# banner motd

Syntax

banner motd #

Example

Router(config)# banner motd #

Unauthorized access is prohibited.

#

What it does

Configures the Message of the Day (MOTD) banner, which is displayed before user authentication.

------------------------------------------------------------

# banner login

Syntax

banner login #

Example

Router(config)# banner login #

Authorized Personnel Only

#

What it does

Displays a banner after a connection is established but before the login prompt appears.

------------------------------------------------------------

# enable password

Syntax

enable password PASSWORD

Example

Router(config)# enable password Cisco123

What it does

Configures a password for entering Privileged EXEC mode. This command is considered legacy and is not recommended for secure deployments.

------------------------------------------------------------

# enable secret

Syntax

enable secret PASSWORD

Example

Router(config)# enable secret Cisco123

What it does

Configures an encrypted password for Privileged EXEC mode. If both `enable password` and `enable secret` are configured, `enable secret` takes precedence.

------------------------------------------------------------

End of File

← Previous

README.md

Next →

Continue with the remaining Basic IOS commands
