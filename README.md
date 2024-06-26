# Bank-system-API

---

This is a Spring Boot application for a banking system that provides management for user accounts, transactions, and user information. The app is built using the Spring Boot framework and a MySQL database to store banking data.

### Functionality

1. **Users Management:**
    - Users are characterized by:
        - Role
        - First name
        - Last name
        - Email
        - Password
        - Phone number
        - Address
        - Status
        - Creation date

2. **Accounts Management:**
    - Bank accounts are linked to users and possess:
        - Card number
        - CVV
        - Balance
        - Status
        - Creation date

3. **Transactions Logging:**
    - Records financial transactions within the system, including:
        - Transaction type
        - Amount
        - Note
        - Creation date
        - Associated account
## API Documentation
Explore our API endpoints using Swagger UI:
[Swagger UI](http://localhost:8081/swagger-ui/index.html#/)

Note: Make sure your server is running to access the Swagger UI.

---

### Entity-Relationship Diagram (ERD)

```mermaid
erDiagram
BANK_USER ||--o{ CARD : "has"
BANK_USER{
    int id pk
    string name
    string passward
    string email
    string phone_number
    string addrees
    string status
    string role
    date creation_date
}

CARD ||--o{ TRANSACTION : "has"
CARD {
    int id pk
    int user_id fk
    string card_number
    int csv
    double balance
    string state
    date creation_date
}

TRANSACTION{
    int id pk
    int card_id fk
    string type(deposite)(withdraw)
    int amount
    date time
}

