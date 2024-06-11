# Logical View of Banking Application

## Component Diagram

```mermaid
graph TD;
    subgraph "Banking Application"
        userInterface(User Interface)
        presentationLayer(Presentation Layer)
        businessLogic(Business Logic)
        dataAccess(Data Access)
        database(Database)
        
        userInterface --> presentationLayer
        presentationLayer --> businessLogic
        businessLogic --> dataAccess
        dataAccess --> database
    end
classDiagram
    class User {
        username: string
        password: string
        authenticate(): boolean
        requestTransaction(): void
    }
    class Account {
        accountNumber: string
        balance: float
        deposit(amount: float): void
        withdraw(amount: float): void
    }
    class Transaction {
        transactionID: string
        amount: float
        timestamp: datetime
        processTransaction(): void
    }
    
    User "1" -- "many" Account
    Transaction "1" -- "1" Account

