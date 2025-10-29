# ERD (Entity-Relationship Diagram) — Deskripsi & Mermaid
Berikut adalah skema ERD tingkat MVP.

Mermaid diagram (diagram dapat divisualisasikan menggunakan Mermaid support):

```mermaid
erDiagram
    USER ||--o{ SHOP : owns
    SHOP ||--o{ PRODUCT : has
    PRODUCT ||--o{ ORDER_ITEM : included_in
    ORDER ||--o{ ORDER_ITEM : contains
    USER ||--o{ ORDER : places
    SHOP ||--o{ ORDER : receives

    USER {
        int id PK
        string name
        string email
        string password_hash
        string phone
        datetime created_at
    }
    SHOP {
        int id PK
        int owner_id FK
        string name
        string address
        string phone
        datetime created_at
    }
    PRODUCT {
        int id PK
        int shop_id FK
        string name
        text description
        decimal price
        int stock
        string image_url
        datetime created_at
    }
    ORDER {
        int id PK
        int shop_id FK
        int customer_id FK
        decimal total_amount
        string status
        datetime created_at
        datetime updated_at
    }
    ORDER_ITEM {
        int id PK
        int order_id FK
        int product_id FK
        int quantity
        decimal unit_price
    }
```

Catatan: Untuk implementasi Firebase, struktur collection bisa mengikuti: users -> shops -> products, orders (top-level or under shops).
