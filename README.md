''' Question: Create a BankAccount class with public attributes for account_number and balance.
Add private attributes for _owner_name and _pin. Implement methods to get and set these attributes securely.'''

class BankAccount:
    def __init__(self, account_number, balance, owner_name, pin):
        self._account_number = account_number
        self._balance = balance
        self._owner_name = owner_name
        self._pin = pin

    # Getter methods to securely access private attributes
    def get_account_number(self):
        return self._account_number

    def get_balance(self):
        return self._balance

    def get_owner_name(self):
        return self._owner_name

    # Setter methods to securely set private attributes
    def set_balance(self, new_balance):
        if new_balance >= 0:
            self._balance = new_balance
        else:
            print("Invalid balance. Balance cannot be negative.")

    def set_owner_name(self, new_owner_name):
        self._owner_name = new_owner_name

    def authenticate(self, entered_pin):
        # Method to authenticate the user using the provided PIN
        return self._pin == entered_pin


# Example usage:
account = BankAccount(account_number=1123112231, balance=90000.00, owner_name="waleed khan", pin="7070")

# Accessing public attributes
print("Account Number:", account.get_account_number())
print("Balance:", account.get_balance())
print("Owner Name:", account.get_owner_name())

# Modifying private attributes securely
account.set_balance(1500.00)
account.set_owner_name("Jane Doe")

# Authenticating with PIN
entered_pin = input("Enter your PIN: ")
if account.authenticate(entered_pin):
    print("PIN is correct. Access granted.")
else:
    print("Incorrect PIN. Access denied.")



