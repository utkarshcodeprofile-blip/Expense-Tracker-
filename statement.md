# Problem Statement

## Problem
Keeping track of personal income and expenses on paper or in scattered notes is time consuming and often leads to mistakes while recording transactions, adding up totals and working out the remaining balance. My program helps tackle this by automating the process. It lets the user record income and expenses, stores them in a database so they are not lost when the program is closed, and displays all transactions along with the total income, total expenses and net balance.

## Scope
A single user, command line program. Data is saved permanently in a local SQLite database (`transactions.db`), so it remains available every time the program is run.

## Target Users
Individuals, students and freelancers who want a simple, lightweight way to track their day-to-day money without using a spreadsheet or a full-fledged finance app.

## Features
1. Adds expenses and income with a description and an amount
2. Stores all transactions permanently in a SQLite database
3. Displays the full list of transactions
4. Calculates total income, total expenses and net balance
5. Deletes the entire transaction history after confirmation
