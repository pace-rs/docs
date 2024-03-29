# Usage Examples

<!-- TOC -->

- [Basic Usage - The Pace Workflow](#basic-usage---the-pace-workflow)
  - [Principle "Do one thing and do it good."](#principle-do-one-thing-and-do-it-good)
  - [Starting an Activity](#starting-an-activity)
    - [Switching Activities](#switching-activities)
  - [Ending an Activity](#ending-an-activity)
  - [Pausing an Activity](#pausing-an-activity)
  - [Showing the Current Activity](#showing-the-current-activity)
  - [Gain Insights with Summaries](#gain-insights-with-summaries)
- [Advanced Functionality](#advanced-functionality)
  - [Listing Activities](#listing-activities)
    - [Listing resumable activities](#listing-resumable-activities)
  - [Adjusting Activities](#adjusting-activities)

<!-- /TOC -->

<!-- TODO: **Command Combinations**: Illustrate how multiple commands can be combined to achieve specific tasks or workflows, showcasing the flexibility and power of the Pace CLI. -->

## Basic Usage - The Pace Workflow

### Principle "Do one thing and do it good."

Pace is designed to support this principle. It will allow only one active
activity at a time. This means you can only start, pause, resume, or end one
activity at a time. This is to ensure that the time tracking is as accurate as
possible and you can actually focus on the task at hand. That's why Pace will
automatically end the current activity when you start a new one. pace is called
a mindful time tracking tool for that reason.

With pace you can easily manage your day. Here's how to start, pause, and
conclude your activities, alongside generating insightful summaries.

### Starting an Activity

Kick off any task with ease. Simply begin your activity now:

```shell
pace begin "Creating new assets" --category "MyProject::MyAreaOfFocus" --tags "design,assets"
```

**Note**: If you don't specify a category or tags, Pace will use reasonable
defaults. Which is no tags and the 'Uncategorized' category. You can also
specify a starting time with the `--at` flag, your time should be in the format
`HH:MM`. If you don't specify a time, pace will use the current time. Using a
different starting time than the current time is useful if you forgot to start
the activity at the right time, but you want to make sure the time is logged
correctly. You cannot start an activity with a starting time in the future.

#### Switching Activities

Move seamlessly to a new task. Pace automatically concludes the previous one:

```shell
pace begin "Reviewing PR #43" --category "MyOtherProject::MyOtherAreaOfFocus" --tags "web,design"
```

### Ending an Activity

Wrap up your current task:

```shell
pace end
```

**Note**: When ending an activity, you can also specify the ending time with the
`--at` flag, your time should be in the format `HH:MM`. If you don't specify a
time, Pace will use the current time. Using a different ending time than the
current time is useful if you forgot to end the activity at the right time, but
you want to make sure the time is logged correctly. You cannot end an activity
with an ending time in the future.

### Pausing an Activity

Need a break or a shift in focus? Pause your current activity:

```shell
pace hold
```

And resume it when you're ready:

```shell
pace resume
```

**Note**: When resuming an activity, you can also specify the resuming time with
the `--at` flag, your time should be in the format `HH:MM`. If you don't specify
a time, Pace will use the current time. Using a different resuming time than the
current time is useful if you forgot to resume the activity at the right time,
but you want to make sure the time is logged correctly. You cannot resume an
activity with a resume time in the future.

### Showing the Current Activity

You can show the current activity with the `pace now` command. This will show
you the current activity, if there is one.

### Gain Insights with Summaries

You can generate summaries of your activities with the `pace reflect` command.
It will show you a summary of your activities for the current day, week, or
month. You can also specify a custom date range to reflect. If you want to see a
summary of your activities for the current day, you can just run:

```shell
pace reflect
```

It defaults to the current day. If you want to see a summary of your activities
for the current week, you can run:

```shell
pace reflect --current-week
```

If you want to see a summary of your activities for a specific date, you can
run:

```shell
pace reflect --date "2021-12-31"
```

While you can also specify a date range to reflect upon:

```shell
pace reflect --from "2021-12-01" --to "2021-12-23"
```

If you only specify the `--from` flag, pace will show you a summary of your
activities from the specified date to the current date. If you only specify the
`--to` flag, pace will show you a summary of your activities from the beginning
of the month to the specified date.

## Advanced Functionality

### Listing Activities

#### Listing resumable activities

You can list all activities that are resumable with the `pace resume --list`
command. This will show you all activities that are ended but which you can
resume by creating a new activity with the same contents. Resuming an activity
will automatically end all the other and the currently active activities.

**Note**: In case `pace resume` cannot find any active activity, it will list
the last `X` activities that are ended and which you can resume by creating a
new activity with the same contents. You can specify the number of activities to
list by setting:

```toml
[general]
most_recent_count = 12 # Default: 9
```

### Adjusting Activities

Need to correct a mistake? You can adjust the contents of the currently active
activity:

```shell
pace adjust --category "MyProject::MyAreaOfFocus" --tags "design,assets" --description "Creating new assets" --start "08:00"
```

**Note**: When adjusting an activity, you can also specify the starting time
with the `--start` flag, your time should be in the format `HH:MM`. If you don't
specify a time, the time will not be changed. Using a different starting time
than the current time is useful if you forgot to start the activity at the right
time, but you want to make sure the time is logged correctly.

### Setting the Time Zone

You can specify a custom time zone or time zone offset when logging an activity
using the `--time-zone` or `--time-zone-offset` flags. This is useful when you
want to track activities in a different time zone or when your system time zone
differs from the time zone you want to use for tracking.

The time zone should be in the format `Region/City`, for example,
`America/New_York` or `Europe/Berlin`. The time zone offset should be in the
format `±HHMM`, for example, `+0530` or `-0800`. The default time zone is the
system time zone. You can use the `pace settings set time-zone` command to set
the default time zone. Or re-run `pace setup config` to set the default time
zone during the initial setup.
