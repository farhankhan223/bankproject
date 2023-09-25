# Define a User class to represent user objects.
class User():
    # Class-level variable to keep track of the total number of users.
    count = 0

    # Constructor to initialize user attributes.
    def __init__(self, name, gender, salary):
        self.name = name
        self.gender = gender
        self.salary = salary

        # Increment the user count and assign a unique account number.
        User.count = User.count + 1
        self.account = User.count

    # Method to display user details.
    def showdetails(self):
        print(f"Name: {self.name}\nGender: {self.gender}\nSalary: {self.salary}")
        print("Account No:", self.account)

# Define a Bank class to represent bank account objects.
class Bank():
    # Class-level variables for bank name, balance, and user count.
    __balance = 0
    __bankname = "DNS Bank".center(30)
    __usercount = 0

    # Constructor to initialize bank account attributes.
    def __init__(self, name, gender, salary, pin):
        self.name = name
        self.gender = gender
        self.salary = salary
        self.__pin = pin

        # Increment the user count and assign a unique account number.
        Bank.__usercount += 1
        self.account = f"bnkaccno000{Bank.__usercount}"

    # Method to deposit money into the account.
    def deposit(self, amount):
        self.__balance = self.__balance + amount
        print("Amount Deposited Successfully")
        print("Your Current Balance is:", self.__balance)

    # Method to withdraw money from the account (with balance and withdrawal limits).
    def withdraw(self, amount):
        if amount > self.__balance:
            print("Insufficient Balance")
            print("Your Current Balance is:", self.__balance)
        elif amount >= 100 and amount <= self.__balance:
            self.__balance = self.__balance - amount
            print("Thank You For Visiting")
            print("Your Current Bank Amount is:", self.__balance)
        elif amount < 100:
            print("You Cannot Withdraw Less Than 100")
            print("Your Current Balance is:", self.__balance)

    # Method to view account balance.
    def viewbalance(self):
        print(f"Name: {self.name}\nGender: {self.gender}\nSalary: {self.salary}\nCurrent Balance: {self.__balance}")

    # Method to transfer money to another account (with balance and transfer limits).
    def transfer(self, amt, user):
        if amt > self.__balance:
            print("Insufficient Balance")
            print("Your Current Balance is:", self.__balance)
        elif amt >= 1 and amt <= self.__balance:
            user.deposit(amt)
            self.__balance = self.__balance - amt
            print("Amount Transferred Successfully")
            print("Current Balance:", self.__balance)
        elif amt < 1:
            print("You Cannot Transfer Amount Less Than 1")
            print("Current Balance:", self.__balance)

    # Method to get the username.
    def getusername(self):
        return self.name

    # Method to get the PIN (password).
    def getpin(self):
        return self.__pin

    # Method to retrieve login data (username and PIN).
    def logindata(self):
        return [self.name, self.__pin]

    # Method to provide a string representation of the bank account.
    def __str__(self):
        return f"{self.name} {self.__pin}"

# Dictionary to store user accounts.
users = {}

# Main loop for the banking system.
while True:
    print("1. Create Account\n2. Login\n3. Exit")
    choice = input("Enter your Selection: ")

    # Option 1: Create a new bank account.
    if choice == "1":
        name = input("Enter your Name: ")
        gender = input("Enter your Gender: ")
        salary = int(input("Enter your Salary: "))
        pin = input("Set your Password (PIN): ")
        
        # Create a new bank account and store it in the 'users' dictionary.
        users[name] = Bank(name, gender, salary, pin)

    # Option 2: Login to an existing bank account.
    elif choice == "2":
        name = input("Enter your Name: ")
        pin = input("Enter your Password (PIN): ")

        # Check if the user exists in the 'users' dictionary.
        obj = users.get(name, 0)

        if obj == 0:
            print("No Match Found")
        else:
            data = obj.logindata()
            # Check if the entered username and PIN match the stored data.
            if [name, pin] in [data]:
                print("Access Granted")
                while True:
                    print("1. Deposit\n2. Withdraw\n3. View Balance\n4. Transfer\n5. Logout")
                    action = input("Choose an Action: ")
                    if action == "1":
                        amount = int(input("Enter the deposit amount: "))
                        obj.deposit(amount)
                    elif action == "2":
                        amount = int(input("Enter the withdraw amount: "))
                        obj.withdraw(amount)
                    elif action == "3":
                        obj.viewbalance()
                    elif action == "4":
                        accountant_name = input("Enter the Account User Name: ")
                        account = users.get(accountant_name, 0)
                        if account == 0:
                            print("Person Not Found")
                        else:
                            amount = int(input("Enter the transfer amount: "))
                            obj.transfer(amount, account)
                    elif action == "5":
                        print("Logging Out")
                        break
                    else:
                        print("Invalid Operation, Try again")
                else:
                    print("Access Denied")
            else:
                print("Access Denied")

    # Option 3: Exit the program.
    elif choice == "3":
        print("Exit")
        break
