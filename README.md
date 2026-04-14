# Java-Project_Basic_Bank-_System
**Overview**
The Banking System is a Java-based console application designed to manage basic banking operations including account creation, balance inquiries, and deposit transactions. Built using object-oriented programming principles, the system provides a simple yet effective solution for managing customer bank accounts with HashMap-based data storage.

****Key Features**
**1. Account Management****

Account Creation: Add new bank accounts with unique account numbers
Customer Information Storage: Stores customer name and account details
Initial Balance Setup: Set opening balance when creating accounts
Account Lookup: Retrieve account information using account number

**2. Transaction Processing**

Deposit Functionality: Add funds to existing accounts
Real-Time Balance Updates: Immediate balance reflection after transactions
Transaction Validation: Verifies account existence before processing
Transaction Confirmation: Displays updated balance after successful deposits

**3. Account Information Display**

Detailed Account View: Shows account number, customer name, and current balance
Formatted Output: Clean, readable display with proper currency formatting
Error Handling: Provides feedback when account is not found


**Technical Architecture**
**Class Structure**
**1. BankingSystem** (Main Class)

Purpose: Entry point of the application
Responsibilities:

Initializes the Bank instance
Creates sample accounts for demonstration
Executes test transactions
Displays account information


Location: Contains the main() method

**2. Bank Class**

Purpose: Central management system for all bank accounts
Data Structure: Uses HashMap<String, Account> for efficient account storage
Key Methods:

addAccount(): Creates and stores new accounts
displayAccountInfo(): Retrieves and displays account details
performTransaction(): Processes deposit transactions


Design Pattern: Acts as a controller/manager for Account objects

**3. Account Class**

Purpose: Represents individual bank account entity
Attributes:

accountNumber (String): Unique identifier
customerName (String): Account holder's name
balance (double): Current account balance


Methods:

Constructor: Initializes account with all required fields
Getters: Provides read access to private fields
deposit(): Modifies balance by adding specified amount


Encapsulation: All fields are private with public getter methods


Data Flow
Account Creation Flow
1. BankingSystem.main() calls bank.addAccount()
2. Bank creates new Account object
3. Account constructor initializes all fields
4. Bank stores Account in HashMap with accountNumber as key
Transaction Flow
1. User/System calls performTransaction() with account number and amount
2. Bank checks if account exists in HashMap
3. If found: Retrieves Account object
4. Calls account.deposit() method
5. Balance updates internally
6. Displays confirmation with new balance
7. If not found: Displays error message
Display Information Flow
1. displayAccountInfo() called with account number
2. HashMap lookup for account
3. If found: Retrieve account details using getters
4. Display formatted information
5. If not found: Display error message

Code Implementation Details
Data Storage Strategy

HashMap Selection: Chosen for O(1) average-case lookup performance
Key-Value Pair: Account number (String) as key, Account object as value
Memory Efficient: Stores only account references, not duplicates
Fast Retrieval: Instant account access using account number

Current Demonstration
The main() method demonstrates:

Account Creation: Two accounts initialized (John Doe - $1000, Jane Smith - $1500)
Successful Transaction: $500 deposit to account "101"
Failed Transaction: Attempt to deposit to non-existent account "103"
Information Display: Shows details for both created accounts


Sample Output
Transaction successful. Updated balance: $1500.0
Account not found!
Account Number: 101
Customer Name: John Doe
Balance: $1500.0
Account Number: 102
Customer Name: Jane Smith
Balance: $1500.0

System Capabilities
What the System Can Do
✅ Create multiple bank accounts with unique numbers
✅ Store customer information (name, account number, balance)
✅ Process deposit transactions
✅ Display account information
✅ Validate account existence before operations
✅ Handle errors gracefully with appropriate messages
✅ Maintain multiple accounts simultaneously

Object-Oriented Principles Applied
**1. Encapsulation**

Private fields in Account class
Public methods control access to data
Data integrity maintained through controlled modification

**2. Abstraction**

Bank class hides HashMap implementation details
Account class encapsulates balance management logic
Users interact through simple, high-level methods

**3. Single Responsibility Principle**

Account: Manages individual account data and operations
Bank: Manages collection of accounts and banking operations
BankingSystem: Provides application entry point and demonstration


Potential Enhancements
Functional Improvements

Withdrawal Method: Add withdraw() to Account class with overdraft prevention
Transfer Functionality: Transfer funds between accounts
Transaction History: ArrayList to track all transactions with timestamps
Interest Calculation: Calculate and apply interest based on account type
Multiple Account Types: Savings, Checking, Fixed Deposit accounts
Minimum Balance: Enforce minimum balance requirements

User Experience

Interactive Menu: Scanner-based menu system for user choices
Input Validation: Check for valid amounts, account numbers, etc.
Better Formatting: Use DecimalFormat for currency display
Account Statements: Generate printable account statements
Search Functionality: Find accounts by customer name

Technical Improvements

Database Integration: JDBC for MySQL/PostgreSQL persistence
File I/O: Save/load account data from files
Exception Handling: Try-catch blocks for robust error management
Logging: Track all operations with timestamps
Spring Boot REST API: Convert to web service with endpoints
Security: Add password authentication and encryption


Usage Example (As-Is)
java// Create bank instance
Bank bank = new Bank();

// Add accounts
bank.addAccount("101", "John Doe", 1000.0);
bank.addAccount("102", "Jane Smith", 1500.0);

// Perform deposit
bank.performTransaction("101", 500.0);
// Output: Transaction successful. Updated balance: $1500.0

// View account info
bank.displayAccountInfo("101");
// Output: Account Number: 101
//         Customer Name: John Doe
//         Balance: $1500.0

Architecture Benefits

Scalable: Easy to add more accounts without code changes
Maintainable: Clear separation of concerns
Extensible: Simple to add new features (withdrawal, transfer, etc.)
Testable: Methods can be unit tested independently
Type-Safe: Strong typing prevents data errors
