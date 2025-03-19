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
- **Player** (required): Reference field linking the player having the injury.
- **Doctor**: Reference field linking to a doctor overlooking the injury (filtered to users with the `doctor` role).
- **Injury Date**: The date when the injury occurred.
- **Estimated Rehabilitation Date**: The expected recovery completion date.
- **Actual Rehabilitation Date**: The actual date when the player recovered.

[IMAGE]

## Injury Record Lifecycle

The injury record progresses through the following stages:

- **In Recovery**: The player is actively recovering from the injury.
- **Setback in Recovery**: A complication has occurred, delaying the recovery process.
- **Fully Recovered**: The player has successfully recovered and is fit to play.
- **Permanent Disability**: The injury has resulted in a long-term or permanent condition.
- **Cancelled**: The injury record is no longer relevant or was created in error.

[IMAGE]

## Action Buttons

- **Save Injury**: Creates or updates an injury record.
- **Delete Injury**: Deletes an injury record.
    - Available only on existing records.

## Required Roles

Please refer to the [Role Hierarchy section](system-roles) for details about role hierarchy. Users with higher roles can perform actions that require lower roles.

- **Retrieve Record**: Requires `player_read` role or higher.
- **Create Record**: Requires `player_read` + `doctor` roles or `player` role or higher.
- **Update Record**:
    - Requires `internal_user` role, if injury is associated to that user directly through **Player** field.
    - Requires `player_read` + `doctor` roles or `player` role or higher, if status is **In Recovery** or **Setback In Recovery**
    - Requires `player_admin` role or higher, if status is **Fully Recovered**, **Permanent Disability**, or **Cancelled**.
- **Delete Record**: Requires `player_admin` role or higher.

## Other Important Information

N/A