# Logical View of Banking Application

## Business Logic

```mermaid
classDiagram
    class Account {
        +balance: float
        +deposit(amount: float): void
        +withdraw(amount: float): void
    }
    class Transaction {
        +amount: float
        +date: Date
        +type: string
        +execute(): void
    }
    Account "1" -- "1..*" Transaction

    class UserInterface {
        +displayMenu(): void
        +getUserInput(): void
    }
    class Controller {
        +processRequest(): void
    }
    class Service {
        +executeTransaction(): void
    }
    class DAO {
        +saveTransaction(): void
        +updateAccountBalance(): void
    }
    
    UserInterface --> Controller
    Controller --> Service
    Service --> DAO

    class Server {
    }

    class Database {
    }

    Controller --> Server
    Server --> Database
