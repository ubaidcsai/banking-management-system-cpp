# banking-management-system-cpp
A simple Banking Management System developed in C++ using Object-Oriented Programming concepts. It supports account creation, deposits, withdrawals, and balance inquiries.

#include <iostream>
using namespace std;

class BankAccount
{
private:
    string name;
    int accountNo;
    double balance;

public:

    void createAccount()
    {
        cout << "\nEnter Account Holder Name: ";
        cin.ignore();
        getline(cin, name);

        cout << "Enter Account Number: ";
        cin >> accountNo;

        cout << "Enter Initial Deposit: ";
        cin >> balance;

        cout << "\nAccount Created Successfully!\n";
    }

    void deposit()
    {
        double amount;

        cout << "\nEnter Amount to Deposit: ";
        cin >> amount;

        balance += amount;

        cout << "Deposit Successful.\n";
        cout << "Current Balance: " << balance << endl;
    }

    void withdraw()
    {
        double amount;

        cout << "\nEnter Amount to Withdraw: ";
        cin >> amount;

        if(amount <= balance)
        {
            balance -= amount;

            cout << "Withdrawal Successful.\n";
            cout << "Remaining Balance: " << balance << endl;
        }
        else
        {
            cout << "Insufficient Balance!\n";
        }
    }

    void display()
    {
        cout << "\n===== Account Details =====\n";

        cout << "Name          : " << name << endl;
        cout << "Account No    : " << accountNo << endl;
        cout << "Balance       : " << balance << endl;
    }
};

int main()
{
    BankAccount account;

    int choice;

    do
    {
        cout << "\n";
        cout << "====== Banking Management System ======\n";
        cout << "1. Create Account\n";
        cout << "2. Deposit Money\n";
        cout << "3. Withdraw Money\n";
        cout << "4. Check Balance\n";
        cout << "5. Exit\n";

        cout << "Enter Your Choice: ";
        cin >> choice;

        switch(choice)
        {
            case 1:
                account.createAccount();
                break;

            case 2:
                account.deposit();
                break;

            case 3:
                account.withdraw();
                break;

            case 4:
                account.display();
                break;

            case 5:
                cout << "\nThank You for Using Banking System.\n";
                break;

            default:
                cout << "\nInvalid Choice!\n";
        }

    }while(choice != 5);

    return 0;
}
