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

- **Id** (read-only): A unique identifier for each team record.
- **Name** (required): The official name of the team.
- **Description**: A brief description of the team, explaining what the team is about or its goals.
- **Status** (required): A dropdown menu to select the current status of the team. More at: [Team Record Lifecycle](#team-record-lifecycle).
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

## Action Buttons

### Main Buttons

- **Save Team**: Creates or updates the team record.
- **Delete Team**: Deletes the team record.
  - Available only on existing records.

### Players Buttons

- **View Tab**: View the list of players assigned to the team.
- **Add Player to Team**: Shows a pop-up window to add a player to the team.
- **Remove Player from Team**: Removes a players from the team (inline button).

### Injuries Buttons

- **View Tab**: View the list of injury details for players on the team.

### Staff Buttons

- **View Tab**: View the list of staff members assigned to the team.
- **Add Staff to Team**: Shows a pop-up window to add a staff member to the team.
- **Remove Staff from Team**: Removes a staff member from the team (inline button).

### Schedule Buttons

- **View Tab**: View the list of events assigned to the team.
- **Add Team to Schedule**: Shows a pop-up window to schedule the team for an (upcoming) series of events or matches.
- **Remove Team from Schedule**: Removes the team from a series of events or matches (inline button).

### Feedback Buttons

- **View Tab**: View the list of feedback given for the team’s performance.
- **Create Feedback**: Opens a new window to the feedback record to provide feedback for the team’s performance in a specific event with populated the Team field value where feedback details can be entered.
- **Delete Feedback**: Deletes the feedback (inline button).

### Achievements Buttons

- **View Tab**: View the list of the achievements of the team.
- **Create Achievement**: Opens a new window to the achievement record with populated the Team field value where achievement details can be entered.
- **Delete Achievement**: Deletes the achievement (inline button).

### Contracts and Payments Buttons

- **View Tab**: View the list of contracts associated with the team.
- **Create Contract**: Opens a new window to the contract record with populated the Team field value where contract details can be entered.
- **Delete Contract**: Deletes the contract (inline button).

## Required Roles

Please refer to the [Role Hierarchy section](system-roles) for details about role hierarchy. Users with higher roles can perform actions that require lower roles.

- **Retrieve Record**:
  - Requires `internal_user` role, if status is **Active** or **Archived** and team is associated to that user directly through **Player** or **Staff** tabs.
  - Requires `team_read`, `player_read` roles or higher.
- **Create Record**: Requires `team` role or higher.
- **Update Record**:
  - Requires `team` role or higher, if status is **Pending**, **Active**, or **Inactive**.
  - Requires `team_admin` role or higher, if status is **Archived**.
- **Delete Record**: Requires `team_admin` role or higher.
- _Players Tab_:
  - **Retrieve Record**: Requires `team_read`, `player_read` roles or higher.
  - **Create Record**: Requires `team`, `player_read` roles or higher.
  - **Update Record**: Does not exist.
  - **Delete Record**: Requires `team`, `player_read` roles or higher.
- _Injuries tab_:
  - **Retrieve Record**: Requires `team`, `player_read` role or higher.
  - **Create Record**: Does not exist.
  - **Update Record**: Does not exist.
  - **Delete Record**: Does not exist.
- _Staff Tab_:
  - **Retrieve Record**: Requires `team_read`, `employee_read` roles or higher.
  - **Create Record**: Requires `team`, `employee_read` roles or higher.
  - **Update Record**: Does not exist.
  - **Delete Record**: Requires `team`, `employee_read` roles or higher.
- _Schedule Tab_:
  - **Retrieve Record**: Requires `team_read`, `event_read` roles or higher.
  - **Create Record**: Requires `team_read`, `event` roles or higher.
  - **Update Record**: Does not exist.
  - **Delete Record**: Requires `team_read`, `event` roles or higher.
- _Feedback Tab_:
  - **Retrieve Record**: Requires `team_read`, `performance_read` roles or higher.
  - **Create Record**: Requires `team_read`, `performance` roles or higher.
  - **Update Record**: Does not exist.
  - **Delete Record**: Requires `team_read`, `performance_admin` roles or higher.
- _Achievements Tab_:
  - **Retrieve Record**: Requires `team_read`, `performance_read` roles or higher.
  - **Create Record**: Requires `team_read`, `performance_read` roles or higher.
  - **Update Record**: Does not exist.
  - **Delete Record**: Requires `team_read`, `performance_admin` roles or higher.
- _Contracts and Payments tab_:
  - **Retrieve Record**: Requires `team_read`, `financial_read` role or higher.
  - **Create Record**: Requires `team_read`, `financial` role or higher.
  - **Update Record**: Does not exist.
  - **Delete Record**: Requires `team_read`, `financial_admin` role or higher.

## Other Important Information

N/A