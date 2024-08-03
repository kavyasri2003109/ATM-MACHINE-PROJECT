import time 

print("Please insert your card")
time.sleep(5)

password = 1234
pin = int(input("Enter your ATM pin: "))
balance = 5000

if pin == password:
    while True:
        print("""
        1 == Balance
        2 == Withdraw Balance
        3 == Deposit Balance
        4 == Exit
        """)
        try:
            option = int(input("Please enter your choice: "))
        except ValueError:
            print("Please enter a valid option")
            continue
        
        if option == 1:
            print(f"Your current balance is {balance}")
            print("======================================================")
            print("======================================================")
            print("======================================================")
        
        elif option == 2:
            withdraw_amount = int(input("Please enter withdraw amount: "))
            if withdraw_amount <= balance:
                balance = balance-withdraw_amount
                print(f"{withdraw_amount} is debited from your account")
                print("======================================================")
                print("======================================================")
                print(f"Your updated balance is {balance}")
                print("======================================================")
                print("======================================================")
            else:
                print("Insufficient balance")
        
        elif option == 3:
            deposit_amount = int(input("Please enter deposit amount: "))
            balance = balance+deposit_amount
            print(f"{deposit_amount} is credited to your account")
            print("======================================================")
            print("======================================================")
            print(f"Your updated balance is {balance}")
            print("======================================================")
            print("======================================================")
        
        elif option == 4:
            break
        else:
            print("Invalid option, please try again")
else:
    print("Wrong pin, please try again")
