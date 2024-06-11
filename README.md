## Logical View (4+1 Model) for Banking Application

This Mermaid diagram illustrates the Logical View (4+1 Model) for a banking application that performs basic transactions.

```mermaid
graph LR
A[Presentation] --> B{Business Logic}
B --> C{Account Management}
B --> D{Transaction Processing}
C --> E{Account Data Access}
D --> E
E --> F{External System (Core Banking System)}
