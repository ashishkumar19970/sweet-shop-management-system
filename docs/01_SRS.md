# Software Requirement Specification (SRS)

## 1. Project Information

**Project Name:** Sweet Shop Management System

**Version:** 1.0

**Prepared By:** Ashish Kumar

**Technology Stack:**
- Java 21
- Spring Boot 3.x
- Spring Security
- JWT
- Hibernate/JPA
- Microservices
- MySQL
- Maven

**Document Version:** 1.0

## 2. Purpose

The purpose of the Sweet Shop Management System is to provide a complete online platform for managing sweet shop operations.

Customers can browse sweets, add products to the cart, place orders, make online payments, and track their orders.

Administrators can manage products, categories, inventory, customer orders, payments, and reports from a centralized dashboard.

The main goal of the system is to reduce manual work, improve order management, and provide a better shopping experience. 

## 3. Scope

The system provides the following features:

### Customer Features

- Customer Registration
- Customer Login
- Browse Products
- Search Products
- Add Products to Cart
- Place Orders
- Online Payment
- Order Tracking
- Order History
- Product Reviews

### Admin Features

- Admin Login
- Manage Categories
- Manage Products
- Manage Inventory
- Manage Orders
- Manage Customers
- View Reports

## 4. Project Objectives

- Build a secure online sweet shop platform.
- Reduce manual billing process.
- Improve customer shopping experience.
- Maintain inventory automatically.
- Provide secure authentication using JWT.
- Support online payment integration.

## 5. User Roles

### Customer

- Register
- Login
- Browse Products
- Place Orders
- Make Payment
- Track Orders

### Admin

- Manage Categories
- Manage Products
- Manage Inventory
- Manage Orders
- Manage Customers
- Generate Reports

- ## 6. Functional Requirements

### FR-001 Customer Registration

The system shall allow customers to register using name, email, mobile number, and password.

### FR-002 Customer Login

The system shall authenticate customers using email and password and generate a JWT token.

### FR-003 Product Management

The admin shall be able to create, update, delete, and view products.

### FR-004 Cart Management

Customers shall be able to add, update, and remove products from the shopping cart.

### FR-005 Order Management

Customers shall be able to place orders successfully.

### FR-006 Payment

The system shall support online payment.

## 7. Non-Functional Requirements

- Secure authentication using JWT.
- Response time should be less than 2 seconds.
- Passwords must be encrypted.
- APIs should follow REST standards.
- Database should support concurrent users.
- Application should be scalable and maintainable.

- ## 8. Business Rules

- Product price must be greater than zero.
- Product stock cannot be negative.
- Customer must login before placing an order.
- Payment must be successful before confirming the order.
- Only purchased customers can submit product reviews.

- ## 9. Assumptions

- Internet connection is available.
- Payment gateway is available.
- MySQL database is running.

- ## 10. Constraints

- Backend will be developed using Java and Spring Boot.
- Database will be MySQL.
- Authentication will use JWT.

- ## 11. Future Enhancements

- Email Notification
- SMS Notification
- Discount Coupons
- Wishlist
- Recommendation System
- AI Chat Support
