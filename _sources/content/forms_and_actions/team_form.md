# Team Form and Actions

The Team form is used for creating, updating, and managing teams within the system. Users can interact with the form to enter or modify team details, including name, status, sport, and key personnel such as coaches and captains. The form also includes functions for managing the team’s logo and related data.

```{admonition} Teams vs Groups
:class: tip, dropdown

Groups and Teams are distinct entities within the system. Groups are used to control the visibility of pages and actions, while Teams are designed to organize players and staff for operational purposes.
```

## Navigation (TBD)
Steps to locate this page:
- Navigate to the **Teams** section in the main menu.
- Select the **Team Form** option from the available list.

## Fields & Functions
- **Id** (read-only): A unique identifier for each team.
- **Name**: The official name of the team.
- **Description**: A brief description of the team, explaining what the team is about or its goals.
- **Status**: A dropdown menu where you can choose the current status of the team. Options include:
    - Pending
    - Active
    - Archived
    - Inactive
- **Sport**: Select the sport that the team participates in. This is linked to a list of available sports.
- **Coach**: Select the coach for the team. Only users with the role of **coach** will appear here.
- **Captain**: Select the captain of the team. This will link to the list of players.
- **Logo**: Upload an image that represents the team, such as the team's official logo.

## Related Lists
Tabs that point to other sections related to the team:
- **Players**: View and manage the players on the team.
- **Injuries**: View injuries related to players on the team.
- **Staff**: View and manage the staff members assigned to the team.
- **Schedule**: View and manage the team’s schedule, including upcoming events and matches.
- **Feedback**: View feedback related to the team's performance.
- **Achievements**: View any awards or achievements the team has earned.
- **Contracts**: View contracts associated to the team.
- **Sponsors**: View information about sponsors supporting the team.

## Actions & Required Roles

```{admonition} Explanation of Roles
:class: tip, dropdown

Please refer to the [Role Hierarchy section](system-roles) for details about role hierarchy. Users with higher roles can perform actions that require lower roles.
```

### Main Actions
- **View Team**: Allows you to view the team's details.
  - Requires **team_read** role or higher.
- **Save Team (New Record)**: Saves the team details when creating a new team.
  - Requires **team** role or higher.
- **Save Team (Existing Record)**: Saves any changes made to an existing team.
  - Requires **team** role or higher.
- **Delete Team**: Allows you to delete a team.
  - **Attention**: This action will remove all associated data, such as players, staff, and schedules.
  - Requires **team_admin** role or higher.

### Players Actions
- **View Players**: Allows you to view the list of players associated with the team.
  - Requires **team_read**, **player_read** roles or higher.
- **Add Player to Team**: Lets you add a new player to the team. You can search for players and select those not already in the team. This action will open a pop-up window to add a player.
  - Requires **team**, **player_read** roles or higher.
- **Remove Player from Team**: Lets you remove a player from the team. This action is available inline next to each player in the team.
  - Requires **team**, **player_read** roles or higher.

### Injuries Actions
- **View Injuries**: Allows you to view injury details for players on the team. This is indirectly available through the Players section.
  - Requires **player_read** role or higher.

### Staff Actions
- **View Staff**: Allows you to see the list of staff members assigned to the team.
  - Requires **team_read**, **employee_read** roles or higher.
- **Add Staff to Team**: Lets you add a new staff member to the team. You can search for staff and select those not already part of the team. This action will open a pop-up window to add staff.
  - Requires **team**, **employee_read** roles or higher.
- **Remove Staff from Team**: Lets you remove a staff member from the team. This action is available inline next to each staff member in the team.
  - Requires **team**, **employee_read** roles or higher.

### Schedule and Performance Actions
- **View Schedule**: Allows you to view the team’s schedule and events.
  - Requires **team_read**, **event_read** roles or higher.
- **Add Team to Schedule**: Lets you schedule the team for an upcoming event or match. This option will open a pop-up window, allowing you to select the event.
  - Requires **team_read**, **event** roles or higher.
- **Remove Team from Schedule**: Lets you remove the team from an event or match. This option is available inline next to each scheduled event.
  - Requires **team_read**, **event** roles or higher.

### Feedback Actions
- **View Feedback**: Allows you to view feedback given for the team’s performance.
  - Requires **team_read**, **performance_read** roles or higher.
- **Give Feedback**: Lets you provide feedback for the team’s performance in a specific event. This opens a new window where feedback can be added.
  - Requires **team_read**, **performance** roles or higher.
- **Delete Feedback**: Lets you remove feedback for the team. This option is available inline next to existing feedback.
  - Requires **team_read**, **performance** roles or higher.

### Achievements Actions
- **View Achievements**: Allows you to see the team’s achievements and awards.
  - Requires **team_read**, **performance_read** roles or higher.
- **Add Achievement**: Lets you add a new achievement for the team. This opens a new window where you can select the achievement and the team.
  - Requires **team_read**, **performance** roles or higher.
- **Delete Achievement**: Lets you remove an achievement from the team’s record. This option is available inline next to each achievement.
  - Requires **team_read**, **performance** roles or higher.

### Contracts Actions
- **View Contract and Payment**: Allows you to view the team’s contract and payment details.
  - Requires **user_read_basic**, **team_read**, **financial_read** roles or higher.
- **Create Contract for Team**: Lets you create a new contract for the team. This option opens a new window where you can enter the contract details.
  - Requires **user_read_basic**, **team_read**, **financial** roles or higher.
- **Delete Contract**: Lets you delete an existing contract for the team. This option is available inline next to the contract details.
  - Requires **user_read_basic**, **team_read**, **financial_admin** roles or higher.

## Other Important Information

N/A