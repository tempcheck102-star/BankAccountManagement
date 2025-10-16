import java.util.Scanner;

class BankAccount {
    private String accountHolder;
    private double balance;

    BankAccount(String accountHolder, double balance) {
        this.accountHolder = accountHolder;
        this.balance = balance;
    }

    void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            System.out.println("Deposited: " + amount);
        } else {
            System.out.println("Invalid deposit amount!");
        }
    }

    void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
            System.out.println("Withdrawn: " + amount);
        } else {
            System.out.println("Insufficient balance or invalid amount!");
        }
    }

    void displayBalance() {
        System.out.println(accountHolder + "'s Current Balance: " + balance);
    }

    public String getName() {
        return accountHolder;
    }
}

public class BankSystem {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter number of bank accounts to create: ");
        int n = sc.nextInt();
        sc.nextLine(); // consume newline

        BankAccount[] accounts = new BankAccount[n];

        // Create multiple accounts
        for (int i = 0; i < n; i++) {
            System.out.print("\nEnter account holder name: ");
            String name = sc.nextLine();
            System.out.print("Enter initial deposit: ");
            double amount = sc.nextDouble();
            sc.nextLine();

            accounts[i] = new BankAccount(name, amount);
        }

        // Simple menu-driven system
        int choice;
        do {
            System.out.println("\n===== Bank Menu =====");
            System.out.println("1. Deposit");
            System.out.println("2. Withdraw");
            System.out.println("3. Check Balance");
            System.out.println("4. Exit");
            System.out.print("Enter your choice: ");
            choice = sc.nextInt();

            switch (choice) {
                case 1:
                    System.out.print("Enter account holder name: ");
                    sc.nextLine();
                    String name1 = sc.nextLine();
                    BankAccount acc1 = findAccount(accounts, name1);
                    if (acc1 != null) {
                        System.out.print("Enter deposit amount: ");
                        double dep = sc.nextDouble();
                        acc1.deposit(dep);
                    } else {
                        System.out.println("Account not found!");
                    }
                    break;

                case 2:
                    System.out.print("Enter account holder name: ");
                    sc.nextLine();
                    String name2 = sc.nextLine();
                    BankAccount acc2 = findAccount(accounts, name2);
                    if (acc2 != null) {
                        System.out.print("Enter withdrawal amount: ");
                        double wd = sc.nextDouble();
                        acc2.withdraw(wd);
                    } else {
                        System.out.println("Account not found!");
                    }
                    break;

                case 3:
                    System.out.print("Enter account holder name: ");
                    sc.nextLine();
                    String name3 = sc.nextLine();
                    BankAccount acc3 = findAccount(accounts, name3);
                    if (acc3 != null)
                        acc3.displayBalance();
                    else
                        System.out.println("Account not found!");
                    break;

                case 4:
                    System.out.println("Thank you for using our Bank System!");
                    break;

                default:
                    System.out.println("Invalid choice!");
            }
        } while (choice != 4);

        sc.close();
    }

    // Helper method to find account
    static BankAccount findAccount(BankAccount[] accounts, String name) {
        for (BankAccount acc : accounts) {
            if (acc.getName().equalsIgnoreCase(name))
                return acc;
        }
        return null;
    }
}
