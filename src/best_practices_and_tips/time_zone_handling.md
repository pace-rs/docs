# Time Zone Handling

Time zones play a crucial role in time tracking applications, as they determine
how time is displayed, calculated, and stored. Understanding how time zones work
and how they affect your data is essential for accurate time tracking and
reporting.

## Overview

A time zone is a region of the globe that observes a uniform standard time for
legal, commercial, and social purposes. Time zones are based on the concept of
Coordinated Universal Time (UTC), which is the primary time standard by which
the world regulates clocks and time.

A time zone typically consists of a set of rules that define how the local time
of a region is related to UTC. These rules include the offset from UTC, daylight
saving time (DST) adjustments, and historical changes in timekeeping practices.

A global map of time zones is divided into regions, each of which has its own
standard time offset from UTC. For example, New York (Eastern Standard Time) is
UTC-5, while London (Greenwich Mean Time) is UTC+0.

You can see a list of time zones and their offsets on the
[IANA Time Zone Database](https://www.iana.org/time-zones). There is also a
[map of time zones](https://en.wikipedia.org/wiki/Time_zone#/media/File:World_Time_Zones_Map.png)
available for reference.

## Time Zone Handling in Pace

Pace uses the time zone information provided by your system to display and store
time data. When you log activities or view reports, the time is converted to
your local time zone for accurate representation.

You can also specify a custom time zone or time zone offset when logging an
activity using the `--time-zone` or `--time-zone-offset` flags. This is useful
when you want to track activities in a different time zone or when your system
time zone differs from the time zone you want to use for tracking.

For example, if you are traveling and want to log activities in the local time
zone of your destination, you can specify the time zone using the `--time-zone`
flag. This ensures that the activities are recorded accurately based on the
location where they occurred.

Similarly, if you are working remotely with a team in a different time zone, you
can specify the team's time zone when logging activities to maintain consistency
across the team.

## Best Practices

Here are some best practices for handling time zones in Pace:

- **Use the system time zone by default:** Unless you have a specific reason to
  use a different time zone, it is recommended to use the system time zone for
  logging activities. This ensures that the time data is consistent with other
  applications and services on your system.

- **Specify a time zone when needed:** When logging activities that occur in a
  different time zone, use the `--time-zone` flag to specify the correct time
  zone. This ensures that the activities are recorded accurately based on the
  location where they occurred.

- **Be consistent:** If you work across multiple time zones, try to maintain
  consistency in the time zone you use for tracking activities. This helps avoid
  confusion and ensures that your time data is accurate and meaningful.

- **Review time zone settings:** Periodically review your time zone settings in
  Pace to ensure that they are correct and up to date. Changes in time zones due
  to travel or daylight saving time adjustments can affect the accuracy of your
  time data.

- **Set default time zone preferences:** If you frequently work in a specific
  time zone, consider setting it as the default time zone in the pace config.
  This can save you time when logging activities and reduce the need to specify
  the time zone manually each time. You can use `pace settings set time-zone` to
  set the default time zone. Or re-run `pace setup config` to set the default
  time zone during the initial setup.

By following these best practices, you can ensure that your time data is
accurate, consistent, and meaningful, regardless of the time zones in which you
work or travel.
