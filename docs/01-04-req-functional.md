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
