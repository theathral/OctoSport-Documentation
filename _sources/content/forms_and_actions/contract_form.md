# Contract Form and Actions

The Contract form is used for creating, updating, and managing contracts related to player memberships, sponsorships, compensations, and other financial agreements. Users can interact with the form to enter or modify contract details, including contract type, status, financial terms, and related entities such as users, teams, and sponsors.

```{admonition} Contract Types
:class: tip, dropdown

Contracts in the system can represent various financial agreements such as player memberships, sponsorships, employee compensations, service agreements, and other revenue-generating deals.
```

## Navigation (TBD)

```{warning} Under Construction
```

Steps to locate this page:

- Navigate to the **Contracts** section in the main menu.
- Select the **Contract Form** option from the available list.

## Fields & Functions

- **Id** (read-only): A unique identifier for each contract record.
- **Name** (required): The contract title or reference name.
- **Type** (required): A dropdown menu selecting the type of contract. Options:
    - **Player Membership**: A contract defining a player's membership agreement with a team or club.
    - **Sponsorship**: A contract related to sponsorship agreements between a sponsor and the team or club.
    - **Employee/Player Compensation**: A contract covering salary and financial compensation for staff or players.
    - **Service Agreement**: A contract related to the provision of a service to or from the club.
    - **Other Revenue**: A contract for miscellaneous revenue sources not covered in the predefined categories.
- **Status** (read-only): A dropdown menu selecting the contract's current status. More at: [Contract Record Lifecycle](#contract-record-lifecycle).
    - Requires `financial_admin` or `admin` role to directly edit the field.
- **User**: Reference field linking a user to the contract.
- **Team**: Reference field linking a team to the contract.
- **Sponsor**: Reference field linking a sponsor to the contract. Required if the contract type is **Sponsorship**.
- **Schedule**: Reference field linking a series of events to the contract.
- **Contract Start Date** (required): The start date of the contract.
- **Contract End Date**: The end date of the contract.
- **Contract/Payment Terms** (required): A dropdown menu selecting the payment frequency. Options include:
    - **Lump Sum**: A one-time full payment.
    - **Installments**: Payments divided into multiple installments.
    - **Weekly**: Payments made every week.
    - **Monthly**: Payments made on a monthly basis.
    - **Quarterly**: Payments made every three months.
    - **Yearly**: Payments made once per year.
    - **Other**: A custom payment term not covered by predefined options.
- **Total Contract Value** (required): The total monetary value of the contract.
- **Amount Due** (read-only): The remaining balance to be paid, calculated from contract value minus payments made.
- **Amount Paid** (read-only): The total amount already paid, calculated from recorded payments.
- **Comments**: Additional notes or details about the contract.

  [IMAGE]

(contract-record-lifecycle)=

## Contract Record Lifecycle

The contract record progresses through the following stages, with specific edit permissions based on user roles:

- **Draft**: The contract is being created and has not yet been signed.
- **Signed**: The contract has been signed by all parties but is not yet active.
- **Active**: The contract is currently in effect.
    - This status triggers automatically when the contract is in **Signed** status and the current date matches the contract's start date.
- **Suspended**: The contract is temporarily inactive.
- **Expired**: The contract has reached its end date and is no longer active.
    - This status triggers automatically when the contract is in **Active** status and the current date matches the contract's end date.
    - Requires `financial_admin` or `admin` role to edit the record after the status is saved to this value.
- **Terminated**: The contract has been ended before its natural expiration.
    - Requires `financial_admin` or `admin` role to edit the record after the status is saved to this value.
- **Canceled**: The contract has been cancelled before activation.
    - Requires `financial_admin` or `admin` role to edit the record after the status is saved to this value.

## Related Lists

Tabs that point to other sections related to the contract:

- **[Payments](./payment_form.md)**: View and manage payments associated with the contract.
  [IMAGE]

## Actions & Required Roles

```{admonition} Explanation of Roles
:class: tip, dropdown

Please refer to the [Role Hierarchy section](system-roles) for details about role hierarchy. Users with higher roles can perform actions that require lower roles.
```

### Main Actions

- **View Contract**: Allows you to view the contract details.
    - Requires `financial_read` role or higher.
- **Save Contract (New Record)**: Allows you to create a new contract record.
    - Requires `financial` role or higher.
- **Save Contract (Existing Record)**: Allows you to modify an existing contract record.
    - Requires `financial` role or higher, unless specified otherwise in the [Contract Record Lifecycle](#contract-record-lifecycle).
- **Sign Contract**: Marks the contract as signed.
    - Available only if the contract status is **Draft**.
    - Requires `financial` role or higher.
- **Suspend Contract**: Marks an active contract as suspend.
    - Available only if the contract status is **Active**.
    - Requires `financial` role or higher.
- **Unsuspend Contract**: Marks a suspended contract as active.
    - Available only if the contract status is **Suspended**.
    - Requires `financial` role or higher.
- **Terminate Contract**: Marks an active contract as terminate.
    - Available only if the contract status is **Active**.
    - Requires `financial` role or higher.
- **Cancel Contract**: Marks a draft contract as cancel.
    - Available only if the contract status is **Draft**.
    - Requires `financial` role or higher.
- **Delete Contract**: Allows you to delete an existing contract record.
    - Requires `financial_admin` role or higher.

### Payments Actions

- **View Payments**: Allows you to view the payments linked to the contract.
    - Requires `financial_read` role or higher.
- **Create Single Payment**: Allows you to create a new payment record.
    - Requires `financial` role or higher.
- **Create Bulk Payments**: Allows creating multiple payments at once.
    - **How**: This option opens a new window to the payment record with populated the Contract field value where you can enter the contract details.
    - Requires `financial` role or higher.
- **Delete Payment**: Allows deleting an existing payment.
    - **How**: This action is available inline next to each record.
    - Requires `financial_admin` role or higher.

## Other Important Information

N/A
