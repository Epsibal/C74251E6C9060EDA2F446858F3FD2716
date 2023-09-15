class BankAccount:
    def __init__(self, account_number, account_holder_name, initial_balance=0.0):
        self.__account_number = account_number
        self.__account_holder_name = account_holder_name
        self.__account_balance = initial_balance

    def deposit(self, amount):
        if amount > 0:
            self.__account_balance += amount
            print("Deposited Rs{}. New balance: Rs{}".format(amount, self.__account_balance))
        else:
            print("Invalid deposit amount. Amount must be greater than 0.")

    def withdraw(self, amount):
        if amount > 0 and amount <= self.__account_balance:
            self.__account_balance -= amount
            print("Withdrew Rs{}. New balance: Rs{}".format(amount, self.__account_balance))
        else:
            print("Invalid withdrawal amount or insufficient balance.")

    def display_balance(self):
        print("Account Balance for {}: Rs{}".format(self.__account_holder_name, self.__account_balance))

# Create an instance of BankAccount
account_number = input("Enter account number: ")
account_holder_name = input("Enter account holder name: ")
initial_balance = float(input("Enter initial balance amount: "))
account = BankAccount(account_number, account_holder_name, initial_balance)

# Test deposit and withdrawal functionality
amount = float(input("Enter the amount for deposit: "))
account.deposit(amount) 
# Deposit 
amount = float(input("Enter the amount for withdrawal: "))
account.withdraw(amount)    # Withdraw
account.display_balance()   # Display updated balance