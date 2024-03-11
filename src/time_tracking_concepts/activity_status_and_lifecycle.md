# Activity Status and Lifecycle

This document explains the concepts of activity status and lifecycle in pace.

## Activity Status

An activity may have a status, such as `active`, `held`, `finished`, et cetera.

An activity may have the following statuses:

- `active`
- `ended`
- `inactive`
- `held`

**Note**: In the future there may also be `archived`, `unarchived` and `deleted`
statuses. But for now, these are not implemented.

## Activity Lifecycle

When an activity is created, it is in the `inactive` state. As we are always
calling a wrapper function to begin an activity, the activity is automatically
set to `active` when it is created.

When you start working on the activity, the status remains `active`. When you
stop working on the activity with `end` or begin another activity the status
changes to `ended`.

When you pause the activity with `hold`, the status changes to `held`. When you
resume the activity with `resume`, the status changes back to `active`.

**NOTE**: There can be only one `active` activity at a time. If you start a new
activity, the previous one and all other active activities are automatically
concluded. This makes sure that there is no overlap between activities, as there
is no way to work on two activities at the same time.

One could say: "But multi-tasking!" - But that's not how pace works. Pace is
about focus and concentration. If you want to track multi-tasking, you can
create a new activity for each task and switch between them with `resume`. In
the future, we might add a feature to track multi-tasking more explicitly, e.g.
by being able to assign multiple tasks to an activity, and switch between these
tasks or something similar to that.
