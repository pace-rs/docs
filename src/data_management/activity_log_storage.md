# Activity Log Storage

The activity log is the central data structure in pace. It is a record of all
activities, intermissions, and tasks that you have tracked. This document
describes how pace stores and manages activity logs.

## Storage Format

When using `pace` offline the activity log is stored in a file in the TOML
format. The file is named `activities.pace.toml` and is located in the pace data
directory. The pace data directory is platform-specific and is typically located
in the user's home directory. The file is a list of activity log entries, each
of which is a TOML table.

Here is an example of an activity log entry with an activity and an
intermission:

```toml
[01HQR3QRXEYK51T6N0D85G5668]
description = "My Task"
begin = "2024-02-28T16:01:13+01:00"
end = "2024-02-28T16:02:40+01:00"
duration = 87
kind = "activity"
tags = ["test", "my", "lawn"]
status = "ended"

[01HQR3RTH6XJKMW4PFD2XFNK71]
description = "My Task"
begin = "2024-02-28T16:01:48+01:00"
end = "2024-02-28T16:02:17+01:00"
duration = 29
kind = "intermission"
parent-id = "01HQR3QRXEYK51T6N0D85G5668"
status = "ended"
```

The activity log entry is identified by a unique identifier. The identifier is a
ULID (Universally Unique Lexicographically Sortable Identifier). The ULID is
used to uniquely identify the activity log entry and to establish relationships
between activity log entries.

## Storage Location

The pace data directory is platform-specific and is typically located in the
user's home directory. The pace data directory is used to store the activity log
and other pace data. The pace data directory is determined by the following
rules:

- On Linux, the pace data directory is `$XDG_DATA_HOME/pace` or
  `$HOME/.local/share/pace`.
- On Windows, the pace data directory is `{FOLDERID_LocalAppData}/pace`.
- On MacOS, the pace data directory is
  `$HOME/Library/Application Support/org.pace-rs.pace`.

The pace data directory is used to store the activity log and other pace data.
The activity log is stored in the file `activities.pace.toml` in the pace data
directory.

Pace also uses a configuration directory to store configuration files. The
configuration directory is platform-specific and is typically located in the
user's home directory. The configuration directory is determined by the
following rules:

- On Linux, the configuration directory is `$XDG_CONFIG_HOME/pace` or
  `$HOME/.config/pace/pace.toml`.
- On Windows, the configuration directory is
  `{FOLDERID_RoamingAppData}/pace/config/pace.toml`.
- On MacOS, the configuration directory is
  `$HOME/Library/Application Support/org.pace-rs.pace/config/pace.toml`.

The configuration directory is used to store configuration files. The
configuration file is named `pace.toml` and is located in the configuration
directory.

### PACE_HOME

You can override the pace data directory and the configuration directory by
setting the `PACE_HOME` environment variable. The `PACE_HOME` environment
variable is used to override the default pace data directory and the
configuration directory.
