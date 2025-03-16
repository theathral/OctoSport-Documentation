# Team Form and Actions

The Team form is used for creating, updating, and managing teams within the system. Users can interact with the form to enter or modify team details, including name, status, sport, and key personnel such as coaches and captains. The form also includes functions for managing the team’s logo and related data.

```{admonition} Teams vs Groups
:class: tip, dropdown

Groups and Teams are distinct entities within the system. Groups are used to control the visibility of pages and actions, while Teams are designed to organize players and staff for operational purposes.
```

## Navigation (TBD)

```{warning} Under Construction
```

Steps to locate this page:

- Navigate to the **Teams** section in the main menu.
- Select the **Team Form** option from the available list.

## Fields & Functions

- **Id** (read-only): A unique identifier for each team.
- **Name** (required): The official name of the team.
- **Description**: A brief description of the team, explaining what the team is about or its goals.
- **Status** (required): A dropdown menu to select the current recovery status of the team. More at: [Team Record Lifecycle](#team-record-lifecycle).
- **Sport** (required): Reference field linking to the sport that the team participates in. This is linked to a list of available sports for the sports club.
- **Coach**: Reference field linking to the coach of the team. Only users with the `coach` role appear here.
- **Captain**: Reference field linking to the captain of the team from the list of players.
- **Logo**: Image that represents the team, such as the team's official logo.

[IMAGE]

## Team Record Lifecycle

The team record progresses through the following stages, with specific edit permissions based on user roles:

- **Pending**: The team record is in the initial stage, awaiting review or approval.
- **Active**: The team record is fully operational and in use.
- **Archived**: The team record is no longer active but retained for historical reference.
    - Requires `player_admin` or `admin` role to edit the record after the status is saved to this value.
- **Inactive**: The team record is inactive and not in use.

## Related Lists

Tabs that point to other sections related to the team:

- **[Players](./player_form.md)**: View and manage the players on the team.
  [IMAGE]

- **[Injuries](./injury_form.md)**: View injuries related to players on the team.
  [IMAGE]

- **[Staff](./employee_form.md)**: View and manage the staff members assigned to the team.
  [IMAGE]

- **[Schedule](./schedule_form.md)**: View and manage the team’s schedule, including upcoming events and matches.
  [IMAGE]

- **[Feedback](./feedback_form.md)**: View feedback related to the team's performance.
  [IMAGE]

- **[Achievements](./achievement_form.md)**: View any awards or achievements the team has earned.
  [IMAGE]

- **[Contracts](./contract_form.md)**: View contracts associated to the team.
  [IMAGE]

- **[Sponsors](./sponsor_form.md)**: View information about sponsors supporting the team.
  [IMAGE]

## Actions & Required Roles

```{admonition} Explanation of Roles
:class: tip, dropdown

Please refer to the [Role Hierarchy section](system-roles) for details about role hierarchy. Users with higher roles can perform actions that require lower roles.
```

### Main Actions

- **View Team**: Allows you to view the team's details.
    - Requires `team_read` role or higher.
- **Save Team (New Record)**: Allows you to create a new team record.
    - Requires `team` role or higher.
- **Save Team (Existing Record)**: Allows you to modify the details of an existing team record.
    - Requires `team` role or higher.
- **Delete Team**: Allows you to delete a team.
    - Requires `team_admin` role or higher.

### Players Actions

- **View Players**: Allows you to view the list of players associated with the team.
    - Requires `team_read`, `player_read` roles or higher.
- **Add Player to Team**: Allows you to add a new player to the team.
    - **How**: This action will open a pop-up window to add a player.
    - Requires `team`, `player_read` roles or higher.
- **Remove Player from Team**: Allows you to remove a player from the team.
    - **How**: This action is available inline next to each record.
    - Requires `team`, `player_read` roles or higher.

### Injuries Actions

- **View Injuries**: Allows you to view injury details for players on the team.
    - Requires `player_read` role or higher.

### Staff Actions

- **View Staff**: Allows you to see the list of staff members assigned to the team.
    - Requires `team_read` and `employee_read` roles or higher.
- **Add Staff to Team**: Allows you to add a new staff member to the team.
    - **How**: This action will open a pop-up window to add a staff member.
    - Requires `team` and `employee_read` roles or higher.
- **Remove Staff from Team**: Allows you to remove a staff member from the team.
    - **How**: This action is available inline next to each record.
    - Requires `team` and `employee_read` roles or higher.

### Schedule Actions

- **View Schedule**: Allows you to view the team’s schedule and events.
    - Requires `team_read` and `event_read` roles or higher.
- **Add Team to Schedule**: Allows you to schedule the team for an (upcoming) series of events or matches.
    - **How**: This action will open a pop-up window to add a schedule.
    - Requires `team_read` and `event` roles or higher.
- **Remove Team from Schedule**: Allows you to remove the team from a series of events or matches.
    - **How**: This action is available inline next to each record.
    - Requires `team_read` and `event` roles or higher.

### Feedback Actions

- **View Feedback**: Allows you to view feedback given for the team’s performance.
    - Requires `team_read` and `performance_read` roles or higher.
- **Give Feedback**: Allows you to provide feedback for the team’s performance in a specific event.
    - **How**: This action will open a pop-up window to add a feedback.
    - Requires `team_read` and `performance` roles or higher.
- **Delete Feedback**: Allows you to delete a feedback from the system associated with the team.
    - **How**: This action is available inline next to each record.
    - Requires `team_read` and `performance_admin` roles or higher.

### Achievements Actions

- **View Achievements**: Allows you to see the team’s achievements and awards.
    - Requires `team_read` and `performance_read` roles or higher.
- **Add Achievement**: Allows you to add a new achievement for the team.
    - **How**: This action will open a pop-up window to add a feedback.
    - Requires `team_read` and `performance` roles or higher.
- **Delete Achievement**: Allows you to delete an achievement from the system associated with the team.
    - **How**: This action is available inline next to each record.
    - Requires `team_read` and `performance_admin` roles or higher.

### Contracts Actions

- **View Contract and Payment**: Allows you to view the team’s contract and payment details.
    - Requires `user_read_basic`, `team_read`, and `financial_read` roles or higher.
- **Create Contract for Team**: Allows you to create a new contract for the team.
    - **How**: This option opens a new window to the contract record with populated the Team field value where you can enter the contract details.
    - Requires `user_read_basic`, `team_read`, and `financial` roles or higher.
- **Delete Contract**: Allows you to remove an existing contract from the team.
    - **How**: This action is available inline next to each record.
    - Requires `user_read_basic`, `team_read`, and `financial_admin` roles or higher.

## Other Important Information

N/A