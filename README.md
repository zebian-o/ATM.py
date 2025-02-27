# ATM.py
class ATM:
    def __init__(self, initial_balance):
        self.balance = initial_balance

    def deposit(self, amount):
        if amount > 0:
            self.balance += amount
            print(f"Deposited: {amount}")

    def withdraw(self, amount):
        if amount > 0 and amount <= self.balance:
            self.balance -= amount
            print(f"Withdrew: {amount}")
        else:
            print("Insufficient funds!")

    def check_balance(self):
        print(f"Current Balance: {self.balance}")
        return self.balance

def main():
    atm = ATM(1000)  # Initial balance

    while True:
        print("Welcome to the ATM!")
        print("1. Deposit")
        print("2. Withdraw")
        print("3. Check Balance")
        print("4. Exit")

        choice = int(input("Enter your choice: "))

        if choice == 1:
            amount = float(input("Enter amount to deposit: "))
            atm.deposit(amount)
        elif choice == 2:
            amount = float(input("Enter amount to withdraw: "))
            atm.withdraw(amount)
        elif choice == 3:
            atm.check_balance()
        elif choice == 4:
            print("Thank you for using the ATM!")
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()
