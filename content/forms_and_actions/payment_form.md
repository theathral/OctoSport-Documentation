# Payment Details Form and Actions

The Payment Details form is used to manage payment records associated with contracts. It includes information on due dates, amounts, statuses, and payment methods.

## Navigation (TBD)

Steps to locate this page:

- Navigate to the **Payments** section in the main menu.
- Select the **Payment Details Form** option from the available list.

## Payment Details Form

### Fields & Functions

- **Id** (read-only): A unique identifier for each payment record.
- **Status** (read-only): A dropdown menu indicating the current payment status. More at: [Payment Record Lifecycle](#payment-record-lifecycle).
- **Contract**: A reference field linking the payment to an active contract.
- **Due Date**: Date field specifying when the payment is due.
- **Payment Date**: Date field specifying when the payment has been made.
- **Billing Period**: Reference field linking to the associated billing period. More at: [Billing Period Selection](billing-period-selection).
- **Payment Method**: Reference field specifying the method of payment. More at: [Payment Method Selection](payment-period-selection).
- **Amount (before Tax)**: Currency field displaying the amount of payment before tax.
- **Tax**: Decimal field representing the tax amount.
- **Amount** (read-only): Currency field displaying the total amount of payment.
- **Comments**: Text field for additional notes.

[IMAGE]

## Payment Record Lifecycle

The payment record progresses through the following stages:

- **Pending**: The payment is awaiting processing and has not yet been completed.
- **Paid**: The payment has been successfully processed and completed.
- **Refunded**: The payment has been returned, typically due to cancellations or errors.
- **Cancelled**: The payment process has been stopped, and will not be made.

### Action Buttons

- **Save Payment**: Creates or updates a payment record.
- **Mark Payment Paid**: Marks a payment as successfully processed and completed.
    - Available only if the payment status is **Pending**.
- **Payment Refunded**: Marks a payment as refunded.
    - Available only if the payment status is **Pending**.
- **Cancel Payment**: Marks a payment record as cancelled.
    - Available only if the payment status is **Pending**.
- **Delete Payment**: Deletes an existing payment record.
    - Available only on existing records.

## Required Roles

Please refer to the [Role Hierarchy section](system-roles) for details about role hierarchy. Users with higher roles can perform actions that require lower roles.

- **Retrieve Record**: Requires `financial_read` role or higher.
- **Create Record**: Requires `financial` role or higher.
- **Update Record**:
    - Requires `financial` role or higher, if status is **Pending**.
    - Requires `financial_admin` role or higher, if status is **Paid**, **Refunded**, or **Cancelled**.
- **Delete Record**: Requires `financial_admin` role or higher.
- **Status field**: Editable for `financial_admin` role or higher.

## Other Important Information

N/A