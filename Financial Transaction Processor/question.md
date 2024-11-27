# Financial Transaction Processor

## Problem Statement

A financial institution operates a transaction system that processes multiple types of transactions, each with different attributes like amount, type, and associated fees. Your task is to develop a financial transaction processor that calculates the total transaction fees for a given set of transactions, adhering to the following constraints:

- **Transaction Limits:** Each transaction type has a maximum amount limit.
- **Transaction Fees:** Each transaction incurs a fee depending on its type (e.g., deposit, withdrawal, transfer).
- **Time Constraints:** Some transactions can only be processed within specific hours.
- **Minimum Balance:** Ensure the balance never drops below a specified threshold after processing.

The processor should compute:

1. **Total Fee:** The total fee accumulated from the transactions processed.
2. **Final Account Balance:** The remaining balance after processing the transactions.

If no valid transactions can be processed under the given constraints, return `-1`.

---

### Input Format

1. **Initial Account Balance** `balance`: The initial balance in the account.
2. **Transaction Details:** A list of transactions where each transaction is represented as:
   - `transaction_type`: Type of transaction (deposit, withdrawal, transfer, etc.)
   - `amount`: The amount involved in the transaction.
   - `transaction_hour`: The hour of the day when the transaction is to be processed.
   - `transaction_fee`: The fee associated with the transaction.

---

### Output Format

- **Return:** The total transaction fee and the final balance as a tuple `(total_fee, final_balance)`. If no valid transaction can be processed, return `-1`.

---

### Example Input

```text
Initial Account Balance: 5000
Transactions:
deposit 2000 10 5
withdrawal 1500 12 3
transfer 1000 15 2


Query:
balance = 5000

```
### Example Output
```plaintext
Output: (10, 3500)

```

## Constraints
- 1 <= balance <= 1000000
- 1 <= amount <= 50000
- 0 <= transaction_hour <= 23
- 0 <= transaction_fee <= 10
- Transaction types are restricted to "deposit", "withdrawal", and "transfer".
- transaction_hour should be between 0 and 23 (inclusive).











