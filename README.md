# Banking Management System (JDBC)

A console-based Banking Management System developed using Java and JDBC with MySQL. This project demonstrates core banking functionalities such as user registration, account creation, deposit, withdrawal, and fund transfer using database connectivity.

---

## Features

* User Registration and Login
* Open Bank Account
* Deposit Money
* Withdraw Money
* Transfer Money Between Accounts
* Check Account Balance
* Security PIN verification for transactions

---

## Technologies Used

* Java
* JDBC (Java Database Connectivity)
* MySQL
* PreparedStatement for secure queries
* Transaction Management (Commit and Rollback)

---

## Project Structure

The main source files are located in:

```id="z2d4ks"
src/main/java/bank/
```

Files:

```id="k1e8o7"
BankingApp.java
User.java
Accounts.java
AccountManager.java
```

---

## Database Setup

### Create Database

```sql id="a6c9lh"
CREATE DATABASE bank;
USE bank;
```

### Create User Table

```sql id="q8w1lp"
CREATE TABLE `user` (
    user_id INT PRIMARY KEY AUTO_INCREMENT,
    full_name VARCHAR(100),
    email VARCHAR(100) UNIQUE,
    password VARCHAR(100)
);
```

### Create Accounts Table

```sql id="n5m2vd"
CREATE TABLE accounts (
    account_number BIGINT PRIMARY KEY,
    full_name VARCHAR(100),
    email VARCHAR(100),
    balance DECIMAL(10,2),
    security_pin VARCHAR(10)
);
```

---

## Configuration

Update database credentials in `BankingApp.java`:

```java id="r3j9ux"
private static final String url = "jdbc:mysql://127.0.0.1:3306/bank";
private static final String username = "root";
private static final String password = "your_password";
```

---

## How to Run

1. Clone the repository
2. Open the project in Eclipse or IntelliJ
3. Add MySQL JDBC Driver or use Maven dependency
4. Run `BankingApp.java`

---

## How It Works

* User registers and logs in
* If no account exists, user creates a new account
* After login, user can perform transactions like deposit, withdrawal, transfer, and balance inquiry

---

## Transaction Handling

The application uses JDBC transaction management:

* Auto-commit is disabled during transactions
* Commit is executed on success
* Rollback is executed on failure

This ensures data consistency during operations like money transfer

---

## Limitations

* Passwords are stored in plain text
* Console-based interface
* Basic validation only

---

## Future Improvements

* Implement password hashing
* Add graphical user interface
* Build web-based version using Servlets or Spring Boot
* Add transaction history feature
* Improve validation and security

---

## Author

Yash Ingole
