# Role Form and Actions (TBD)

## Purpose
Describe the purpose of the form and how users interact with it.

## Fields & Functions
- **Field Name 1**: Description of what this field does.
- **Field Name 2**: Description of another field.
- ...

## Step-by-Step Guide
1. Navigate to the form.
2. Fill in the required fields.
3. Click the submit button.
4. Verify confirmation message.

## Expected Results
- Successful submission of data.
- Confirmation message displayed.
- Data stored and available for retrieval.

## Additional Notes
- Validation rules (e.g., required fields, character limits).
- Dependencies with other modules.

(system-roles)=
## System Roles
(to be reviewed)
### Section-Specific Roles

For each section in the system (e.g., Team, Player, etc.), we have three levels of roles:

- **{section}_admin**: This role has the highest level of access for the section. Users with this role can **view**, **modify**, and **delete** records in the section. They have full administrative rights within the section.
  
- **{section}**: Users with this role can **view** and **modify** records within the section but cannot **delete** them. This role is intended for users who need to manage and update records but don't have full administrative control.

- **{section}_read**: This role is the most restrictive. Users can only **view** records within the section. They cannot make any changes to the data and have a read-only view of the section's content.

**Hierarchy Overview for Section-Specific Roles**:
- `{section}_admin` > `{section}` > `{section}_read`
- A higher role inherits all the permissions of the lower roles. For example, a user with the `{section}_admin` role can perform all actions available to users with the `{section}` and `{section}_read` roles.

### Specific roles

### System-Wide Admin Roles

In addition to section-specific roles, there are two **admin roles** that have system-wide access:

- **admin**: This role has the highest level of access across the entire system. Users with the `admin` role can **view**, **modify**, and **delete** any records in the system, regardless of the section. Admins have full control over all areas of the system.

- **admin_read**: This role provides **view-only access** to everything in the system. Users with this role can see all records across sections but cannot make any modifications or deletions. Admin_read users can monitor and review the system but have no write permissions.

**Hierarchy Overview for Admin Roles**:
- `admin` > `admin_read`
- The `admin` role includes all the permissions of the `admin_read` role, so admins can perform any action, while admin_read users can only view records without altering them.

### Role Hierarchy Summary
- **Section Roles**: `{section}_admin` > `{section}` > `{section}_read`
- **System Admin Roles**: `admin` > `admin_read`
- A higher role in both section-specific and system-wide roles automatically inherits the permissions of lower roles.


