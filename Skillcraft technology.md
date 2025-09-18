# Task-1

def loan_repayment_calculator(principal, annual_interest_rate, annual_payment):
    years = 0
    total_paid = 0.0
    balance = principal
    interest_rate = annual_interest_rate / 100.0

    while balance > 0:
        # Apply interest for the year
        balance += balance * interest_rate
        # Make payment
        balance -= annual_payment
        if balance < 0:
            total_paid += annual_payment + balance  # adjust for overpayment
            balance = 0
        else:
            total_paid += annual_payment
        years += 1
    
    return years, total_paid

# Input from user
principal = float(input("Enter loan principal amount: "))
annual_interest_rate = float(input("Enter annual interest rate (in %): "))
annual_payment = float(input("Enter annual payment amount: "))

years_needed, total_repayment = loan_repayment_calculator(principal, annual_interest_rate, annual_payment)

print(f"Total years to repay: {years_needed}")
print(f"Total amount repaid: {total_repayment:.2f}")
