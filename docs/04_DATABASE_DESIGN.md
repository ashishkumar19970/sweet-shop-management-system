# Database Design

## Project Information

**Project Name:** Sweet Shop Management System

**Document Name:** Database Design

**Version:** 1.0

**Prepared By:** Ashish Kumar

**Document Status:** Draft

---

# Purpose

This document defines the database structure of the Sweet Shop Management System. It contains entities, table design, relationships, constraints, business rules, and indexing strategy.

---

# Database

MySQL 8.x

---

# Entities

The system contains the following entities:

- User
- Role
- Category
- Product
- Cart
- CartItem
- Order
- OrderItem
- Payment
- Review
- Inventory
- Address

---

# Table Design

---

## Users

| Column | Type | Constraint |
|----------|-------------|----------------|
| id | BIGINT | Primary Key |
| first_name | VARCHAR(100) | NOT NULL |
| last_name | VARCHAR(100) | NULL |
| email | VARCHAR(150) | UNIQUE |
| mobile | VARCHAR(15) | UNIQUE |
| password | VARCHAR(255) | NOT NULL |
| status | BOOLEAN | DEFAULT TRUE |
| created_at | TIMESTAMP | NOT NULL |
| updated_at | TIMESTAMP | NOT NULL |

---

## Roles

| Column | Type |
|----------|------------|
| id | BIGINT |
| role_name | VARCHAR(50) |

Example Roles

- ADMIN
- CUSTOMER

---

## Categories

| Column | Type |
|----------|------------|
| id | BIGINT |
| category_name | VARCHAR(100) |
| description | TEXT |
| status | BOOLEAN |

---

## Products

| Column | Type |
|----------|------------|
| id | BIGINT |
| name | VARCHAR(150) |
| description | TEXT |
| price | DECIMAL(10,2) |
| stock | INTEGER |
| weight | DOUBLE |
| image_url | VARCHAR(255) |
| category_id | BIGINT (FK) |
| created_at | TIMESTAMP |
| updated_at | TIMESTAMP |

---

## Cart

| Column | Type |
|----------|------------|
| id | BIGINT |
| user_id | BIGINT (FK) |
| total_price | DECIMAL(10,2) |

---

## Cart Item

| Column | Type |
|----------|------------|
| id | BIGINT |
| cart_id | BIGINT (FK) |
| product_id | BIGINT (FK) |
| quantity | INTEGER |
| price | DECIMAL(10,2) |

---

## Orders

| Column | Type |
|----------|------------|
| id | BIGINT |
| user_id | BIGINT (FK) |
| total_amount | DECIMAL(10,2) |
| order_status | VARCHAR(50) |
| payment_status | VARCHAR(50) |
| created_at | TIMESTAMP |

---

## Order Items

| Column | Type |
|----------|------------|
| id | BIGINT |
| order_id | BIGINT (FK) |
| product_id | BIGINT (FK) |
| quantity | INTEGER |
| price | DECIMAL(10,2) |

---

## Payments

| Column | Type |
|----------|------------|
| id | BIGINT |
| order_id | BIGINT (FK) |
| payment_method | VARCHAR(50) |
| transaction_id | VARCHAR(150) |
| payment_status | VARCHAR(50) |

---

# Relationships

## User → Order

One User can place Many Orders.

Relationship

@OneToMany

@ManyToOne

---

## Category → Product

One Category contains Many Products.

Relationship

@OneToMany

@ManyToOne

---

## Cart → CartItem

One Cart contains Many Cart Items.

Relationship

@OneToMany

@ManyToOne

---

## Order → OrderItem

One Order contains Many Order Items.

Relationship

@OneToMany

@ManyToOne

---

## Order → Payment

One Order has One Payment.

Relationship

@OneToOne

@OneToOne

---

# Business Rules

- Product price must be greater than zero.
- Product stock cannot be negative.
- Customer must login before placing an order.
- Customer cannot place an order if the cart is empty.
- Payment must be successful before confirming the order.
- Stock decreases only after successful payment.
- Only purchased customers can submit reviews.

---

# Constraints

- Email must be unique.
- Mobile number must be unique.
- Product name cannot be empty.
- Category is mandatory for every product.
- Every order must belong to one customer.

---

# Indexes

The following indexes should be created for better performance:

- email
- mobile
- category_id
- product_name
- order_status
- created_at

---

# Naming Convention

Database Tables

- users
- roles
- categories
- products
- carts
- cart_items
- orders
- order_items
- payments

Primary Key

id

Foreign Keys

user_id

category_id

product_id

order_id

cart_id

---

# Future Tables

- coupons
- wishlist
- notifications
- delivery
- invoices

---

# Summary

This database design serves as the foundation for Entity creation, JPA mapping, Repository implementation, and MySQL schema generation.
