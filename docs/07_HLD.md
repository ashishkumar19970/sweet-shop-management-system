# High Level Design (HLD)

## Project Information

**Project Name:** Sweet Shop Management System

**Document Name:** High Level Design (HLD)

**Version:** 1.0

**Prepared By:** Ashish Kumar

**Document Status:** Draft

---

# Purpose

This document describes the overall system architecture, major modules, component interaction, data flow, deployment architecture, and technology stack of the Sweet Shop Management System.

The purpose of this document is to provide a high-level overview of how the complete system works before implementation begins.

---

# System Overview

Sweet Shop Management System is an online e-commerce application that allows customers to browse sweets, place orders, make payments, and track orders.

Administrators can manage products, categories, inventory, customers, and orders through an admin dashboard.

---

# Architecture Type

- Monolithic Architecture (Phase 1)
- RESTful API
- Layered Architecture
- Client-Server Architecture

Future Enhancement

- Microservices Architecture

---

# Technology Stack

## Frontend

- React.js

## Backend

- Java 21
- Spring Boot 3.x
- Spring Security
- Spring Data JPA
- Hibernate
- JWT

## Database

- MySQL 8.x

## Build Tool

- Maven

## API Documentation

- Swagger / OpenAPI

## Version Control

- Git
- GitHub

---

# System Components

## Client Layer

- Customer
- Admin

---

## Presentation Layer

- React Web Application

Responsibilities

- Display UI
- Send API Requests
- Display API Responses

---

## API Layer

Spring Boot REST APIs

Responsibilities

- Receive Requests
- Validate Requests
- Return Responses

---

## Business Layer

Responsibilities

- Business Logic
- Authentication
- Order Processing
- Payment Processing

---

## Data Access Layer

Responsibilities

- Database Communication

Components

- JPA Repository

---

## Database Layer

Database

MySQL

Responsibilities

- Store Data
- Retrieve Data
- Maintain Relationships

---

# High Level Architecture Diagram

```
                Customer / Admin
                       │
                       ▼
               React Frontend
                       │
                       ▼
              REST API (HTTPS)
                       │
                       ▼
          Spring Boot Backend
                       │
      ┌────────────────┼─────────────────┐
      ▼                ▼                 ▼
Authentication     Product Module     Order Module
      │                │                 │
      └────────────────┼─────────────────┘
                       ▼
                 Service Layer
                       ▼
                Repository Layer
                       ▼
                 MySQL Database
```

---

# Request Flow

Customer

↓

React UI

↓

REST API

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

React UI

↓

Customer

---

# Core Modules

Authentication

- Register
- Login
- Logout
- JWT

Category

- Category CRUD

Product

- Product CRUD
- Search
- Filter

Inventory

- Stock Management

Cart

- Add Item
- Remove Item
- Update Quantity

Order

- Place Order
- Order History

Payment

- Online Payment

Review

- Product Reviews

---

# Security Architecture

Authentication

- JWT Authentication

Authorization

- Role Based Access

Password Security

- BCrypt Password Encoding

---

# Logging

Framework

- SLF4J
- Logback

Log Levels

- INFO
- WARN
- ERROR

---

# Exception Handling

Global Exception Handler

Custom Exceptions

- UserNotFoundException
- ProductNotFoundException
- OrderNotFoundException
- BusinessException

---

# Deployment Architecture

Developer

↓

GitHub Repository

↓

Build using Maven

↓

Spring Boot JAR

↓

Server

↓

MySQL Database

---

# Non Functional Design

- High Availability
- Security
- Scalability
- Maintainability
- Performance
- Reliability

---

# Future Enhancements

- Docker
- Redis
- Kafka
- Microservices
- API Gateway
- CI/CD
- Kubernetes
- Monitoring Dashboard

---

# Summary

The High Level Design provides an overall view of the Sweet Shop Management System. It explains the architecture, system components, communication flow, technology stack, deployment flow, and module interaction. This document acts as the blueprint for architects, developers, testers, and DevOps engineers before development begins.
