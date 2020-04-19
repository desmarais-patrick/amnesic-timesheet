# Software requirements

## Intro

The requirements clearly translate what is to build from the user perspective.
Hence, this article is meant for designers, developers and testers 
of this system.

Requirements aim to be:

- *Cohesive* units, about one thing ☝
- *Fully described*, in one place 📦
- *Consistent*, avoiding contradictions and ambiguity between each one 🚅
- *Atomic*, as in validate A and B becomes validate A and validate B 🔬
- *Traceable*, as all requirements are in and well labeled with IDs 🔖
- *Current* and maintained, to avoid obsolete items and confusion ✨
- *Unambiguous*, with minimal jargon and extra details, factual and subject 
  to one interpretation 🔑
- *With specified importance* based on user value, stakeholder value, 
  time or budget 🏆
- *Verifiable* or testable, as being to add a checkmark once built 🔨

The requirements have been divided into:

1. Overall description
1. Business requirements
1. User requirements
1. Functional requirements
1. Non-functional requirements
1. Interface requirements

The writing style for the following requirements is *traditional text*.

## Overall description

The *amnesic timesheet* project originated from an idea to improve logging
time spent on different work activities to report to managers at work.
While keeping history of all work days isn't relevant, the logging could be
amnesic to only one day.

The following information is relevant to time logging:

- Start time
- End time
- Time spent on breaks
- Number of breaks
- Type of activities performed during the day and how long
- Total amount of time worked

The target users are office workers, such as software developers.
Such users may aim to improve their estimation skills or learn about their
capacity to better answer how much work they can take.

## Business requirements

B.1.
The project
shall
produce a timesheet system
enabling users to record the time spent on different activities for a given day.

## User requirements

U.1.
The user
should be able to
enter the amount time spent on break
for computing total time at work within start and end times.
#breaks

U.2.
The user
should
receive a report to find total time spent on work activities during a day.
#report

U.3.
The user
should have enough information to
report their time spent to another system based on the computed time.
#report

## Functional requirements

<sub>Next ID: F.11.</sub>

### Amnesic

F.1.
The timesheet system
shall
record time information for one work day at a time.

F.2.
The timesheet system
may
reset its values to record fresh time information.

### Initialization

F.3.
The timesheet system
should
allow to record what was done at a given time during the day
between a start time and an end time.

### Inputs

F.4.
The timesheet system
shall
support time inputs in the following format: `h:mm T`.
#input

### Schedule

F.5.
The timesheet system
shall
present a time schedule based on the start and end times.

F.6.
The timesheet system
shall
allow identification of a break period.

F.7.
The timesheet system
shall
allow adding a description of the activity performance.

F.8.
The timesheet system
shall
distinguish between a planned activity and a logged activity.

F.10.
The timesheet system
shall
assume that empty activity descriptions, without break indication,
mean that the same activity was repeated based on previous time slot.

### Report

F.9.
The timesheet system
shall
compute a time summary based on the logged activity.


## Non-functional requirements

NF.1.
The system
should
open in less than one second.

NF.2.
The system
should
display computed results instantly or less than one second.

## Interface requirements

I.1.
The interface
shall
support a desktop experience.

I.3.
The interface
should
support mobile, tablet and desktop dimensions
in the latest version of any of the following browsers:

- Google Chrome
- Mozilla Firefox
- Safari

I.2.
The interface 
shall
display validation messages when inputs are contradicting,
such as when start time is after end time.
