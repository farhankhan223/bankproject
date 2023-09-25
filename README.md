 Banking System is a simple Python program that emulates the functionality of a basic banking system. It allows users to create bank accounts, log in securely, and perform various banking transactions. The project consists of two main classes: User and Bank.

1. User Class:

The User class is responsible for creating and managing user profiles.
Each user has the following attributes:
Name: The user's full name.
Gender: The user's gender.
Salary: The user's monthly salary.
Account Number: A unique account number assigned to each user.
Users can view their account details, including their name, gender, salary, and account number.
The User class keeps track of the total number of users using the class variable count.

2. Bank Class:

The Bank class is responsible for creating and managing bank accounts.
Each bank account has the following attributes:
Name: The user's full name associated with the account.
Gender: The user's gender associated with the account.
Salary: The user's monthly salary associated with the account.
PIN (Password): A private PIN used for secure login.
Balance: The current balance in the account.
Account Number: A unique account number assigned to each account.
Users can perform the following banking operations:
Deposit money into their account.
Withdraw money from their account (subject to balance and withdrawal limits).
View their account balance.
Transfer money to another account (subject to balance and transfer limits).
The Bank class keeps track of the total number of accounts and the total balance across all accounts using class-level attributes.
