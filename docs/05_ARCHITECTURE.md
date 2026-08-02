# Software Architecture

## Project Information

**Project Name:** Sweet Shop Management System

**Document Name:** Software Architecture

**Version:** 1.0

**Prepared By:** Ashish Kumar

**Document Status:** Draft

---

# Purpose

This document describes the overall architecture of the Sweet Shop Management System. It explains how different layers of the application communicate with each other.

---

# Architecture Style

The project follows a Layered Architecture using Spring Boot.

Architecture Type

- Layered Architecture
- REST API
- Client-Server Architecture
- Monolithic Architecture (Phase 1)

Future Upgrade

- Microservices Architecture

---

# Technology Stack

Backend

- Java 21
- Spring Boot 3.x
- Spring Security
- Spring Data JPA
- Hibernate
- JWT

Database

- MySQL 8.x

Build Tool

- Maven

API

- REST API

Documentation

- Swagger / OpenAPI

Version Control

- Git
- GitHub

---

# High Level Architecture

Customer
        │
        ▼
React Web Application
        │
        ▼
REST API
        │
        ▼
Spring Boot Application
        │
 ┌──────┼───────────────┐
 ▼      ▼               ▼
Authentication   Product   Order Module
        │
        ▼
Service Layer
        │
        ▼
Repository Layer
        │
        ▼
MySQL Database

---

# Application Layers

## Presentation Layer

Responsibilities

- Receive HTTP Requests
- Return HTTP Responses
- Validate Request

Components

- Controller

---

## Business Layer

Responsibilities

- Business Logic
- Validation
- Workflow
- Transaction Management

Components

- Service
- ServiceImpl

---

## Data Access Layer

Responsibilities

- Database Operations
- CRUD Operations

Components

- Repository

---

## Database Layer

Responsibilities

- Store Data
- Retrieve Data

Database

MySQL

---

# Request Flow

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

# Major Modules

Authentication

- Registration
- Login
- JWT
- Logout

Category

- CRUD

Product

- CRUD
- Search
- Inventory

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

- JWT Token

Authorization

- Role Based Access

Password Encryption

- BCrypt

---

# Exception Handling

Global Exception Handler

Custom Exceptions

- UserNotFoundException
- ProductNotFoundException
- CategoryNotFoundException
- BusinessException

---

# Logging

SLF4J

Logback

Log Levels

- INFO
- WARN
- ERROR

---

# Validation

Bean Validation

Annotations

- @NotNull
- @NotBlank
- @Email
- @Size

---

# API Documentation

Swagger UI

OpenAPI 3

---

# Monitoring

Spring Boot Actuator

Health Check

Metrics

---

# Future Improvements

- Microservices
- Docker
- Redis Cache
- Kafka
- API Gateway
- CI/CD Pipeline
- Kubernetes

---

# Summary

The Sweet Shop Management System follows a clean layered architecture that separates presentation, business logic, data access, and database layers. This architecture improves maintainability, scalability, security, and code reusability.
