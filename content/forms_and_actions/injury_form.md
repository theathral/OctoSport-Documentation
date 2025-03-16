# Injury Form and Actions

The Injury form is used for recording, updating, and managing injuries associated with players. Users can interact with the form to enter or modify injury details, including status, assigned doctor, and rehabilitation timelines.

## Navigation (TBD)
Steps to locate this page:
- Navigate to the **Injuries** section in the main menu.
- Select the **Injury Form** option from the available list.

## Fields & Functions
- **Id** (read-only): A unique identifier for each injury record.
- **Name**: The name or title of the injury record.
- **Comments**: Additional notes related to the injury.
- **Status**: A dropdown menu to select the current recovery status of the injury. Options include:
    - In Recovery
    - Setback in Recovery
    - Fully Recovered
    - Permanent Disability
    - Cancelled
- **Player**: Reference field linking the injury to a specific player.
- **Doctor**: Reference field linking to a doctor (filtered to users with the doctor role).
- **Injury Date**: The date when the injury occurred.
- **Estimated Rehabilitation Date**: The expected recovery completion date.
- **Actual Rehabilitation Date**: The actual date when the player recovered.

## Actions & Required Roles

```{admonition} Explanation of Roles
:class: tip, dropdown

Please refer to the [Role Hierarchy section](system-roles) for details about role hierarchy. Users with higher roles can perform actions that require lower roles.
```

### Main Actions
- **View Injury**: Allows users to view the details of an injury.
    - Requires **player_read** role or higher.
- **Save Injury (New Record)**: Saves the injury details when creating a new injury record.
    - Requires **player** role or **player_read** + **doctor** roles.
- **Save Injury (Existing Record)**: Saves any changes made to an existing injury record.
    - Requires **player** role or **player_read** + **doctor** roles.
- **Delete Injury**: Allows the deletion of an injury record.
    - Requires **player_admin** role or higher.

## Other Important Information

N/A