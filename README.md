# ATM System - Object-Oriented Python Implementation

A command-line ATM simulation built using object-oriented programming principles in Python. This project demonstrates core OOP concepts including encapsulation, instance methods, and state management through a practical banking interface.

## Overview

This ATM system provides a simple yet functional interface for managing a bank account. Users can create and update PINs, check balances, withdraw funds, and deposit cash. The implementation uses a single class structure with instance variables to maintain account state throughout the session.

## Features

The system supports the following operations:

- **PIN Creation**: Initialize a new account with a custom PIN and starting balance
- **PIN Update**: Change your existing PIN after verification
- **Cash Withdrawal**: Withdraw funds with balance validation
- **Balance Inquiry**: Check current account balance
- **Cash Deposit**: Add funds to the account
- **Session Management**: Interactive menu system for continuous operation

## Technical Implementation

### Class Structure

The `Atm` class manages all account operations through instance variables:

- `self.pin`: Stores the user's PIN as a string
- `self.balance`: Maintains the current account balance as an integer

### Key Methods

**`__init__(self)`**  
Constructor that initializes account variables and immediately launches the menu interface.

**`menu(self)`**  
Displays the main menu and routes user input to appropriate methods. Acts as the primary control flow mechanism.

**`create_pin(self)`**  
Establishes initial account credentials and starting balance.

**`update_pin(self)`**  
Validates current PIN before allowing updates. Returns to menu on authentication failure.

**`withdraw(self)`**  
Processes withdrawal requests with PIN authentication and sufficient funds verification.

**`check_balance(self)`**  
Displays current balance after PIN verification with option to return to menu.

**`deposit_cash(self)`**  
Adds funds to the account following PIN authentication.

## Usage Example

```python
# Create ATM instance (menu launches automatically)
obj = Atm()

# The system prompts for operation selection:
# User selects option 1 to create PIN
# Enters PIN: "wamikmk"
# Sets initial balance: 15000

# Check balance (option 4)
# Verifies PIN and displays: "Your current balance is: 15000"

# Withdraw funds (option 3)
# Authenticates and withdraws: 5500
# New balance: 9500

# Deposit cash (option 5)
# Authenticates and deposits: 7500
# Updated balance: 17000
```

## Design Considerations

### Security
PIN validation is performed before each sensitive operation. The current implementation stores PINs as plaintext strings for educational purposes. Production systems should use proper encryption and hashing.

### User Flow
The menu system provides continuous operation until the user explicitly exits. After completing certain operations (deposit, failed authentication), the system automatically returns to the menu.

### Error Handling
The system includes basic validation for insufficient funds and incorrect PIN entries. Additional input validation could be added for production use.

## Requirements

- Python 3.x
- No external dependencies required

## Running the Code

Execute the notebook cells in sequence:

1. Run the class definition cell to load the `Atm` class
2. Create an instance with `obj = Atm()`
3. The menu will launch automatically
4. Call `obj.menu()` at any time to restart the interface

## Potential Enhancements

- Input validation for non-numeric balance entries
- Transaction history logging
- Multiple account support
- PIN encryption
- Withdrawal limits and daily transaction caps
- Enhanced error messages and user feedback
- Unit tests for core functionality

## Educational Purpose

This project serves as a practical introduction to object-oriented programming in Python, demonstrating how classes can maintain state and provide structured interfaces for complex operations. The ATM context makes the concepts tangible while keeping the implementation accessible to beginners.
