# Software requirements

## About this documentation

The requirements aim to clearly translate what is to be built 
from the user's perspective.
This article is meant for designers, developers and testers.

Requirements aim to be:

- *Cohesive* units, about one thing ☝
- *Fully described*, in one place 📦
- *Consistent*, avoiding contradictions and ambiguity with each other 🚅
- *Atomic*, as in validate A and B becomes validate A and validate B 🔬
- *Traceable*, as all requirements are in and well labeled with IDs 🔖
- *Current* and maintained, to avoid obsolete items and 
  confusion with farfetched features ✨
- *Unambiguous*, with minimal jargon and extra details, factual and subject 
  to one interpretation 🔑
- *With specified importance* based on user value, stakeholder value, 
  time or budget (shall, should, could, ) 🏆
- *Verifiable* or testable, as checkmark-able once built 🔨

The requirements have been divided into:

1. Overall description
1. Business requirements
1. User requirements
1. Functional requirements
1. Non-functional requirements
1. Interface requirements

The writing style for the following requirements varies between:

- *traditional text*,
- *user stories*, and
- *use cases*.

Happy reading! 🙂


## Overall description

The *amnesic timesheet* project originated from an idea to improve logging
time spent on different work activities. The motivation behind tracking this
time is two-fold:

- Learn about estimating work and capacity
- Share this information with managers for project control

While other software allow to report such information everyday,
keeping history of all work days isn't relevant for this system.
The logging could be amnesic, restricted to one day at a time;
however, it could be saved in later project iterations.

**Logging**

The following information is relevant to time logging:

- Start time
- End time
- Time spent on breaks (to subtract from total time)
- Time spent on activities and projects

With this information, we can compute more metrics such as the total time spent
on breaks and the total time spent working.

**Planning and estimating**

The following information is relevant to planning and estimating:

- Top priorities and goals
- Time distribution and guidelines
- Schedule with day events (ex. meeting)
- Steps to accomplish an activity
- Daily activities

With this information, we can get an overview of the expected time to spend
before starting logging our activities and adjust plan as we learn.

**Reviewing**

The following information is relevant to reviewing:

- Levels of energy when day started and day ended
- Overall feelings during the day (ex. frustrations, happy moments)
- Number of breaks
- Perceived productivity
- Estimation effectiveness
- Number of priorities accomplished
- What I am grateful for
- Lessons to take from the day
- Feedback notes and points of improvements
- Progress towards short-, medium- and long-term goals (big picture)

The review helps with introspection and requires a step back.

--

The target users are office workers, such as software developers.
Such users may aim to improve their estimation skills or learn about their
capacity to better answer how much work they can take.

## Business requirements (B)

🔖 B.1.
The system
shall
allow users to enter time spent on different activities for a given day
in order to log this information for review at the end of the day.

🔖 B.2.
The system
shall
produce an overall report system
enabling users to review and copy the time information into another system.

🔖 B.3.
The system
shall
allow users to enter a day plan according to project priorities
enabling users to compare time logged with day play.

## User requirements (U)

🔖 U.1.
The user
should be able to
enter the amount of time spent on breaks
for computing total time at work within start and end times.
🛋 *breaks*

🔖 U.2.
The user
should
receive a report to find total time spent on work activities during a day.
🗄 *report*

🔖 U.3.
The user
should have enough information to
report their time spent to another system based on the computed time.
🗄 *report*

## Functional requirements (F)

<sub>Next ID: F.11.</sub>

### Amnesic

🔖 F.1.
The timesheet system
shall
record time information for one work day at a time.

🔖 F.2.
The timesheet system
may
reset its values to record fresh time information.

### Initialization

🔖 F.3.
The timesheet system
should
allow to record what was done at a given time during the day
between a start time and an end time.

### Inputs

🔖 F.4.
The timesheet system
shall
support time inputs in the following format: `h:mm T`.
✏ *input*

### Schedule

🔖 F.5.
The timesheet system
shall
present a time schedule based on the start and end times.

🔖 F.6.
The timesheet system
shall
allow identification of a break period.

🔖 F.7.
The timesheet system
shall
allow adding a description of the activity performance.

🔖 F.8.
The timesheet system
shall
distinguish between a planned activity and a logged activity.

🔖 F.10.
The timesheet system
shall
assume that empty activity descriptions, without break indication,
mean that the same activity was repeated based on previous time slot.

### Report

🔖 F.9.
The timesheet system
shall
compute a time summary based on the logged activity.


## Non-functional requirements

🔖 NF.1.
The system
should
open in less than one second.

🔖 NF.2.
The system
should
display computed results instantly or less than one second.

## Interface requirements

🔖 I.1.
The interface
shall
support a desktop experience.

🔖 I.3.
The interface
should
support mobile, tablet and desktop dimensions
in the latest version of any of the following browsers:

- Google Chrome
- Mozilla Firefox
- Safari

🔖 I.2.
The interface 
shall
display validation messages when inputs are contradicting,
such as when start time is after end time.
