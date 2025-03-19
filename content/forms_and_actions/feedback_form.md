# Feedback Form and Actions

The Feedback form is used for recording, updating, and managing feedback related to events, teams, and users. Users can interact with the form to enter or modify feedback details, including status, rating, and assigned recipients.

## Navigation (TBD)

Steps to locate this page:

- Navigate to the **Feedback** section in the main menu.
- Select the **Feedback Form** option from the available list.

## Fields & Functions

- **Id** (read-only): A unique identifier for each feedback record.
- **Name** (required): The name or title of the feedback record.
- **Description**: Full text description of given feedback.
- **Status** (read-only): A dropdown menu indicating the current feedback status. More at: [Feedback Record Lifecycle](#feedback-record-lifecycle).
- **Given by** (read-only): Shows the name of the person who provided the feedback. The field is populated by the user created the record.
- **Event**: Reference field linking to a specific event related to the feedback.
- **Team or User**: Reference field linking to the user or team that the feedback is about.
- **Rating**: A numerical rating with the following options:
    - 1 - Below Expectation
    - 2 - Developing
    - 3 - Meets Expectations
    - 4 - Exceeds Expectations
    - 5 - Exceptional

[IMAGE]

## Feedback Record Lifecycle

The feedback record progresses through the following stages:

- **Draft**: The feedback is still being edited.
- **Published**: The feedback is publicly available.
- **Hidden Published**: The feedback is published but hidden from the users associated with.
- **Cancelled**: The feedback record is no longer relevant or was created in error.

[IMAGE]

## Action Buttons

- **Save Feedback**: Creates or updates a feedback record.
- **Publish Feedback**: Marks a feedback record as published.
    - Available only if the feedback status is **Draft**.
- **Hidden Publish Feedback**: Marks a feedback record as published while keeping it hidden from the associated users
    - Available only if the feedback status is **Draft**.
- **Cancel Feedback**: Marks a feedback record as cancelled.
    - Available only on existing records, not in **Cancelled** status.
- **Delete Feedback**: Deletes a feedback record.
    - Available only on existing records.

## Required Roles

Please refer to the [Role Hierarchy section](system-roles) for details about role hierarchy. Users with higher roles can perform actions that require lower roles.

- **Retrieve Record**:
    - Requires `internal_user` role, if status is **Published** and feedback is associated to that user directly or indirectly through **Team or User** field.
    - Requires `feedback_create` role, if feedback has been created by that user.
    - Requires `performance_read` role or higher.
- **Create Record**: Requires `feedback_create` role or `performance` role or higher.
- **Update Record**:
    - Requires `feedback_create` role, if status is **Draft** and feedback has been created by that user.
    - Requires `performance` role or higher, if status is **Draft**.
    - Requires `performance_admin` role or higher, if status is **Published**, **Hidden Published**, or **Cancelled**.
- **Delete Record**: Requires `performance_admin` role or higher.
- **Status field**: Editable for `performance_admin` role or higher.

## Other Important Information

N/A