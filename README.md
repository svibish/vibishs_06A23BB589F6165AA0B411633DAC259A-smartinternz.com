class BankAccount:
    def _init_(self, account_number, account_holder_name, initial_balance=0.0):
        self.__account_number = account_number
        self.__account_holder_name = account_holder_name
        self.__account_balance = initial_balance

    def deposit(self, amount):
        if amount > 0:
            self.__account_balance += amount
            return f"Deposited ${amount}. New balance: ${self.__account_balance}"
        else:
            return "Invalid deposit amount. Please deposit a positive amount."

    def withdraw(self, amount):
        if amount > 0 and amount <= self.__account_balance:
            self.__account_balance -= amount
            return f"Withdrew ${amount}. New balance: ${self.__account_balance}"
        elif amount > self.__account_balance:
            return "Insufficient funds. Withdrawal not possible."
        else:
            return "Invalid withdrawal amount. Please withdraw a positive amount."

    def display_balance(self):
        return f"Account Balance for {self.__account_holder_name}: ${self.__account_balance}"


if _name_ == "__main__":
    
    my_account = BankAccount("123456789", "John Doe", 1000.0)

    
    print(my_account.deposit(500))  

    
    print(my_account.withdraw(200))  

    
    print(my_account.display_balance())