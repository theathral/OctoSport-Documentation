# Achievement Form and Actions

The Achievement form is used for recording, updating, and managing achievements related to events, teams, and users. Users can interact with the form to enter or modify details, including status, approvals, and assigned recipients.

## Navigation (TBD)

Steps to locate this page:

- Navigate to the **Achievements** section in the main menu.
- Select the **Achievement Form** option from the available list.

## Achievement Form

### Fields & Functions

- **Id** (read-only): A unique identifier for each achievement record.
- **Name**: The name or title of the achievement record.
- **Description**: Additional notes related to the achievement.
- **Status** (read-only): A dropdown menu to select the current status of the achievement. More at: [Achievement Record Lifecycle](#achievement-record-lifecycle).
- **Team or User** (required): Reference field linking to the user or team that the achievement is about.
- **Approved by** (read-only): Reference field linking to the user who approved the achievement.
- **Date** (required): Date field capturing the achievement's date.

[IMAGE]

## Achievement Record Lifecycle

The achievement record progresses through the following stages:

- **Draft**: The achievement is still being edited.
- **Pending Approval**: The achievement has been submitted for review but not yet approved.
- **Approved**: The achievement has been accepted.
- **Rejected**: The achievement has been rejected.
- **Cancelled**: The achievement record is no longer relevant or was created in error.

[IMAGE]

## Action Buttons

- **Save Achievement**: Creates or updates an achievement record.
- **Request Approval**: Marks an achievement ready to be approved.
    - Available only if the achievement status is **Draft**.
- **Approve Achievement**: Marks an achievement record approved.
    - Available only if the achievement status is **Pending Approval**.
- **Reject Achievement**: Marks an achievement record rejected.
    - Available only if the achievement status is **Pending Approval**.
- **Cancel Achievement**: Marks an achievement record as cancelled.
    - Available only on existing records, not in **Cancelled** status.
- **Delete Achievement**: Deletes an achievement record.
    - Available only on existing records.

## Required Roles

Please refer to the [Role Hierarchy section](system-roles) for details about role hierarchy. Users with higher roles can perform actions that require lower roles.

- **Retrieve Record**:
    - Requires `internal_user` role, if status is **Approved** and achievement is associated to that user directly or indirectly through **Team or User** field.
    - Requires `achievement_approver` role, if status is **Request Approval**.
    - Requires `performance_read` role or higher.
- **Create Record**: Requires `achievement_create` role or `performance` role or higher.
- **Update Record**:
    - Requires `achievement_create` role, if status is **Draft** and achievement has been created by that user.
    - Requires `performance` role or higher, if status is **Draft** or **Pending Approval**.
    - Requires `performance_admin` role or higher, if status is **Approved**, **Rejected**, or **Cancelled**.
- **Approve or Reject Record**: Requires `achievement_approver` role or `performance` role or higher.
- **Delete Record**: Requires `performance_admin` role or higher.
- **Status field**: Editable for `performance_admin` role or higher.

## Other Important Information

N/A