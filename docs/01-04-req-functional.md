## 1.4. Functional requirements (F)

Functional requirements outline the functions of the system with
behaviours, inputs and outputs.

The following requirements follow a *use case* form of description.
A use case diagram support the use cases described below.

### Key info

**Actors** included in the following requirements include:

- Software Developer (Patrick)

**Scope** values include:

- 🏎 Main
- 🎞 planning
- 🛋 breaks
- 📝 logging
- 🗄 report

**Priority** values include:

- Essential
- High

---

### Use cases

![Use case diagram](./diagrams/use-case-diagram-amnesic-timesheet.svg)

📒 F.1. Enter reference times

- *Actor(s)*: Patrick
- *Scope*: 🏎 Main, 🛋 breaks, 🎞 planning
- *Priority*: Essential
- *Assumptions*: Patrick uses the system more than one day.
- *Preconditions*:
  - Patrick has consciously cleared reference times (previous entry) before starting a new day, if a previous entry was present.
  - System displays default time values, or it displays time values based on the last entry if Patrick has already used the system. <sub>(💡 a double-reset to return to last entry and then default values, to strengthen efficient habits)</sub>
- *Postconditions*: The end time is computed based on the start time, the target duration and the expected number of breaks.
- *Trigger*: Patrick starts a new day at work.
- *Main success scenario*:
  1. Patrick enters start time.
  1. Patrick enters target duration.
  1. Patrick enters expected number of breaks.
  1. System computes end time.
- *Alternative scenario*:
  1. Patrick adjusts one of the values to reach satisfying end time.
  1. System computes adjusted end time.

📒 F.2. Plan activities

- *Actor(s)*: Patrick
- *Scope*: 🎞 planning, 🛋 breaks
- *Priority*: High
- *Assumptions*: Patrick plans for one or more work activities during the day.
- *Preconditions*: Reference times have been submitted. See **F.1**.
- *Postconditions*:
  - Time periods have been (un)assigned new activities.
  - Break is recorded, if the activity is marked as break.
- *Trigger*: Patrick plans his work activities and breaks within time references.
- *Main success scenario*:
  1. Patrick enters short description (only once for contiguous time periods) of the planned activity, at the start of contiguous time periods (blocks).
  1. Patrick marks time periods considered as breaks.
- *Alternative scenario*:
  - Patrick changes plan during the day.
- *Extra*: Special descriptions may be entered as comments with leading "//".

📒 F.3. Log activity

- *Actor(s)*: Patrick
- *Scope*: 📝 logging, 🛋 breaks, 🗄 report, 🎞 planning
- *Priority*: High
- *Assumptions*: Patrick performs one or more work activities.
- *Preconditions*:
  - Reference times have been submitted. See **F.1**.
  - Activities have been planned. See **F.2**.
- *Postconditions*:
  - Activity has been confirmed and marked as completed or break.
  - Activity description change is recorded.
- *Trigger*: Patrick completes one or many time periods and wants to log his time on one or more activities or break periods.
- *Main success scenario*:
  1. Patrick enters short description (only once for contiguous time periods) of the activity performed, at the start of the time period, if different from planning.
  1. Patrick marks the activity as completed for relevant time periods, from start time period to current time, and interface shows recorded activity (for example when reflecting a repeated activity over many time periods).
  1. Patrick marks time periods considered as breaks, if any.
- *Alternative scenario*:
  - Time period has been (un)assigned a new activity.
  - Patrick adjusts one or more time periods by modifying existing description, (un)marking as complete, (un)marking as break.
- *Extra*: Special descriptions may be entered as comments with leading "//".

📒 F.4. Review activities

- *Actor(s)*: Patrick
- *Scope*: 🗄 report, 🛋 breaks
- *Priority*: High
- *Assumptions*: Patrick performs one or more work activities.
- *Preconditions*:
  - Reference times have been submitted. See **F.1**.
  - Activities have been planned. See **F.2**.
  - Work and breaks have been logged. See **F.3**.
- *Postconditions*:
  - Activities appears in the summary.
    - Original activities account in planned times.
    - Confirmed and completed activities account in log times.
  - Break is recorded, if the activity is marked as break.
  - Activity changes during the day are reflected in the summary.
    - If an activity didn't already exist, it is logged separately.
    - If an activity disappears and doesn't appear anywhere else, it is removed.
    - The activity total time reflects number of time periods it appears in.
  - The total time accounts for activity and breaks.
- *Trigger*: Patrick wants to review his planning or activity log.
- *Main success scenario*:
  1. Patrick navigates to summary section.
  1. System computes the live summary of time accumulated by activity and the sum of all of them, taking into account breaks.
- *Alternative scenario*:
  - Patrick hasn't entered any activity.
  - Patrick resets activities. See **F.5**.
- *Extra*: Comments with leading "//" do not count as activities.

📒 F.5. Reset timesheet

- *Actor(s)*: Patrick
- *Scope*: 🏎 Main
- *Priority*: Essential
- *Assumptions*: Patrick uses the system more than one day.
- *Preconditions*: (None)
- *Postconditions*: Patrick is ready to start logging times for today.
- *Trigger*: Patrick starts a new day at work.
- *Main success scenario*:
  1. When Patrick opens the system at the beginning of the day, they see the last entry.
  1. Patrick resets the timesheet day.
  1. System forgets the last entry and displays a fresh timesheet.
- *Alternative scenario*:
  - If Patrick didn't record his time report for the previous day, then Patrick opens the report and copies the information to the other system.

---

[`..` (Requirements)](./01-00-requirements.md)

1. [Context](./01-01-req-context.md)
1. [Business requirements](./01-02-req-business.md)
1. [User requirements](./01-03-req-user.md)
1. ** [Functional requirements](./01-04-req-functional.md)
1. [Non-functional requirements](./01-05-req-non-functional.md)
1. [Interface requirements](./01-06-req-interface.md)
