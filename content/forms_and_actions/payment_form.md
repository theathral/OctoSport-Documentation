# Payment Details Form and Actions

The Payment Details form is used to manage payment records associated with contracts. It includes information on due dates, amounts, statuses, and payment methods.

## Navigation (TBD)
Steps to locate this page:
- Navigate to the **Payments** section in the main menu.
- Select the **Payment Details Form** option from the available list.

## Payment Details Form

### Fields & Functions
- **Id** (read-only): A unique identifier for each payment record.
- **Status**: A dropdown menu indicating the current payment status. Options include:
    - Pending
    - Paid
    - Refunded
    - Cancelled
- **Contract**: A reference field linking the payment to an active contract.
- **Due Date**: Date field specifying when the payment is due.
- **Payment Date**: Date field required if the status is set to Paid.
- **Billing Period**: Reference field linking to the associated billing period.
- **Payment Method**: Reference field specifying the method of payment.
- **Amount (before Tax)**: Currency field displaying the amount before tax.
- **Tax**: Decimal field representing the tax amount.
- **Amount**: Currency field displaying the total amount (automatically calculated, no direct database field).
- **Comments**: Text field for additional notes.

### Actions & Required Roles

#### Main Actions
- **View Payment**: Allows users to view payment details.
    - Requires **financial_read** role or higher.
- **Save Payment (New Record)**: Saves a new payment record.
    - Requires **financial** role.
- **Save Payment (Existing Record)**: Updates an existing payment record.
    - Requires **financial** role.
- **Delete Payment**: Deletes an existing payment record.
    - Requires **financial_admin** role.

## Other Important Information

N/A