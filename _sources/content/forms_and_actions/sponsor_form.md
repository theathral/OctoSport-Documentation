# Sponsor Form and Actions

The Sponsor form is used for creating, updating, and managing sponsors within the system. Users can interact with the form to enter or modify sponsor details, including name, type, contact person, and relevant contact information. The form also provides functions for managing sponsorship contracts and tracking pending payments.

```{admonition} Sponsor vs Contracts
:class: tip, dropdown

Sponsors are entities that provide financial or material support to teams or events. Contracts define the formal agreements between sponsors and the organization.
```

## Navigation (TBD)

```{warning} Under Construction
```

Steps to locate this page:

- Navigate to the **Sponsors** section in the main menu.
- Select the **Sponsor Form** option from the available list.

## Fields & Functions

- **Id** (read-only): A unique identifier for each sponsor record.
- **Name** (required): The official name of the sponsor.
- **Description**: A brief description of the sponsor.
- **Active**: Checkbox indicating whether the sponsor is active.
- **Sponsor Type** (required): A dropdown to select the sponsor type. This classification helps in structuring sponsorship agreements and financial interactions. Options include:
    - **Company**: A business entity sponsoring the sports club, typically providing financial support in exchange for brand visibility and advertising opportunities.
    - **Individual**: A private person who offers financial support or resources to the club, often for personal interest or to help the community.
    - **Organization**: A non-profit, sports federation, or similar group that contributes sponsorship for supporting sports programs or community initiatives.
- **Contact Person**: Reference field linking to the contact person of the sponsor. Only users with the `sponsor` role appear here.
- **Sponsor Email**: The email address of the sponsor.
- **Sponsor Phone**: The phone number of the sponsor.
- **Sponsor Address**: The physical address of the sponsor.

[IMAGE]

## Related Lists

Tabs that point to other sections related to the sponsor:

- **[Contracts](./contract_form.md)**: View and manage contracts related to the sponsor.
  [IMAGE]

- **[Payments](./payment_form.md)**: Track outstanding sponsorship-related payments for the sponsor.
  [IMAGE]

## Action Buttons

### Main Buttons

- **Save Sponsor**: Creates or updates the sponsor record.
- **Delete Sponsor**: Deletes the sponsor record.
  - Available only on existing records.

### Contracts Buttons

- **View Tab**: View the list of sponsors associated with the sponsor.
- **Create Contract**: Opens a new window to the contract record with populated the Sponsor field value where contract details can be entered.
- **Delete Contract**: Deletes the contract (inline button).

### Pending Payments Buttons

- **View Tab**: View the list of pending payments. Remove the filter to see all the payments of the sponsor.

## Required Roles

Please refer to the [Role Hierarchy section](system-roles) for details about role hierarchy. Users with higher roles can perform actions that require lower roles.

- **Retrieve Record**: Requires `financial_read` role or higher.
- **Create Record**: Requires `financial` role or higher.
- **Update Record**: Requires `financial` role or higher.
- **Delete Record**: Requires `financial_admin` role or higher.
- _Contracts tab_:
  - **Retrieve Record**: Requires `financial_read` role or higher.
  - **Create Record**: Requires `financial` role or higher.
  - **Update Record**: Does not exist.
  - **Delete Record**: Requires `financial_admin` role or higher.
- _Pending Payments tab_:
  - **Retrieve Record**: Requires `financial_read` role or higher.
  - **Create Record**: Does not exist.
  - **Update Record**: Does not exist.
  - **Delete Record**: Does not exist.

## Other Important Information

N/A
