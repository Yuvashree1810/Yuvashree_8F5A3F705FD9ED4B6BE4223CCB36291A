class BankAccount:
    def __init__(self, owner, balance=0.0):
        self.owner = owner
        self.balance = balance

    def deposit(self, amount):
        if amount > 0:
            self.balance += amount
            return f"Deposited ${amount}. New balance: ${self.balance}"
        else:
            return "Invalid deposit amount."

    def withdraw(self, amount):
        if 0 < amount <= self.balance:
            self.balance -= amount
            return f"Withdrew ${amount}. New balance: ${self.balance}"
        else:
            return "Invalid withdrawal amount or insufficient balance."

    def get_balance(self):
        return f"Current balance for {self.owner}: ${self.balance}"

# Example usage:
if __name__ == "__main__":
    account1 = BankAccount("John")
    print(account1.get_balance())  # Initial balance for John: $0.0

    print(account1.deposit(100))  # Deposited $100. New balance: $100.0
    print(account1.withdraw(50))  # Withdrew $50. New balance: $50.0
    print(account1.get_balance())  # Current balance for John: $50.0