# Activity, Intermission, Session

This document explains the concepts of activity, intermission, and session in
pace.

## Activity

An activity is a period of time during which you are working on something. It
may be a task, a project, or any other kind of work or break.

An activity always has a GUID, a start time, an end time and a description. The
GUID is a unique identifier for the activity. The start time is the time when
you start working on the activity, and the end time is the time when you stop
working on the activity. A description is a short text that describes the
activity.

Activities may have a status, such as `active`, `held`, `finished`, et cetera.
The status of an activity may change over time. Activities can also have
categories, tags, and other optional metadata.

An activity may be interrupted by one or many intermissions. An activity may
also be part of a session.

## Intermission

An intermission is a period of time during which you are not working on
anything. It may be a break, a rest, or any other kind of pause.

An intermission is a special kind of activity. So overall it has the same
properties as an activity. An intermission always has a GUID, a start time, an
end time and a reason. The GUID is a unique identifier for the intermission. The
start time is the time when you start the intermission, and the end time is the
time when you stop the intermission. An intermission may interrupt an activity.
An intermission may also be part of a session.

In addition to the properties of an activity, an intermission has a reason which
internally is a description of the intermission. Also an intermission has a
`parent-id` field which is the GUID of the activity that the intermission
interrupts.

## Session

A session is a period of time during which you are working on a series of
activities that can be interrupted by intermissions. It may be a work session, a
study session, or any other kind of session. A session is basically a list of
activities and intermissions that are combined under the same category and
description.

A session has no unique identifier and not really an own start or end time, but
it inherits the duration of the activities and intermissions that are part of
the session. A session may have some optional metadata, such as a description
and other properties like duration amount and total duration lengths.
