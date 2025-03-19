# Group Form and Actions

The Group form is used for creating, updating, and managing groups within the system. Users can interact with the form to enter or modify group details, including name, description, and active status. The form also includes functions for managing users and roles associated with the group.

```{admonition} Teams vs Groups
:class: tip, dropdown

Groups and Teams are distinct entities within the system. Groups are used to control the visibility of pages and actions, while Teams are designed to organize players and staff for operational purposes.
```

## Navigation (TBD)

```{warning} Under Construction
```

Steps to locate this page:

- Navigate to the **Groups** section in the main menu.
- Select the **Group Form** option from the available list.

## Fields & Functions

- **Id** (read-only): A unique identifier for each group.
- **Name** (required): The official name of the group.
- **Description**: A brief description of the group.
- **Active**: Checkbox indicating whether the group is currently active.

[IMAGE]

## Related Lists

Tabs that point to other sections related to the group:

- **[Users](./user_form.md)**: View and manage users assigned to the group.
  [IMAGE]

- **[Roles](./role_form.md)**: View and manage roles associated with the group.
  [IMAGE]

## Action Buttons

### Main Buttons

- **Save Group**: Creates or updates a group record.
- **Delete Group**: Deletes an existing group.
    - Available only on existing records.

### Users Tab Buttons

- **View Tab**: View the list of users associated with the group.
- **Add User to Group**: Shows a pop-up window to add a user to the group.
- **Remove User from Group**: Removes a user from the group (inline button).

### Roles Tab Buttons

- **View Tab**: View the list of roles assigned to the group.
- **Add Role to Group**: Shows a pop-up window to add a role to the group.
- **Remove Role from Group**: Removes a role from the group (inline button).

## Required Roles

Please refer to the [Role Hierarchy section](system-roles) for details about role hierarchy. Users with higher roles can perform actions that require lower roles.

- **Retrieve Record**: Requires `admin_read` role or higher.
- **Create Record**: Requires `admin` role or higher.
- **Update Record**: Requires `admin` role or higher.
- **Delete Record**: Requires `admin` role or higher.
- _Users Tab_:
    - **Retrieve Record**: Requires `admin_read` role or higher.
    - **Create Record**: Requires `admin` role or higher.
    - **Update Record**: Does not exist.
    - **Delete Record**: Requires `admin` role or higher.
- _Roles Tab_:
    - **Retrieve Record**: Requires `admin_read` role or higher.
    - **Create Record**: Requires `admin` role or higher.
    - **Update Record**: Does not exist.
    - **Delete Record**: Requires `admin` role or higher.

## Other Important Information

N/A