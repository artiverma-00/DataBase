
# Database Relationships

## Definition of Database Relationship

A **database relationship** defines how data in one table is logically connected to data in another table using **primary keys** and **foreign keys**.
Relationships ensure **data consistency, integrity, and efficient data retrieval**, especially in relational databases used by real-world applications such as e-commerce platforms.

In an e-commerce system, relationships help connect **customers, orders, products, payments, and categories** in a meaningful and structured way.

---

## Types of Database Relationships

There are **three main types** of database relationships:

1. One-to-One (1:1)
2. One-to-Many (1:N)
3. Many-to-Many (M:N)

---

## 1️ One-to-One Relationship (1:1)

### Definition

In a **one-to-one relationship**, **one record in Table A** is associated with **only one record in Table B**, and vice versa.

### E-commerce Example

**User ↔ User Profile**

* Each user has exactly one profile
* Each profile belongs to exactly one user

### Example Tables

```text
Users
- user_id (PK)
- email
- password

UserProfiles
- profile_id (PK)
- user_id (FK)
- address
- phone
```

![Image](https://support.microsoft.com/images/en-us/9e935295-f8bb-4fce-8ad3-1eddeb37f988)

![Image](https://beginnersbook.com/wp-content/uploads/2015/04/ER_diagram_one_to_one.png)

### Use Case in E-commerce

* Separating authentication data from personal data
* Improves security and modular design

---

## 2️ One-to-Many Relationship (1:N)

### Definition

In a **one-to-many relationship**, **one record in Table A** can be associated with **multiple records in Table B**, but each record in Table B belongs to **only one record in Table A**.

### E-commerce Example

**Customer → Orders**

* One customer can place multiple orders
* Each order belongs to one customer

### Example Tables

```text
Customers
- customer_id (PK)
- name
- email

Orders
- order_id (PK)
- customer_id (FK)
- order_date
- status
```

![Image](https://images.ctfassets.net/w6r2i5d8q73s/QDa5oq16N1ifmlWC6Dnu2/a52db5fdedc3e933c865bbd3575e903b/technical_diagramming_01_database_diagram_product_image_EN_standard_4_3_2x.png?fm=webp\&q=75)

![Image](https://i.sstatic.net/thblX.jpg)

### Use Case in E-commerce

* Tracking order history
* Customer analytics
* Order lifecycle management

---

## 3️ Many-to-Many Relationship (M:N)

### Definition

In a **many-to-many relationship**, **multiple records in Table A** are related to **multiple records in Table B**.
This relationship requires a **junction (bridge) table**.

### E-commerce Example

**Orders ↔ Products**

* One order can contain multiple products
* One product can appear in multiple orders

### Example Tables

```text
Orders
- order_id (PK)

Products
- product_id (PK)

OrderItems (Junction Table)
- order_id (FK)
- product_id (FK)
- quantity
- price
```

![Image](https://images.ctfassets.net/w6r2i5d8q73s/QDa5oq16N1ifmlWC6Dnu2/a52db5fdedc3e933c865bbd3575e903b/technical_diagramming_01_database_diagram_product_image_EN_standard_4_3_2x.png?fm=webp\&q=75)

![Image](https://www.datensen.com/blog/wp-content/uploads/2021/10/many-to-many-relationship-1-1024x261.png)

### Use Case in E-commerce

* Shopping cart implementation
* Invoice generation
* Revenue analytics

---

## Summary Table

| Relationship Type | Description                      | E-commerce Example |
| ----------------- | -------------------------------- | ------------------ |
| One-to-One        | One record linked to one record  | User ↔ Profile     |
| One-to-Many       | One record linked to many        | Customer → Orders  |
| Many-to-Many      | Many linked to many via junction | Orders ↔ Products  |



## Conclusion

Database relationships form the **foundation of relational database design**.
In an e-commerce application, they ensure:

* Accurate data mapping
* Efficient querying
* Data integrity
* Scalability



