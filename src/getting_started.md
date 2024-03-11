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

## Opening The Documentation

You can open the use documentation website with the following command. This will
open the documentation in your default web browser.

```shell
pace docs
```

If you want to open the developer documentation, you can use the following
command:

```shell
pace docs --dev
```

The documentation for the configuration file can be opened with the following
command:

```shell
pace docs --config
```

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
sections, we'll go over the basic workflow of pace. This will show you how to
start, pause, and conclude your activities, alongside generating insightful
summaries.
