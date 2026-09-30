Expense and Income Tracker (CLI)
A lightweight command-line tool written in Python to record day-to-day personal finances, inspect transaction records, and monitor cash flow using a persistent SQLite database.

Overview
Managing daily spending without bloated spreadsheets or ad-heavy mobile apps can be tedious. This project provides a terminal-based interface to quickly log earnings and expenditures, check running totals, view net balances, and reset records when starting a new accounting period.

The application uses Python's standard library and SQLite, requiring zero external package installations.

Features
Record Income & Expenses: Prompts for an item description and decimal amount, assigning transaction types automatically.

Persistent Storage: Stores all entries in an SQLite database file (transactions.db) created locally upon startup.

Financial Summary: Calculates real-time total expenses, total income, and net balance (income - expenses).

Transaction Log: Displays formatted transaction history with unique record IDs.

Data Reset: Includes a confirmation prompt before deleting all stored entries.

Project Structure
Plaintext
├── main.py             # Main application source code and database logic
├── transactions.db     # SQLite database (auto-generated on first run)
└── README.md           # Project documentation and run guide
Prerequisites
Python 3.8 or higher

No external packages (pip) are required. The project relies entirely on built-in modules:

sqlite3 (standard Python database interface)

To verify Python is installed on your machine, run:

Bash
python --version
# or
python3 --version
Installation & Setup
Clone the repository:

Bash
git clone https://github.com/{your-username}/{your-repo-name}.git
cd {your-repo-name}
Verify files:
Ensure main.py is present in your working directory:

Bash
ls          # macOS / Linux
dir         # Windows PowerShell / CMD
Running the Application
Execute the script directly from your terminal:

On Windows:
Bash
python main.py
On macOS / Linux:
Bash
python3 main.py
Walkthrough & Usage
When launched, the program displays a 5-option interactive menu:

Plaintext
Expense and Income Tracker
1. Add Expense
2. Add Income
3. Display Transactions
4. Delete Transaction History
5. Exit
Enter your choice: 
1. Adding an Expense or Income
Select 1 (Expense) or 2 (Income).

Enter a brief text label (e.g., Groceries, Freelance Project).

Enter the monetary amount (e.g., 45.50 or 1200).

The program commits the record to transactions.db and returns to the menu.

2. Viewing Transactions and Totals
Select 3.

The terminal prints each recorded transaction formatted as:
[ID] - [Description]: $[Amount] ([Type])

A financial breakdown follows immediately:

Total expenses

Total income

Net balance

3. Resetting Transaction History
Select 4.

Type y to confirm deletion or n to cancel.

4. Exiting
Select 5 to close the database connection and terminate the process.

Database Schema
The database table transactions is initialized with the following structure:

Column	Data Type	Notes
id	INTEGER	Primary Key, Auto-incremented
description	TEXT	Brief item description
amount	REAL	Transaction value
type	TEXT	Categorized as either expense or income
Troubleshooting
Permission issues on Linux/macOS: Ensure you have write permissions in the directory so the application can create transactions.db.

Database lock: If the program is abruptly terminated during a write operation, verify no orphan Python processes are running before restarting.
