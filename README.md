# Nike Store Entity Relationship Diagram 
This outlines the ERD for the Nike Store, illustrating the relationships and constraints between the various entities involved in the store's operations.
## Entity Relationship Diagram 
```mermaid 
erDiagram 
    Product {
    string product_id PK "Unique identifier for each shoe model"
    string name "Name of the shoe model" 
    string size "Soze of the shoe" 
    decimal price "Price of the shoe"
    }
    Customer {
    sting customer_id PK "Unique identifer for each customer"
    string name "Name of customer"
    string email "email of customer"
    string pone "phone number of customer" 
    } 
    Sale {
    string sale_id PK "Unique identifier for each sale transaction"
    date sale_date "Date of the sale"
    string product_id FK "Reference to the purchased product"
    string customer_id FK "Reference to customer making purchase"
    int quantity "Number of units sold"
    decimal total_amount "Total amount for sale" 
    }
    Inventory {
    string product_id PK, FK "Unique identifier for each shoe model"
    int stock_level "Current stock level of product" 
    }

Product ||--o{ Sale : sells
Customer ||--o{ Sale : makes
Inventory ||--o{ Product : has

