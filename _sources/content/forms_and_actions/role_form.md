# Role Form and Actions

The Role form is used for creating, updating, and managing roles within the system. Users can interact with the form to view role details, including name, description, and active status. The form also includes functions for assigning users and associating roles with groups.

```{admonition} Should I assign Roles to Groups or Users?
:class: tip, dropdown

The best practice is to assign Roles to Groups rather than directly to Users, and then assign Users to Groups. This approach simplifies management by allowing you to control permissions at the group level, ensuring consistency across users with similar roles. It also reduces administrative overhead and provides flexibility, as users can be easily reassigned to different groups without the need to adjust individual permissions.
```

## Navigation (TBD)

```{warning} Under Construction
```

Steps to locate this page:

- Navigate to the **Roles** section in the main menu.
- Select the **Role Form** option from the available list.

## Fields & Functions

- **Id** (read-only): A unique identifier for each role.
- **Name** (required): The official name of the role.
- **Description**: A brief description of the role.
- **Active**: Checkbox indicating whether the role is currently active.

[IMAGE]

## Related Lists

Tabs that point to other sections related to the role:

- **[Users](./user_form.md)**: View and manage users assigned to the role.
  [IMAGE]

- **[Groups](./group_form.md)**: View and manage groups associated with the role.
  [IMAGE]


## Actions & Required Roles

```{admonition} Explanation of Roles
:class: tip, dropdown

Please refer to the [Role Hierarchy section](system-roles) for details about role hierarchy. Users with higher roles can perform actions that require lower roles.
```

### Main Actions

- **View Role**: Allows you to view the role's details.
    - Requires `admin_read` or `admin` role.

### Users Actions

- **View Users**: Allows you to view the list of users associated with the role.
    - Requires `admin_read` or `admin` role.
- **Add User to Role**: Lets you assign a user to the role. This action will open a pop-up window to add a user.
    - **How**: This action will open a pop-up window to add a user.
    - Requires `admin` role.
- **Remove User from Role**: Lets you remove a user from the role. This action is available inline next to each user.
    - **How**: This action is available inline next to each record.
    - Requires `admin` role.

### Groups Actions

- **View Groups**: Allows you to view the list of groups associated with the role.
    - Requires `admin_read` or `admin` role.
- **Add Role to Group**: Lets you assign the role to a group. This action will open a pop-up window to add a role.
    - Requires `admin` role.
    - **How**: This action will open a pop-up window to add a group.
- **Remove Role from Group**: Lets you remove a role from a group. This action is available inline next to each group.
    - **How**: This action is available inline next to each record.
    - Requires `admin` role.

(system-roles)=

## System Roles

The system defines three main types of roles: **Section-Specific**, **Special**, and **Admin Roles**. Each type serves a unique purpose and is critical for effective permission management across the platform.

### Section-Specific Roles

For each section in the system (e.g., Team, Player, Employee, etc.), there are three levels of roles:

- **{section}_admin**: This role provides the highest level of access within a section. Users with this role can **view**, **modify**, and **delete** records in the section. They have full administrative rights within the section.

- **{section}**: Users with this role can **view** and **modify** records within the section but cannot **delete** them. This role is designed for users who need to update records but do not require full administrative control.

- **{section}_read**: This role is the most restrictive. Users can only **view** records within the section, with no permissions to make any modifications. It provides a read-only view of the section's content.

**Hierarchy Overview for Section-Specific Roles**:

- `{section}_admin` > `{section}` > `{section}_read`
- Higher roles inherit all the permissions of the lower roles. For example, a user with the `{section}_admin` role has the same permissions as a user with the `{section}` and `{section}_read` roles, plus additional administrative privileges.

### Special roles

Special roles are used for specific purposes or unique conditions within the system. These roles are defined explicitly in field details or the action section of the form when required. They are not part of the general role hierarchy.

### System-Wide Admin Roles

In addition to section-specific and special roles, there are two **admin roles** that have system-wide access:

- `admin`:  This role has full access across the entire system. Users with this role can **view**, **modify**, and **delete** any records, regardless of the section. Admins have unrestricted control over all areas of the platform.

