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

## Actions & Required Roles

```{admonition} Explanation of Roles
:class: seealso

Please refer to the [Role Hierarchy section](system-roles) for details about role hierarchy. Users with higher roles can perform actions that require lower roles.
```

### Main Actions

- **View Group**: Allows you to view the group's details.
    - Requires `admin_read` or `admin` role.
- **Save Group (New Record)**: Allows you to create a new group record.
    - Requires `admin` role.
- **Save Group (Existing Record)**: Allows you to modify the details of an existing group record.
    - Requires `admin` role.
- **Delete Group**: Allows you to delete a group.
    - Requires `admin` role.

### Users Actions

- **View Users**: Allows you to view the list of users associated with the group.
    - Requires `admin_read` or `admin` role.
- **Add User to Group**: Allows you to add a new user to the group.
    - **How**: This action will open a pop-up window to add a user.
    - Requires `admin` role.
- **Remove User from Group**: Allows you to remove a user from the group.
    - **How**: This action is available inline next to each record.
    - Requires `admin` role.

### Roles Actions

- **View Roles**: Allows you to see the list of roles assigned to the group.
    - Requires `admin_read` or `admin` role.
- **Add Role to Group**: Allows you to add a new role to the group.
    - **How**: This action will open a pop-up window to add a role.
    - Requires `admin` role.
- **Remove Role from Group**: Allows you to remove a role from the group.
    - **How**: This action is available inline next to each record.
    - Requires `admin` role.

## Other Important Information

N/A