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

---

### Use cases

![Use case diagram](./diagrams/use-case-diagram-amnesic-timesheet.svg)

<style>
.use-case { border: 1px solid #999; padding: 1rem; margin-bottom: 2rem; }
.use-case-row {
  display: block;
  width: 100%;
  padding: .125rem .25rem;
  box-sizing: border-box;
}
.use-case-row-space-after { margin-bottom: .5rem; }
.use-case-row-header {
    display: inline-block;
    width: 25%;
    padding-right: 1rem;
    box-sizing: border-box;
    text-align: right;
    vertical-align: top;
    opacity: .65;
}
.use-case-row-value { display: inline-block; width: 75%; }
.use-case-row-value p { margin: 0; }
.use-case-row-value sub { opacity: .5; }
</style>
<div class="use-case">
  <div class="use-case-row use-case-row-space-after">
    <div class="use-case-row-header">
      <label for="f_1_title">Title</label>
    </div><div class="use-case-row-value">
      <p id="f_1_title"><strong> 📒 F.1. Reset logs</strong></p>
    </div>
  </div>
  <div class="use-case-row use-case-row-space-after">
    <div class="use-case-row-header">
      <label for="f_1_actors">Actor(s)</label>
    </div><div class="use-case-row-value">
      <p id="f_1_actors">Patrick</p>
    </div>
  </div>
  <div class="use-case-row">
    <div class="use-case-row-header">
      <label for="f_1_scope">Scope</label>
    </div><div class="use-case-row-value">
      <p id="f_1_scope">Main</p>
    </div>
  </div>
  <div class="use-case-row use-case-row-space-after">
    <div class="use-case-row-header">
      <label for="f_1_priority">Priority</label>
    </div><div class="use-case-row-value">
      <p id="f_1_priority">Essential</p>
    </div>
  </div>
  <div class="use-case-row">
    <div class="use-case-row-header">
      <label for="f_1_assumptions">Assumptions</label>
    </div><div class="use-case-row-value">
      <p id="f_1_assumptions">Patrick use the system more than one day.</p>
    </div>
  </div>
  <div class="use-case-row">
    <div class="use-case-row-header">
      <label for="f_1_preconditions">Preconditions</label>
    </div><div class="use-case-row-value">
      <p id="f_1_preconditions">None</p>
    </div>
  </div>
  <div class="use-case-row use-case-row-space-after">
    <div class="use-case-row-header">
      <label for="f_1_postconditions">Postconditions</label>
    </div><div class="use-case-row-value">
      <p id="f_1_postconditions">Patrick is ready to start logging times for today.</p>
    </div>
  </div>
  <div class="use-case-row">
    <div class="use-case-row-header">
      <label for="f_1_trigger">Trigger</label>
    </div><div class="use-case-row-value">
      <p id="f_1_trigger">Patrick starts a new day at work.</p>
    </div>
  </div>
  <div class="use-case-row">
    <div class="use-case-row-header">
      <label for="f_1_main_success_scenario">Main success scenario:</label>
    </div><div class="use-case-row-value">
      <ol id="f_1_main_success_scenario">
        <li>When Patrick opens the system at the beginning of the day, they see the 
   last entry.</li>
        <li>Patrick resets the timesheet day.</li>
        <li>System forgets the last entry and displays a fresh timesheet.</li>
      </ol>
    </div>
  </div>
  <div class="use-case-row">
    <div class="use-case-row-header">
      <label for="f_1_alternative_scenario">Alternative scenario:</label>
    </div><div class="use-case-row-value">
      <p id="f_1_alternative_scenario">
        If Patrick didn't record his time report for the previous day:
      </p>
      <ol>
        <li>Patrick opens the report and copies the information to the other system.</li>
      </ol>
    </div>
  </div>
</div>

<div class="use-case">
  <div class="use-case-row use-case-row-space-after">
    <div class="use-case-row-header">
      <label for="f_2_title">Title</label>
    </div><div class="use-case-row-value">
      <p id="f_2_title"><strong> 📒 F.2. Enter reference times</strong></p>
    </div>
  </div>
  <div class="use-case-row use-case-row-space-after">
    <div class="use-case-row-header">
      <label for="f_2_actors">Actor(s)</label>
    </div><div class="use-case-row-value">
      <p id="f_2_actors">Patrick</p>
    </div>
  </div>
  <div class="use-case-row">
    <div class="use-case-row-header">
      <label for="f_2_scope">Scope</label>
    </div><div class="use-case-row-value">
      <p id="f_2_scope">Main, 🛋 breaks, 🎞 planning </p>
    </div>
  </div>
  <div class="use-case-row use-case-row-space-after">
    <div class="use-case-row-header">
      <label for="f_2_priority">Priority</label>
    </div><div class="use-case-row-value">
      <p id="f_2_priority">Essential</p>
    </div>
  </div>
  <div class="use-case-row">
    <div class="use-case-row-header">
      <label for="f_2_assumptions">Assumptions</label>
    </div><div class="use-case-row-value">
      <p id="f_2_assumptions">Patrick uses the system for a full day.</p>
    </div>
  </div>
  <div class="use-case-row">
    <div class="use-case-row-header">
      <label for="f_2_preconditions">Preconditions</label>
    </div><div class="use-case-row-value">
      <ul id="f_2_preconditions">
        <li>Patrick has consciously cleared reference times (previous entry) before starting a new day, if a previous entry was present.</li>
        <li>System displays default time values, or it displays time values based on the last entry if Patrick has already used the system. <sub>(💡 a double-reset to return to last entry and then default values, to strengthen efficient habits)</sub></li>
      </ul>
    </div>
  </div>
  <div class="use-case-row use-case-row-space-after">
    <div class="use-case-row-header">
      <label for="f_2_postconditions">Postconditions</label>
    </div><div class="use-case-row-value">
      <p id="f_2_postconditions">The end time is computed based on the start time, the total duration and the expected number of breaks.</p>
    </div>
  </div>
  <div class="use-case-row">
    <div class="use-case-row-header">
      <label for="f_2_trigger">Trigger</label>
    </div><div class="use-case-row-value">
      <p id="f_2_trigger">Patrick starts a new day plan.</p>
    </div>
  </div>
  <div class="use-case-row">
    <div class="use-case-row-header">
      <label for="f_2_main_success_scenario">Main success scenario:</label>
    </div><div class="use-case-row-value">
      <ol id="f_2_main_success_scenario">
        <li>Patrick enters start time.</li>
        <li>Patrick enters target duration.</li>
        <li>Patrick enters expected number of breaks.</li>
        <li>System computes end time.</li>
      </ol>
    </div>
  </div>
  <div class="use-case-row">
    <div class="use-case-row-header">
      <label for="f_2_alternative_scenario">Alternative scenario:</label>
    </div><div class="use-case-row-value">
      <p id="f_2_alternative_scenario">
        Patrick adjusts one of the values to reach satisfying end time.
      </p>
    </div>
  </div>
</div>

<div class="use-case">
  <div class="use-case-row use-case-row-space-after">
    <div class="use-case-row-header">
      <label for="f_3_title">Title</label>
    </div><div class="use-case-row-value">
      <p id="f_3_title"><strong> 📒 F.3. Log activity</strong></p>
    </div>
  </div>
  <div class="use-case-row use-case-row-space-after">
    <div class="use-case-row-header">
      <label for="f_3_actors">Actor(s)</label>
    </div><div class="use-case-row-value">
      <p id="f_3_actors">Patrick</p>
    </div>
  </div>
  <div class="use-case-row">
    <div class="use-case-row-header">
      <label for="f_3_scope">Scope</label>
    </div><div class="use-case-row-value">
      <p id="f_3_scope">Main, 📝 logging, 🛋 breaks, 🗄 report, 🎞 *planning* </p>
    </div>
  </div>
  <div class="use-case-row use-case-row-space-after">
    <div class="use-case-row-header">
      <label for="f_3_priority">Priority</label>
    </div><div class="use-case-row-value">
      <p id="f_3_priority">High</p>
    </div>
  </div>
  <div class="use-case-row">
    <div class="use-case-row-header">
      <label for="f_3_assumptions">Assumptions</label>
    </div><div class="use-case-row-value">
      <p id="f_3_assumptions">Patrick performs one or more work activities.</p>
    </div>
  </div>
  <div class="use-case-row">
    <div class="use-case-row-header">
      <label for="f_3_preconditions">Preconditions</label>
    </div><div class="use-case-row-value">
      <ul id="f_3_preconditions">
        <li>Reference times have been submitted.</li>
    </div>
  </div>
  <div class="use-case-row use-case-row-space-after">
    <div class="use-case-row-header">
      <label for="f_3_postconditions">Postconditions</label>
    </div><div class="use-case-row-value">
      <ul id="f_3_postconditions">
        <li>Time period has been (un)assigned a new activity and marked as completed.</li>
        <li>A new activity appears in the summary, if it didn't already exist, or an activity disappears if it was replaced or removed, and activity total times have been adjusted.</li>
        <li>The total time accounts for activity change (increase if marked as completed or unmarked as break, decrease if unmarked or newly marked as break).</li>
        <li>Break is recorded, if the activity is marked as break.</li>
      </ul>
    </div>
  </div>
  <div class="use-case-row">
    <div class="use-case-row-header">
      <label for="f_3_trigger">Trigger</label>
    </div><div class="use-case-row-value">
      <p id="f_3_trigger">Patrick completes one or many time periods and wants to log his time.</p>
    </div>
  </div>
  <div class="use-case-row">
    <div class="use-case-row-header">
      <label for="f_3_main_success_scenario">Main success scenario:</label>
    </div><div class="use-case-row-value">
      <ol id="f_3_main_success_scenario">
        <li>Patrick enters short description (only once for contiguous time periods) of the activity performed, at the start of the time period.</li>
        <li>Patrick marks the activity as completed for relevant time periods, from start time period to current time.</li>
        <li>Patrick marks time periods considered as breaks.</li>
        <li>System computes the live summary of time accumulated by activity and the sum of all of them, taking into account breaks.</li>
      </ol>
    </div>
  </div>
  <div class="use-case-row">
    <div class="use-case-row-header">
      <label for="f_3_alternative_scenario">Alternative scenario:</label>
    </div><div class="use-case-row-value">
      <ul id="f_3_alternative_scenario">
        <li>Patrick adjusts one or more time periods by modifying existing description, (un)marking as complete, (un)marking as break.</li>
        <li>Patrick enters more than one description. <sub>💡 Use "//" as a comment for special descriptions that don't count as new activity.</sub></li>
        <li>Patrick enters an activity without marking as complete, to indicate a planned activity.</li>
      </p>
    </div>
  </div>
</div>


## Non-functional requirements

Non-functional requirements describe what's around functionality:
quality, constraints, non-behaviours, etc.

The following requirements are written using *traditional text* style using the following terms:

- *shall*: is required to
- *should*: is the preferred option among several
- *may*: permissible
- *can*: is able to
- *will*: fact, not mandatory

---

🔖 NF.1.
The system
should
open in less than one second.

🔖 NF.2.
The system
should
display computed results instantly or less than one second.

---

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
support a desktop experience on:

- MacBook Pro 15-inch (2880x1800)
- Lenovo tower with 24-inch Dell (1920x1080)
- Lenovo laptop 17-inch (1920x1080)

with various application window widths and heights
in the Google Chrome browser.

🔖 I.2.
The interface
may
support mobile, tablet and desktop dimensions
in the latest version of the following browsers:

- Mozilla Firefox
- Safari

🔖 I.3.
The interface
may
support the following devices:

- iPhone SE first generation
- Nexus 10-inch tablet by Samsung

🔖 I.4.
The interface 
shall
display validation messages when inputs are contradicting,
such as when start time is after end time.
