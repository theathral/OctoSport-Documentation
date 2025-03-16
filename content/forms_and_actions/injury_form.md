# Injury Form and Actions

The Injury form is used for recording, updating, and managing injuries associated with players. Users can interact with the form to enter or modify injury details, including status, assigned doctor, and rehabilitation timelines.

## Navigation (TBD)

```{warning} Under Construction
```

Steps to locate this page:

- Navigate to the **Injuries** section in the main menu.
- Select the **Injury Form** option from the available list.

## Fields & Functions

- **Id** (read-only): A unique identifier for each injury record.
- **Name** (required): The name or title of the injury record.
- **Comments**: Additional notes related to the injury.
- **Status** (required): A dropdown menu to select the current recovery status of the injury. More at: [Injury Record Lifecycle](#injury-record-lifecycle).
- **Player**: Reference field linking the player having the injury.
- **Doctor**: Reference field linking to a doctor overlooking the injury (filtered to users with the doctor role).
- **Injury Date**: The date when the injury occurred.
- **Estimated Rehabilitation Date**: The expected recovery completion date.
- **Actual Rehabilitation Date**: The actual date when the player recovered.

[IMAGE]

## Injury Record Lifecycle

The injury record progresses through the following stages, with specific edit permissions based on user roles:

- **In Recovery**: The player is actively recovering from the injury
- **Setback in Recovery**: A complication has occurred, delaying the recovery process.
- **Fully Recovered**: The player has successfully recovered and is fit to play
    - Requires `player_admin` or `admin` role to edit the record after the status is saved to this value.
- **Permanent Disability**: The injury has resulted in a long-term or permanent condition
    - Requires `player_admin` or `admin` role to edit the record after the status is saved to this value.
- **Cancelled**: The injury record is no longer relevant or was created in error
    - Requires `player_admin` or `admin` role to edit the record after the status is saved to this value.

## Actions & Required Roles

```{admonition} Explanation of Roles
:class: tip, dropdown

Please refer to the [Role Hierarchy section](system-roles) for details about role hierarchy. Users with higher roles can perform actions that require lower roles.
```

### Main Actions

- **View Injury**: Allows users to view the details of an injury.
    - Requires `player_read` role or higher.
- **Save Injury (New Record)**: Allows you to create a new injury record.
    - Requires `player_read` + `doctor` roles or `player` role or higher.
- **Save Injury (Existing Record)**: Allows you to modify the details of an existing injury record.
    - Requires `player_read` + `doctor` roles or `player` role or higher, unless specified otherwise in the [Injury Record Lifecycle](#injury-record-lifecycle).
- **Delete Injury**: Allows the deletion of an injury record.
    - Requires `player_admin` role or higher.

## Other Important Information

N/A