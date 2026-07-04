# Terminal Commands

---

**Volume:** 01 • IOS Fundamentals

**Estimated Reading Time:** 20 Minutes

---

## Contents

- [terminal length](#terminal-length)
- [terminal width](#terminal-width)
- [terminal history size](#terminal-history-size)
- [terminal monitor](#terminal-monitor)
- [no terminal monitor](#no-terminal-monitor)
- [show terminal](#show-terminal)
- [terminal no editing](#terminal-no-editing)
- [terminal editing](#terminal-editing)
- [terminal exec prompt timestamp](#terminal-exec-prompt-timestamp)
- [terminal datadump](#terminal-datadump)

---

# terminal length

## Syntax

    terminal length NUMBER

## Example

    R1# terminal length 0

## Description

    Sets the number of output lines displayed before the CLI
    pauses. A value of 0 disables pagination completely.

------------------------------------------------------------

# terminal width

## Syntax

    terminal width NUMBER

## Example

    R1# terminal width 132

## Description

    Sets the width of the terminal display in characters.
    This command is useful when viewing long command output.

------------------------------------------------------------

# terminal history size

## Syntax

    terminal history size NUMBER

## Example

    R1# terminal history size 100

## Description

    Configures the number of commands stored in the command
    history buffer for the current terminal session.

------------------------------------------------------------

# terminal monitor

## Syntax

    terminal monitor

## Example

    R1# terminal monitor

## Description

    Enables the display of log messages on the current
    Telnet or SSH session.

------------------------------------------------------------

# no terminal monitor

## Syntax

    no terminal monitor

## Example

    R1# no terminal monitor

## Description

    Disables the display of system log messages on the
    current remote terminal session.

------------------------------------------------------------

# show terminal

## Syntax

    show terminal

## Example

    R1# show terminal

## Description

    Displays the current terminal settings, including
    terminal length, width, history size, and editing
    options.

------------------------------------------------------------

# terminal no editing

## Syntax

    terminal no editing

## Example

    R1# terminal no editing

## Description

    Disables command-line editing features for the current
    terminal session. Cursor movement and line editing keys
    are no longer available.

------------------------------------------------------------

# terminal editing

## Syntax

    terminal editing

## Example

    R1# terminal editing

## Description

    Enables command-line editing features for the current
    terminal session. This is the default behavior on
    Cisco IOS devices.

------------------------------------------------------------

# terminal exec prompt timestamp

## Syntax

    terminal exec prompt timestamp

## Example

    R1# terminal exec prompt timestamp

## Description

    Displays a timestamp with the EXEC prompt for the
    current terminal session. Availability depends on
    the Cisco IOS platform and software version.

------------------------------------------------------------

# terminal datadump

## Syntax

    terminal datadump

## Example

    R1# terminal datadump

## Description

    Disables paging and terminal formatting for the current
    session, allowing command output to be displayed without
    interruption. This command is useful when capturing CLI
    output or exporting logs.

------------------------------------------------------------

## Navigation

⬆️ [Back to Contents](#contents)

⬅️ Previous: **[02_Verification_Commands.md](02_Verification_Commands.md)**

➡️ Next: **[04_Labs.md](04_Labs.md)**
