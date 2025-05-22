# NikeStore_ERD

```mermaid 
erDiagram 
PRODUCT { 
    string product_id PK
    string name
    float price
} 
CUSTOMER { 
    string customer_id PK
    string name
    string email
} 
SALE { 
    string sale_id PK
    string product_id FK
    string customer_id FK
    date sale_date
} 
INVENTORY { 
    string inventory_id PK
    string product_id FK
    int quantity
}

PRODUCT ||--o{ SALE : "sold in"
CUSTOMER ||--o{ SALE : "makes"
PRODUCT ||--o{ INVENTORY : "stocked in"
``` 
## Entity Descriptions

- **PRODUCT**: Each product represents a Nike shoe model with a unique ID, name, and price.
- **CUSTOMER**: Customers who buy the shoes. Each has an ID, name, and email.
- **SALE**: Records each sale, connecting a product and a customer, with the date of the sale.
- **INVENTORY**: Tracks how many units of each product are in stock.

## Relationships

- One product can be sold in many sales.
- One customer can make many purchases.
- Inventory tracks how many of each product are available.