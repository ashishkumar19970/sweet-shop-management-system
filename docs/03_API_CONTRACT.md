# API Contract

## Project Information

**Project Name:** Sweet Shop Management System

**Document Name:** API Contract

**Version:** 1.0

**Prepared By:** Ashish Kumar

**Document Status:** Draft

---

# Purpose

This document defines all REST APIs used in the Sweet Shop Management System. It specifies request format, response format, validation rules, authentication requirements, and business rules.

---

# Common Standards

## Base URL

```
http://localhost:8080/api/v1
```

## Content Type

```
application/json
```

## Authentication

- JWT Token
- Bearer Authentication

Example Header

```
Authorization: Bearer <JWT_TOKEN>
```

---

# Authentication Module

---

## API-001 Customer Registration

### Method

POST

### URL

```
/auth/register
```

### Description

Registers a new customer.

### Authentication Required

No

### Request Body

```json
{
  "firstName": "Ashish",
  "lastName": "Kumar",
  "email": "ashish@gmail.com",
  "mobile": "9876543210",
  "password": "Password@123"
}
```

### Success Response

```json
{
  "success": true,
  "message": "Registration successful",
  "data": {
    "userId": 1
  }
}
```

### Error Responses

- 400 Bad Request
- 409 Email Already Exists
- 500 Internal Server Error

### Database Tables

- users
- roles

---

## API-002 Customer Login

### Method

POST

### URL

```
/auth/login
```

### Authentication Required

No

### Request Body

```json
{
  "email": "ashish@gmail.com",
  "password": "Password@123"
}
```

### Success Response

```json
{
  "success": true,
  "message": "Login Successful",
  "data": {
    "token": "JWT_TOKEN"
  }
}
```

### Error Responses

- 401 Invalid Credentials
- 500 Internal Server Error

---

# Category Module

---

## API-003 Add Category

### Method

POST

### URL

```
/categories
```

### Authentication Required

Yes (ADMIN)

### Request Body

```json
{
  "categoryName": "Sweets",
  "description": "Traditional Indian Sweets"
}
```

### Success Response

```json
{
  "success": true,
  "message": "Category Added Successfully"
}
```

---

## API-004 Get All Categories

### Method

GET

### URL

```
/categories
```

### Authentication Required

No

### Success Response

```json
{
  "success": true,
  "data": []
}
```

---

# Product Module

---

## API-005 Add Product

### Method

POST

### URL

```
/products
```

### Authentication Required

Yes (ADMIN)

### Request Body

```json
{
  "name": "Kaju Katli",
  "price": 650,
  "stock": 100,
  "categoryId": 1
}
```

### Success Response

```json
{
  "success": true,
  "message": "Product Added Successfully"
}
```

---

## API-006 Get Product By Id

### Method

GET

### URL

```
/products/{id}
```

### Path Variable

```
id
```

### Success Response

```json
{
  "success": true,
  "data": {}
}
```

---

# Cart Module

---

## API-007 Add Product To Cart

### Method

POST

### URL

```
/cart/add
```

### Authentication Required

Yes (CUSTOMER)

### Request Body

```json
{
  "productId": 10,
  "quantity": 2
}
```

### Success Response

```json
{
  "success": true,
  "message": "Item Added To Cart"
}
```

---

# Order Module

---

## API-008 Place Order

### Method

POST

### URL

```
/orders
```

### Authentication Required

Yes (CUSTOMER)

### Success Response

```json
{
  "success": true,
  "message": "Order Placed Successfully"
}
```

---

# Payment Module

---

## API-009 Make Payment

### Method

POST

### URL

```
/payments
```

### Authentication Required

Yes

### Request Body

```json
{
  "orderId": 101,
  "paymentMethod": "UPI"
}
```

### Success Response

```json
{
  "success": true,
  "message": "Payment Successful"
}
```

---

# Common Response Format

```json
{
  "success": true,
  "message": "Operation completed successfully",
  "data": {},
  "timestamp": "2026-08-02T12:00:00",
  "status": 200
}
```

---

# HTTP Status Codes

| Code | Description |
|------|-------------|
|200|Success|
|201|Created|
|400|Bad Request|
|401|Unauthorized|
|403|Forbidden|
|404|Not Found|
|409|Conflict|
|500|Internal Server Error|

---

# Security

- JWT Authentication
- BCrypt Password Encryption
- Role Based Authorization
- Input Validation

---

# Future APIs

- Wishlist API
- Coupon API
- Notification API
- Review API
- Dashboard API
