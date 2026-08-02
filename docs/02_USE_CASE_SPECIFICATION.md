# Use Case Specification

## Project Information

**Project Name:** Sweet Shop Management System

**Document Name:** Use Case Specification

**Version:** 1.0

**Prepared By:** Ashish Kumar

**Document Status:** Draft

---

# Purpose

This document describes all use cases of the Sweet Shop Management System. It explains how customers and administrators interact with the system.

---

# Actors

### Primary Actors

- Customer
- Admin

### Secondary Actors

- Payment Gateway
- Database
- Email Service (Future)

---

# Use Cases

---

## UC-001 Customer Registration

### Actor

Customer

### Description

A new customer creates an account in the system.

### Preconditions

- Customer is not registered.
- Valid email and mobile number.

### Main Flow

1. Customer opens the Registration page.
2. Customer enters personal details.
3. Customer enters email and password.
4. System validates the information.
5. System checks duplicate email/mobile.
6. Customer account is created.
7. Success message is displayed.

### Alternative Flow

- Email already exists.
- Mobile number already exists.

### Postconditions

- Customer account is successfully created.

---

## UC-002 Customer Login

### Actor

Customer

### Description

Customer logs into the application.

### Preconditions

- Customer must be registered.

### Main Flow

1. Customer enters email and password.
2. System validates credentials.
3. JWT token is generated.
4. Customer dashboard opens.

### Alternative Flow

- Invalid email.
- Wrong password.

### Postconditions

- Customer successfully logged in.

---

## UC-003 Browse Products

### Actor

Customer

### Description

Customer views available products.

### Preconditions

- Products are available.

### Main Flow

1. Customer opens Products page.
2. System fetches product list.
3. Products are displayed.
4. Customer selects a product.

### Postconditions

- Product details displayed.

---

## UC-004 Add Product to Cart

### Actor

Customer

### Description

Customer adds products to shopping cart.

### Preconditions

- Customer logged in.
- Product available in stock.

### Main Flow

1. Customer selects product.
2. Clicks Add to Cart.
3. System checks stock.
4. Product added into cart.
5. Cart updated.

### Alternative Flow

- Product out of stock.

### Postconditions

- Cart updated successfully.

---

## UC-005 Place Order

### Actor

Customer

### Description

Customer places an order.

### Preconditions

- Customer logged in.
- Cart contains products.

### Main Flow

1. Customer opens cart.
2. Reviews items.
3. Clicks Place Order.
4. System calculates total.
5. Order created.

### Alternative Flow

- Cart empty.

### Postconditions

- Order created successfully.

---

## UC-006 Make Payment

### Actor

Customer

### Description

Customer pays for the order.

### Preconditions

- Order exists.

### Main Flow

1. Customer selects payment method.
2. System redirects to payment gateway.
3. Customer completes payment.
4. Payment status updated.
5. Order confirmed.

### Alternative Flow

- Payment failed.
- Payment cancelled.

### Postconditions

- Payment successful.

---

## UC-007 Order History

### Actor

Customer

### Description

Customer views previous orders.

### Preconditions

- Customer logged in.

### Main Flow

1. Customer opens My Orders.
2. System fetches order history.
3. Orders displayed.

### Postconditions

- Customer views previous orders.

---

## UC-008 Admin Login

### Actor

Admin

### Description

Admin logs into the admin panel.

### Preconditions

- Admin account exists.

### Main Flow

1. Admin enters credentials.
2. System validates.
3. JWT generated.
4. Admin Dashboard displayed.

### Postconditions

- Admin logged in.

---

## UC-009 Manage Categories

### Actor

Admin

### Description

Admin manages product categories.

### Main Flow

- Add Category
- Update Category
- Delete Category
- View Categories

---

## UC-010 Manage Products

### Actor

Admin

### Description

Admin manages products.

### Main Flow

- Add Product
- Update Product
- Delete Product
- Search Product
- Update Stock

---

## UC-011 Manage Orders

### Actor

Admin

### Description

Admin manages customer orders.

### Main Flow

- View Orders
- Update Order Status
- Cancel Order
- Complete Order

---

# Business Rules

- Customer must login before placing an order.
- Product stock must be greater than zero.
- Payment must be successful before confirming an order.
- Only purchased customers can submit reviews.

---

# Future Use Cases

- Wishlist
- Coupons
- Notifications
- Invoice Download
- AI Recommendation
