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
on breaks and the total time spent working. This time is useful to copy over
another timesheet system used by the organization.

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

The following requirements may not encompass all the content described
in this overall description at first, but the requirements will grow
with the project.

The target users are office workers, such as software developers.
Such users may aim to improve their estimation skills or learn about their
capacity to better answer how much work they can take.

## Business requirements (B)

Business requirements describe high-level features.
They are requirements seen from a 30'000-foot viewpoint.

The following requirements are written using *traditional text*.

📄 B.1.
The system
shall
allow users to enter time spent on different activities for a given day
in order to log this information for review at the end of the day.

📄 B.2.
The system
shall
produce an overall report
enabling users to review and copy the time information into another system.

📄 B.3.
The system
shall
allow users to enter a day plan according to project priorities
enabling users to compare time logged with day plan.

## User requirements (U)

User requirements describe features from the point of view of the user.

The following requirements are written using *user stories*.

📖 U.1.
In order to review how much time was spent on work,
users need to subtract the time spent on breaks from total time at work,
based on a start and end time.
🛋 *breaks*

📖 U.2.
In order to report total time spent on work activities in a day,
users want to review a sum of all time spent on those activities.
🗄 *report*

📖 U.3.
In order to review time spent per activity,
users want to track the times of the day when activity was being accomplished.
📝 *logging*

📖 U.4.
In order to plan and estimate time for activities in their day,
users want to assign time slots to activity as the day starts.
🎞 *planning*

## Functional requirements (F)

Functional requirements outline the functions of the system with
behaviours, inputs and outputs.

The following requirements follow a *use case* form of description.
A use case diagram support the use cases described below.

Actors included in the following requirements include:

- Software Developer (Patrick)

<sub>Next ID: F.11.</sub>

### Amnesic

📒  F.1. Reset timesheet

Patrick enters their times for one day at a time.
If day times are filled, they clear the timesheet to start a new one.

*Actor(s)*: Patrick

*Scope*: Amnesic Timesheet Main

*Priority*: Essential

*Assumptions*: Patrick works more than one day.

*Preconditions*: None

*Postconditions*: Patrick is ready to start logging his times for today.

*Trigger*: Patrick starts a new day at work.

*Main success scenario*:

1. When Patrick opens the system at the beginning of the day, they see the 
   last entry.
1. Patrick resets the timesheet day.
1. System forgets the last entry and displays a fresh timesheet.

*Alternative scenario*:

If Patrick didn't record his time report for the previous day:

1. Patrick opens the report and copies the information to the other system.

*Tags*: 📝 *logging*, 🗄 *report*

---

### General

📒 F.2. Enter reference times

System receives input for start time and target duration,
as well as expected number of 15-minute breaks.

<!-- time inputs in the following format: `h:mm T`. -->

*Tags*: 📝 *logging*, 🛋 *breaks*, 🎞 *planning*

📒 F.3. Log activity

System records a time period where the activity was performed
with reference time guidelines.

System shall record a short description of the activity.

System differentiates breaks from work times.

*Tags*: 📝 *logging*, 🛋 *breaks*

---

📒 F.4. Report time spent on activities

System should sum time spent on work activities.

*Tags*: 🗄 *report*

---

📒 F.5. Plan day activities

System shall distinguish between a planned activity and a logged activity.

*Tags*: 🎞 *planning*

---

## Non-functional requirements

Non-functional requirements describe what's around functionality:
quality, constraints, non-behaviours, etc.

The following requirements are written using *traditional text* style.

🔖 NF.1.
The system
should
open in less than one second.

🔖 NF.2.
The system
should
display computed results instantly or less than one second.

## Interface requirements

The interface requirements outline interactions with the system.
It includes:

- Hardware requirements
- Software requirements
- System communication
- User interfaces

The following requirements use *traditional text* as the form of writing.
Mockups and style guides accompany these requirements.

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
