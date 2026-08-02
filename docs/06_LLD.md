# Low Level Design (LLD)

## Project Information

**Project Name:** Sweet Shop Management System

**Document Name:** Low Level Design (LLD)

**Version:** 1.0

**Prepared By:** Ashish Kumar

**Document Status:** Draft

---

# Purpose

This document describes the internal design of the Sweet Shop Management System. It defines the Java package structure, classes, interfaces, DTOs, repositories, services, controllers, exception handling, validation, and utility classes.

---

# Project Package Structure

```
com.sweetshop
│
├── config
├── controller
├── service
├── service.impl
├── repository
├── entity
├── dto
│   ├── request
│   └── response
├── mapper
├── exception
├── advice
├── security
├── validation
├── util
├── constant
├── common
└── filter
```

---

# Authentication Module

## Controller

AuthController

Responsibilities

- Customer Registration
- Customer Login
- Logout
- Refresh Token

---

## Service

AuthService

Responsibilities

- Register Customer
- Authenticate Customer
- Generate JWT Token
- Validate User

---

## Repository

UserRepository

Responsibilities

- Save User
- Find By Email
- Find By Mobile
- Check Existing User

---

## Entity

User

Fields

- id
- firstName
- lastName
- email
- mobile
- password
- role
- createdAt
- updatedAt

---

## DTO

### Request DTOs

- RegisterRequest
- LoginRequest

### Response DTOs

- LoginResponse
- RegisterResponse

---

# Category Module

Controller

CategoryController

Service

CategoryService

Repository

CategoryRepository

Entity

Category

DTO

CategoryRequest

CategoryResponse

---

# Product Module

Controller

ProductController

Service

ProductService

Repository

ProductRepository

Entity

Product

DTO

ProductRequest

ProductResponse

---

# Cart Module

Controller

CartController

Service

CartService

Repository

CartRepository

Entity

Cart

CartItem

---

# Order Module

Controller

OrderController

Service

OrderService

Repository

OrderRepository

Entity

Order

OrderItem

---

# Payment Module

Controller

PaymentController

Service

PaymentService

Repository

PaymentRepository

Entity

Payment

---

# Common Components

## Base Entity

Fields

- createdAt
- updatedAt

---

## Common API Response

Fields

- success
- message
- data
- timestamp
- status

---

## Global Exception Handler

Handles

- UserNotFoundException
- ProductNotFoundException
- CategoryNotFoundException
- OrderNotFoundException
- PaymentFailedException
- BusinessException

---

# Validation

Request Validation

- @NotNull
- @NotBlank
- @Email
- @Size
- @Positive

---

# Mapper

Responsibilities

- Entity to DTO
- DTO to Entity

Example

UserMapper

ProductMapper

CategoryMapper

---

# Security

Components

- JwtFilter
- JwtUtil
- SecurityConfig
- CustomUserDetailsService
- PasswordEncoder

---

# Utility Classes

- DateUtil
- ResponseUtil
- JwtUtil

---

# Constants

ApplicationConstants

SecurityConstants

APIConstants

---

# Logging

Log Every

- Request
- Response
- Exception
- Database Operation

---

# Class Interaction

Client

↓

Controller

↓

Service

↓

Repository

↓

Database

↓

Repository

↓

Service

↓

Controller

↓

Client

---

# Design Principles

- Single Responsibility Principle (SRP)
- Open Closed Principle (OCP)
- Dependency Injection
- Separation of Concerns
- Layered Architecture
- Clean Code Practices

---

# Future Improvements

- Redis Cache
- Kafka Integration
- Docker Support
- Microservices Migration
- Event Driven Architecture

---

# Summary

The Low Level Design document defines the internal class-level architecture of the Sweet Shop Management System. It acts as the blueprint for Java implementation and helps developers understand how each layer and component interacts with each other before coding begins.
