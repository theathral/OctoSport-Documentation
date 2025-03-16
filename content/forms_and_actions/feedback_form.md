# Feedback Form and Actions

The Feedback form is used for recording, updating, and managing feedback related to events, teams, and users. Users can interact with the form to enter or modify feedback details, including status, rating, and assigned recipients.

## Navigation (TBD)
Steps to locate this page:
- Navigate to the **Feedback** section in the main menu.
- Select the **Feedback Form** option from the available list.

## Fields & Functions
- **Id** (read-only): A unique identifier for each feedback record.
- **Name**: The name or title of the feedback record.
- **Description**: Additional notes related to the feedback.
- **Status** (read-only): A dropdown menu indicating the feedback's current status. Options include:
    - Draft
    - Published
    - Hidden Published
    - Cancelled
- **Given by**: Reference field (read-only) indicating the user who provided the feedback (logged-in user).
- **Event**: Reference field linking the feedback to a specific event.
- **Team / User**: M2M table allowing selection between a team or individual user (if changed, previous record is deleted).
- **Rating**: A numerical rating with the following options:
    - 1 - Below Expectation
    - 2 - Developing
    - 3 - Meets Expectations
    - 4 - Exceeds Expectations
    - 5 - Exceptional

## Actions & Required Roles

```{admonition} Explanation of Roles
:class: tip, dropdown

Please refer to the [Role Hierarchy section](system-roles) for details about role hierarchy. Users with higher roles can perform actions that require lower roles.
```

### Main Actions
- **View Feedback**: Allows users to view the details of feedback.
    - Requires **performance_read** role or higher.
- **Save Feedback (New Record)**: Saves the feedback details when creating a new feedback record.
    - Requires **performance** role or **feedback_create** role.
- **Save Feedback (Existing Record)**: Saves any changes made to an existing feedback record.
    - Requires **performance** role or **feedback_create** role.
    - If user has **feedback_create** role, they can only modify feedback where **Given by** = {User}.
- **Publish Feedback**: Publishes a feedback record.
    - Requires **performance** role or **feedback_create** role.
    - Must be in **Draft** status.
    - If user has **feedback_create** role, they can only modify feedback where **Given by** = {User}.
- **Hidden Publish Feedback**: Publishes feedback in a hidden state.
    - Requires **performance** role or **feedback_create** role.
    - Must be in **Draft** status.
    - If user has **feedback_create** role, they can only modify feedback where **Given by** = {User}.
- **Cancel Feedback**: Cancels a feedback record.
    - Requires **performance** role or **feedback_create** role.
    - Must be in **Draft** status.
    - If user has **feedback_create** role, they can only modify feedback where **Given by** = {User}.
- **Delete Feedback**: Allows the deletion of a feedback record.
    - Requires **performance_admin** role or higher.
    - Deletes M2M Users and Teams associated with the feedback.

## Other Important Information

N/A