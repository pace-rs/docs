# Command Reference

<!-- TOC -->

- [List of Commands](#list-of-commands)
- [Command Descriptions](#command-descriptions)
  - [adjust](#adjust)
  - [begin](#begin)
  - [end](#end)
  - [hold](#hold)
  - [now](#now)
  - [resume](#resume)
  - [review](#review)
  - [setup](#setup)
  - [docs](#docs)
  - [help](#help)
- [Options and Flags](#options-and-flags)
  - [Only available on `adjust`](#only-available-on-adjust)
  - [`adjust`, `begin`, `end`, `hold`, `resume`](#adjust-begin-end-hold-resume)
  - [Only available on `resume`](#only-available-on-resume)
  - [Only available on `review`](#only-available-on-review)
  - [Only available on `docs`](#only-available-on-docs)
- [Usage Syntax](#usage-syntax)
  - [`adjust`](#adjust-1)
  - [`begin`](#begin-1)
  - [`end`](#end-1)
  - [`hold`](#hold-1)
  - [`now`](#now-1)
  - [`resume`](#resume-1)
  - [`review`](#review-1)
  - [`setup`](#setup-1)
  - [`docs`](#docs-1)
  - [`help`](#help-1)

<!-- /TOC -->

## List of Commands

```console
Commands:
  adjust  📝 Adjust the details of an activity, such as its category, description, or tags [aliases: a]
  begin   ⌚ Starts tracking time for an activity [aliases: b]
  end     ⏹️ Stops time tracking for the most recent or all activities [aliases: e]
  hold    ⏸️ Pauses the time tracking for the most recent active activity [aliases: h]
  now     ⏲️ Shows you at a glance what you're currently tracking [aliases: n]
  resume  ⏯️ Resumes a previously paused activity, allowing you to continue where you left off [aliases: r]
  review  📈 Get sophisticated insights on your activities [aliases: rev]
  setup   🛠️ Set up a pace configuration, a new project, or generate shell completions [aliases: s]
  docs    📚 Open the online documentation for pace [aliases: d]
  help    Print this message or the help of the given subcommand(s)
```

## Command Descriptions

### adjust

Adjust the current activity's start time, description, category, or tags. This
is useful for correcting mistakes or adding more detail to your activities.

**Usage:**
`pace adjust --category <Category> --description <Description> --start <Start Time>`

### begin

Starts tracking time for the specified task. You can optionally specify a
category or project to help organize your tasks.

**Usage:** `pace begin "Design Work" --category "Freelance" --start 10:00`

### end

Stops time tracking for all tasks, marking them as completed or finished for the
day.

**Usage:** `pace end --end 11:30`

### hold

Pauses the time tracking for the specified task. This is useful for taking
breaks without ending the task.

**Usage:** `pace hold --reason <Reason>`

### now

Displays the currently running task, showing you at a glance what you're
currently tracking.

**Usage:** `pace now`

### resume

Resumes time tracking for a previously paused task, allowing you to continue
where you left off.

**Usage:** `pace resume` or `pace resume --list`

### review

Gain insight in your activities and tasks. You can specify the time frame for
daily, weekly, or monthly insights.

**Usage:** `pace review --last-week` or
`pace review --from 2024-02-10 --to 2024-03-06` or
`pace review --today -o json -e ./data/data.json`

### setup

Create configuration files for pace, including the main configuration file and
any additional settings. This is useful for setting up pace for the first time
or when you need to change your settings. You can also generate shell
completions for your shell of choice. And generate a project configuration file.

**Usage:** `pace setup config` or `pace setup completions`

### docs

Opens the documentations for users, developers, and the configuration file in
your default browser.

**Usage:** `pace docs` or `pace docs --dev` or `pace docs --config`

### help

Prints a help message or the help of the given subcommand(s).

**Usage:** `pace help` or `pace help begin` or `pace help adjust`

## Options and Flags

### Only available on `adjust`

- **--override-tags**: Overrides the current tags with the specified tags.

  **Usage:** `--override-tags "design,assets"` or
  `--override-tags "design,assets,client-x"`

- **--start**: Specifies the start time of the activity.

  **Usage:** `--start 10:00` or `--start 10:00:00`

### `adjust`, `begin`, `end`, `hold`, `resume`

- **--category**: Specifies the category of the activity.

  **Usage:** `--category "Freelance"` or `--category "Freelance::Design"`

- **--description**: Specifies the description of the activity.

  **Usage:** `--description "Design Work"` or
  `--description "Design Work for Client X"`

- **--at**: Specifies the start, end or resuming time of the activity.

  **Usage:** `--at 10:00` or `--at 10:00:00`

- **--tags**: Specifies the tags for the activity, they will be deduplicated.

  **Usage:** `--tags "design,assets"` or `--tags "design,assets,client-x"`

### Only available on `resume`

- **--reason**: Specifies the reason for holding the activity.

  **Usage:** `--reason "Lunch Break"` or `--reason "Meeting"`

- **--list**: Lists all activities that are resumable.

  **Usage:** `--list`

### Only available on `review`

```console
Options:
  -a, --activity-kind <Activity Kind>  Filter by activity kind (e.g., activity, task)
  -c, --category <Category>            Filter by category name, wildcard supported
      --case-sensitive                 Case sensitive category filter
  -o, --output-format <Output Format>  Specify output format (e.g., text, markdown, pdf) [possible values: console, json, html, csv, markdown, plain-text]
  -e, --export-file <Export File>      Export the review report to a specified file
  -h, --help                           Print help
  -V, --version                        Print version

Flags for specifying time periods:
      --today          Show the review for the current day
      --yesterday      Show the review for the previous day
      --current-week   Show the review for the current week
      --last-week      Show the review for the previous week
      --current-month  Show the review for the current month
      --last-month     Show the review for the previous month

Date flags for specifying custom date ranges or specific dates:
      --date <Specific Date>  Show the review for a specific date, mutually exclusive with `from` and `to`. Format: YYYY-MM-DD
      --from <Start Date>     Start date for the review period. Format: YYYY-MM-DD
      --to <End Date>         End date for the review period. Format: YYYY-MM-DD

Expensive flags for detailed insights:
      --detailed         Include detailed time logs in the review
      --comparative      Enable comparative insights against a previous period
      --recommendations  Enable personalized recommendations based on review data
```

### Only available on `docs`

- **--dev**: Opens the developer documentation.

  **Usage:** `--dev`

- **--config**: Opens the configuration documentation.

  **Usage:** `--config`

## Usage Syntax

### `adjust`

```console
Usage: pace adjust <--category <Category>|--description <Description>|--start <Start Time>|--tags <Tags>|--override-tags>
```

### `begin`

```console
Usage: pace begin [OPTIONS] <Activity Description>
```

### `end`

```console
Usage: pace end [OPTIONS]
```

### `hold`

```console
Usage: pace hold [OPTIONS]
```

### `now`

```console
Usage: pace now
```

### `resume`

```console
Usage: pace resume [OPTIONS]
```

### `review`

```console
pace review [OPTIONS]
```

### `setup`

```console
Usage: pace setup <config|completions|show>
```

### `docs`

```console
Usage: pace docs [--dev|--config]
```

### `help`

```console
Usage: pace help [COMMAND]
```
