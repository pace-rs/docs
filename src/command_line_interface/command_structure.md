# Command Structure

<!-- TOC -->

1. [Command Syntax](#command-syntax)
1. [Subcommands](#subcommands)
1. [Options and Flags](#options-and-flags)
1. [Argument Formats](#argument-formats)

<!-- /TOC -->

## Command Syntax

The Pace CLI uses a simple and intuitive syntax for executing commands. The
basic structure of a command is as follows:

```console
pace [GLOBAL_OPTIONS] <COMMAND> [OPTIONS] [ARGUMENTS]
```

- `<COMMAND>`: The primary action or task to be performed, such as `begin`,
  `end`, `hold`, `resume` or `review`.

- `[GLOBAL_OPTIONS]`/`[OPTIONS]`: Optional flags or settings that modify the
  behavior of the command. Options are typically preceded by a hyphen (`-`) or
  double hyphen (`--`).

- `[ARGUMENTS]`: Additional information or data required to complete the
  command, such as activity descriptions, time ranges, or category names.

## Subcommands

The Pace CLI organizes its functionality into subcommands, each serving a
specific purpose or task. For example, the `begin` command is used to start
tracking time for an activity, while the `review` command provides insights on
your activities.

For a complete list of available commands, you can run:

```console
pace help
```

## Options and Flags

Options and flags are used to modify the behavior of commands or provide
additional information. They are typically specified using a hyphen (`-`) or
double hyphen (`--`) followed by a keyword or abbreviation.

For example, the `--category/-c` option can be used to specify the category of
an activity, while the `--tags/-t` option can be used to add tags to an
activity.

You can view the available options and flags for each command by running:

```console
pace help <COMMAND>

# or within the command itself using the --help flag
pace <COMMAND> --help
```

## Argument Formats

Arguments are additional pieces of information or data required to complete a
command. They can take various formats, such as:

- **Activity descriptions**: Text that describes the activity being logged. For
  example, `"Writing blog post"` or `"Debugging code"`. Descriptions are
  mandatory for the `begin` command. For other commands, they are optional and
  can be specified using the `--description/-d` option.

- **Time**: A start or end time for an activity. For example, `"9:00"` or
  `"24:00"`. Where applicable, time can be specified using the `--at/-a` option.

- **Category names**: The name of a category to which an activity belongs. For
  example, `"Development"` or `"Writing"`. Where applicable, category names can
  be specified using the `--category/-c` option.

- **Tags**: Keywords or labels that provide additional context for an activity.
  For example, `"important"` or `"urgent"`. Where applicable, tags can be
  specified using the `--tags/-t` option. They can be specified as a
  comma-separated list, such as `"important,urgent"`.
