# Configuration

The configuration file is a TOML file that is used to set up the pace CLI. The
configuration file is used to set up the location of the activity file, the
storage kind, the category separator, the default priority, and the most recent
count, among other settings.

## Specification of the Configuration File

A full list of settings and their default values can be found in the
[Pace Configuration Specification](https://github.com/pace-rs/pace/blob/main/config/README.md).

## Guided Setup Process

You can use the `pace setup config` command to create a configuration file. This
command will open an interactive setup process that will ask you a few questions
about where to store your data and how to store it. Once you've answered all the
questions, pace will create a configuration and an activity log file for you.

### Manually Setting up the Configuration File

The configuration file is a TOML file. This means it's a text file that contains
key-value pairs. You can use this file to adjust the settings of pace to your
liking. Here's an example of a configuration file:

```toml
[general]
path = "C:\\Users\\YourName\\pace\\activities.pace.toml"
storage-kind = "file"
category-separator = "::"
default-priority = "medium"
most-recent-count = 12
```

If you want to use a different location for the config file, you can specify the
location with the `--config` flag. For example:

```shell
pace --config "C:\\Users\\YourName\\pace\\config.toml" begin "Creating new assets" --category "MyProject::MyAreaOfFocus" --tags "design,assets"
```

### Showing Settings

You can show the current settings with the `pace setup show` command. This will
show you the currently loaded settings and the location of the activity file.

<!-- TODO:
### Opening The Configuration File

You can open the configuration file with the following command:

```shell
pace setup compose
```

This will open the configuration file in your default text editor. You can use
this file to adjust the settings of pace to your liking.
-->
