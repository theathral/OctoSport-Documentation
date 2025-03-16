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
- **Status** (read-only): A dropdown menu indicating the achievement's current status. Options include:
    - Draft
    - Pending Approval
    - Approved
    - Rejected
    - Cancelled
- **Team / User**: M2M table allowing selection between a team or individual user (if changed, previous record is deleted).
- **Approved by**: Reference field (read-only) indicating the user who approved the achievement.
- **Date**: Date field capturing the achievement's date.

### Actions & Required Roles

#### Main Actions
- **View Achievement**: Allows users to view the details of an achievement.
    - Requires **performance_read** role or higher.
- **Save Achievement (New Record)**: Saves the achievement details when creating a new achievement record.
    - Requires **performance** role or **achievement_create** role.
    - If **achievement_create**, then Status = Pending Approval.
- **Save Achievement (Existing Record)**: Saves any changes made to an existing achievement record.
    - Requires **performance** role or **achievement_create** role.
    - If user has **achievement_create** role, they can only modify achievements where **Created by** = {User}, and they cannot update the status.
- **Request Approval**: Submits an achievement for approval.
    - Requires **performance** role or **achievement_create** role.
    - Must be in **Draft** status.
    - If user has **achievement_create** role, they can only modify achievements where **Created by** = {User}.
- **Approve Achievement**: Approves an achievement record.
    - Requires **performance** role or **achievement_approver** role.
    - Must be in **Pending Approval** status.
- **Reject Achievement**: Rejects an achievement record.
    - Requires **performance** role or **achievement_approver** role.
    - Must be in **Pending Approval** status.
- **Cancel Achievement**: Cancels an achievement record.
    - Requires **performance** role or **achievement_create** role.
    - If user has **achievement_create** role, they can only modify achievements where **Created by** = {User}.
- **Delete Achievement**: Allows the deletion of an achievement record.
    - Requires **performance_admin** role or higher.
    - Deletes M2M Users and Teams associated with the achievement.

## Other Important Information

N/A