# Kadzodev
#include <iostream>
using namespace std;

class BankAccount {
private:
    int accountNumber;
    string accountHolder;
    double balance;

public:
    // Constructor
    BankAccount(int accNum, string accHolder, double bal) {
        accountNumber = accNum;
        accountHolder = accHolder;
        balance = bal;
    }

    // Deposit function
    void deposit(double amount) {
        balance += amount;
        cout << "\nDeposit: " << amount << endl;
        cout << "New Balance: " << balance << endl;
    }

    // Withdraw function
    void withdraw(double amount) {
        if (amount > balance) {
            cout << "\nWithdrawal: " << amount << endl;
            cout << "Insufficient funds!" << endl;
        } else {
            balance -= amount;
            cout << "\nWithdrawal: " << amount << endl;
            cout << "New Balance: " << balance << endl;
        }
    }

    // Display account details
    void displayAccount() {
        cout << "\nAccount Number: " << accountNumber << endl;
        cout << "Account Holder: " << accountHolder << endl;
        cout << "Balance: " << balance << endl;
    }
};

int main() {

    // Creating two BankAccount objects
    BankAccount account1(101, "John", 5000);
    BankAccount account2(102, "Alice", 3000);

    // Display initial details
    account1.displayAccount();

    // Perform deposit and withdrawal
    account1.deposit(1000);
    account1.withdraw(2000);

    // Display updated details
    account1.displayAccount();

    return 0;
}
