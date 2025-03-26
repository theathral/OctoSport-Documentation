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

## Contract Record Lifecycle

The contract record progresses through the following stages:

- **Draft**: The contract is being created and has not yet been signed.
- **Signed**: The contract has been signed by all parties but is not yet active.
- **Active**: The contract is currently in effect.
    - This status triggers automatically when the contract is in **Signed** status and the current date matches the contract's start date.
- **Suspended**: The contract is temporarily inactive.
- **Expired**: The contract has reached its end date and is no longer active.
    - This status triggers automatically when the contract is in **Active** status and the current date matches the contract's end date.
- **Terminated**: The contract has been ended before its natural expiration.
    - This status triggers automatically when the contract is in **Suspended** status and the current date matches the contract's end date.
- **Canceled**: The contract has been cancelled before activation.

## Related Lists

Tabs that point to other sections related to the contract:

- **[Payments](./payment_form.md)**: View and manage payments associated with the contract.
  [IMAGE]

## Actions & Required Roles

### Main Actions

- **Save Contract**: Creates or updates the contract record.
- **Sign Contract**: Marks the contract as signed.
    - Available only if the contract status is **Draft**.
- **Suspend Contract**: Marks the contract as suspended.
    - Available only if the contract status is **Active**.
- **Unsuspend Contract**: Marks the contract as active.
    - Available only if the contract status is **Suspended**.
- **Terminate Contract**: Marks the contract as terminated.
    - Available only if the contract status is **Active**.
- **Cancel Contract**: Marks the contract as cancelled.
    - Available only if the contract status is **Draft**.
- **Delete Contract**: Deletes a contract record.
    - Available only on existing records.

### Pending Payments Buttons

- **View Tab**: View the list of pending payments. Remove the filter to see all the payments of the sponsor.
- **Create Payment**: Opens a new window to the payment record with populated the Contract field value where payment details can be entered.
- **Delete Payment**: Deletes a payment (inline button).

## Required Roles

Please refer to the [Role Hierarchy section](system-roles) for details about role hierarchy. Users with higher roles can perform actions that require lower roles.

- **Retrieve Record**: Requires `financial_read` role or higher.
- **Create Record**: Requires `financial` role or higher.
- **Update Record**:
    - Requires `financial` role or higher, if status is **Draft**, **Signed**, or **Suspended**.
    - Requires `financial_admin` role or higher, if status is **Expired**, **Terminated**, or **Canceled**.
- **Delete Record**: Requires `financial_admin` role or higher.
- _Pending Payments tab_:
    - **Retrieve Record**: Requires `financial_read` role or higher.
    - **Create Record**: Requires `financial` role or higher.
    - **Update Record**: Does not exist.
    - **Delete Record**: Requires `financial` role or higher.

## Other Important Information

N/A