- `admin_read`: This role grants **view-only** access across the entire system. Users with this role can see all records in the system but cannot make any modifications or deletions. They can monitor the system but have no write permissions.

**Hierarchy Overview for Admin Roles**:

- `admin` > `admin_read`
- The `admin` role inherits all permissions of the `admin_read` role, meaning `admins` can perform all actions, while
  `admin_read` users are limited to viewing records only.

### Role Hierarchy Summary

- **Section Roles**: `{section}_admin` > `{section}` > `{section}_read`
- **System Admin Roles**: `admin` > `admin_read`
- Higher roles in both section-specific and system-wide categories automatically inherit the permissions of lower roles.

### List of roles

For **Admin Role Roles**:

- `admin`: Complete system access, including the ability to view, modify, and delete all records and settings.
- `admin_read`: View-only access to all records across all sections. Modifications and deletions are not permitted.
- `internal_user`: Restricted access to the platform.
  ```{note}
  All users with access to the platform can view their own record and associated details. The Form and Actions section outlines the specific permissions for users with the `internal_user` role, detailing what they can view and modify.
  ```

For **User and Group Roles**:

- `user_n_group`: Basic user permissions.
- `user_n_group_read`: Read-only view of user and group data.
- `user_read_basic`: View full name, used only to see basic details.

For **Player and Injury Roles**:

- `player_admin`: Full access for managing players.
- `player`: Basic player management.
- `player_read`: Read-only access to player data.
  ```{admonition} Inherits **user_read** role
  :class: note, dropdown
  All users with either of the roles, they inherit the `user_read` role.
  ```

For **Employee Roles**:

- `employee_admin`: Full access for managing employees.
- `employee`: Basic employee management.
- `employee_read`: Read-only access to employee data.
  ```{admonition} Inherits **user_read** role
  :class: note, dropdown
  All users with either of the roles, they inherit the `user_read` role.
  ```

For **Team Roles**:

- `team_admin`: Full access for managing teams.
- `team`: Basic team management.
- `team_read`: Read-only access to team data.
  ```{admonition} Inherits **user_read_basic** role
  :class: note, dropdown
  All users with either of the roles, they inherit the `user_read_basic` role.
  ```

For **Schedule, Event, Result, and Attendance Roles**:

- `event_admin`: Full access to manage events.
- `event`: Basic event management.
- `event_read`: Read-only access to event data.
  ```{admonition} Inherits **user_read_basic** and **team_read** role
  :class: note, dropdown
  All users with either of the roles, they inherit the `user_read_basic` and `team_read` roles.
  ```

For **Feedback, Performance, and Achievement Roles**:

- `performance_admin`: Full access for managing performance, feedback, and achievement data.
- `performance`: Basic performance, feedback, and achievement management.
- `performance_read`: Read-only access to performance, feedback, and achievement data.
  ```{admonition} Inherits **user_read_basic** and **team_read** role
  :class: note, dropdown
  All users with either of the roles, they inherit the `user_read_basic` and `team_read` roles.
  ```

For **Sponsor, Contract, and Payment Roles**:

- `financial_admin`: Full access for managing financial data.
- `financial`: Basic financial management.
- `financial_read`: Read-only access to financial data.
  ```{admonition} Inherits **user_read_basic** and **team_read** role
  :class: note, dropdown
  All users with either of the roles, they inherit the `user_read_basic` and `team_read` roles.
  ```

For **Additional Roles**:

- `doctor`: Role specific to managing medical or injury-related data for players.
- `coach`: Role specific to managing player performance and team strategies.
- `sponsor`: Role specific to managing sponsorship and financial relationships. (TBD) Maybe not after all
- `achievement_create`: Role specific to creating achievements.
- `achievement_approver`: Role specific to approving achievements.
- `feedback_create`: Role specific to creating feedback.
  ```{admonition} Inherits **user_read_basic** and **team_read** role
  :class: note, dropdown
  All users with either of the roles, they inherit the `user_read_basic` and `team_read` roles.
  ```

## Other Important Information

N/A