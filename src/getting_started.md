# Getting started

## Installation

Please refer to the [installation guide](./installation.md) for instructions on
how to install pace.

## Quickstart

Pace is a command-line tool, this means it runs in your terminal. To get
started, open your terminal. Depending on your operating system, you can use the
following commands to open your terminal:

- **Windows**: Press `Win + R`, type `cmd` and press `Enter`.
- **MacOS**: Press `Cmd + Space`, type `terminal` and press `Enter`.
- **Linux**: Press `Ctrl + Alt + T`.

Once you have your terminal open, you can run the following command to check if
pace is installed:

```shell
pace --version
```

If you see a version number, you're good to go! If not, please refer to the
[installation guide](./installation.md) for instructions on how to install pace.
Or ask for help in our [Discord Chat](./FAQ.md#getting-help).

## Setting up Pace

Before you can start tracking your time, you need to set up pace. This means
telling pace where to store your time tracking data. You can do this by running
the following command:

```shell
pace setup config
```

This will open an interactive setup process. You will be asked a few questions
about where to store your data and how to store it. Once you've answered all the
questions, pace will create a configuration and an activity log file for you.

## Tracking Time

Now that you have pace set up, you can start tracking your time. In the next
section, we'll go over the basic workflow of pace. This will show you how to
start, pause, and conclude your activities, alongside generating insightful
summaries.

## The Pace Workflow

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
correctly.

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
you want to make sure the time is logged correctly.

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
but you want to make sure the time is logged correctly.

### Showing the Current Activity

You can show the current activity with the `pace now` command. This will show
you the current activity, if there is one.

## Advanced Usage

### Listing Activities

#### Listing resumable activities

You can list all activities that are resumable with the `pace resume --list`
command. This will show you all activities that are ended but which you can
resume by creating a new activity with the same contents. Resuming an activity
will automatically end all the other and the currently active activities.

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

### Showing Settings

You can show the current settings with the `pace setup show` command. This will
show you the current settings and the location of the configuration file.
