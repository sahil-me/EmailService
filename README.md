# 🛒 E-Commerce Platform 🛍

## Infrastructure

[![Spring Cloud | Eureka Server](https://img.shields.io/badge/Spring%20Cloud-Eureka%20Server-6DB33F?style=for-the-badge&logo=spring&logoColor=white)](https://github.com/sahil-me/ServiceDiscovery)
[![Spring Cloud | API Gateway](https://img.shields.io/badge/Spring%20Cloud-API%20Gateway-6DB33F?style=for-the-badge&logo=spring&logoColor=white)](https://github.com/sahil-me/ApiGateway)

## Business Services

[![Microservice | User Service](https://img.shields.io/badge/Microservice-User%20Service-007EC6?style=for-the-badge&labelColor=555555&logo=spring&logoColor=white)](https://github.com/sahil-me/UserService)
[![Microservice | Product Service](https://img.shields.io/badge/Microservice-Product%20Service-007EC6?style=for-the-badge&labelColor=555555&logo=spring&logoColor=white)](https://github.com/sahil-me/ProductService)
[![Microservice | Payment Service](https://img.shields.io/badge/Microservice-Payment%20Service-007EC6?style=for-the-badge&labelColor=555555&logo=spring&logoColor=white)](https://github.com/sahil-me/PaymentService)
[![Microservice | Email Service](https://img.shields.io/badge/Microservice-Email%20Service-007EC6?style=for-the-badge&labelColor=555555&logo=spring&logoColor=white)](https://github.com/sahil-me/EmailService)

https://github.com/user-attachments/assets/48c32572-9405-4ea8-b42c-141b23c28af8

> 🎥 Email Service Demonstration!

---

## Table of Contents
- [Introduction](#introduction)
- [Architecture Diagram](#architecture-diagram)
- [Project Structure](#project-structure)
- [Tech Stack](#tech-stack)
- [Product Requirements Document (PRD)](#product-requirements-document-prd)
  - [Functional Requirements](#functional-requirements)
    - [User Management](#1%EF%B8%8F⃣-user-management)
    - [Product Catalog](#2%EF%B8%8F⃣-product-catalog)
    - [Cart & Checkout](#3%EF%B8%8F⃣-cart--checkout)
    - [Order Management](#4%EF%B8%8F⃣-order-management)
    - [Payment](#5%EF%B8%8F⃣-payment)
    - [Authentication](#6%EF%B8%8F⃣-authentication)
  - [High-Level Design (HLD)](#high-level-design-hld)
    - [Architecture Components](#architecture-components)
      - [Load Balancers (LB)](#architecture-components)
      - [API Gateway](#architecture-components)
      - [Microservices Architecture](#architecture-components)
      - [Databases](#architecture-components)
      - [Message Broker (Kafka)](#architecture-components)
      - [Caching (Redis)](#architecture-components)
      - [Search & Analytics (Elasticsearch)](#architecture-components)      
  - [Typical Flow](#typical-flow)
    - [Part 1: Product Search](#part-1-product-search)
    - [Part 2: Add to Cart](#part-2-add-to-cart)
    - [Part 3: Checkout](#part-3-checkout)
- [Resources](#resources)
- [Contributing](#contributing)
- [License](#license)
- [Author](#author)

---

## Introduction

A scalable and modular e-commerce platform built using a microservices architecture. The system is designed to handle core e-commerce functionalities such as product management, cart operations, order processing, payment integration, and user management through independently deployable backend services.

The project demonstrates real-world backend engineering concepts including RESTful APIs, database design, asynchronous communication, scalability, service abstraction, caching, payment gateway integration, and microservices-based system design using Spring Boot and related technologies.

---

## Architecture Diagram

    Client
       │
       ▼
    API Gateway
       │
       ▼
    Service Discovery
       │
       ├── User Service
       ├── Product Service
       ├── Payment Service
       └── Email Service

---

## Project Structure

    E-Commerce-Platform/
    │
    ├── ServiceDiscovery/   # Eureka Service Registry
    ├── ApiGateway/         # API Gateway
    ├── UserService/        # User Management
    ├── ProductService/     # Product Catalog Management
    ├── PaymentService/     # Payment Integration
    └── EmailService/       # Email Notifications

---

## Tech Stack

| Technology                          | Purpose                                  |
| ----------------------------------- | ---------------------------------------- |
| Java 21                             | Core Programming Language                |
| Spring Boot 3.4.0                   | Application Framework                    |
| Spring Web                          | RESTful API Development                  |
| Spring Kafka                        | Kafka Producer/Consumer Integration      |
| Apache Kafka                        | Event Streaming & Message Broker         |
| JavaMail API                        | Email Composition & SMTP Communication   |
| Spring Cloud Netflix Eureka Client  | Service Discovery                        |
| Lombok                              | Boilerplate Code Reduction               |
| Maven                               | Build Automation & Dependency Management |
| Spring Boot DevTools                | Development & Hot Reload Support         |
| Spring Boot Configuration Processor | Configuration Metadata Support           |
| JUnit 5                             | Testing Framework                        |
| IntelliJ IDEA                       | Integrated Development Environment       |


---

## Product Requirements Document (PRD)

### Functional Requirements

### 1️⃣ User Management
- **Registration**: Allow users to register via email or social media profiles.
- **Login**: Secure user login with credentials.
- **Profile Management**: Enable users to view and edit their profiles.
- **Password Reset**: Allow password resets through secure email links.

### 2️⃣ Product Catalog
- **Browsing**: Users can browse products by category.
- **Product Details**: Product pages include images, descriptions, specifications, and more.
- **Search**: Provide search functionality with keyword-based queries.

### 3️⃣ Cart & Checkout
- **Add to Cart**: Users can add products to their cart.
- **Cart Review**: View selected items with price, quantity, and totals.
- **Checkout**: Seamless process to finalize purchases, including delivery details and payment options.

### 4️⃣ Order Management
- **Order Confirmation**: Confirm orders with details after purchase.
- **Order History**: Allow users to view past orders.
- **Order Tracking**: Provide delivery status tracking.

### 5️⃣ Payment
- **Multiple Payment Options**: Support credit/debit cards, online banking, and other methods.
- **Secure Transactions**: Ensure secure payment handling.
- **Payment Receipt**: Generate receipts for successful payments.

### 6️⃣ Authentication
- **Secure Authentication**: Protect user data during login and active sessions.
- **Session Management**: Allow users to stay logged in until they log out or after a specified duration.

## High-Level Design (HLD)

### Architecture Components

1️⃣ **Load Balancers (LB)**: Distribute traffic across servers for high availability (e.g., AWS ELB).

2️⃣ **API Gateway**: Entry point for routing requests, managing rate limits, and handling authentication (e.g., Kong).

3️⃣ **Microservices**: Separate services for modular and scalable architecture.

4️⃣ **Databases**: MySQL and MongoDB for structured and unstructured data.

5️⃣ **Message Broker (Kafka)**: Enable asynchronous inter-service communication.

6️⃣ **Caching (Redis)**: Boost response times for frequently accessed data.

7️⃣ **Search & Analytics (Elasticsearch)**: Efficient product searches with advanced capabilities.

## Typical Flow

### Part 1: Product Search
1️⃣ User logs in and searches for a product.

2️⃣ Request passes through the Load Balancer to the API Gateway.

3️⃣ API Gateway routes the search request to the Product Catalog Service.

4️⃣ Product Catalog Service queries Elasticsearch for results.

### Part 2: Add to Cart
1️⃣ User adds a product to the cart.

2️⃣ Cart Service stores the item in MongoDB and produces a Kafka message.

### Part 3: Checkout
1️⃣ User checks out.

2️⃣ Order Management Service processes the order and sends a Kafka message.

3️⃣ Payment Service consumes the message to handle payment.

---

## Resources

[![Spring Boot Mail](https://img.shields.io/badge/Spring%20Boot-Email-6DB33F?style=for-the-badge&logo=spring&logoColor=white)](https://docs.spring.io/spring-boot/reference/io/email.html)
[![Spring for Apache Kafka](https://img.shields.io/badge/Spring%20for-Apache%20Kafka-6DB33F?style=for-the-badge&logo=spring&logoColor=white)](https://spring.io/projects/spring-kafka)
[![Spring Boot Kafka Guide](https://img.shields.io/badge/Spring%20Boot-Kafka%20Guide-6DB33F?style=for-the-badge&logo=spring&logoColor=white)](https://docs.spring.io/spring-boot/reference/messaging/kafka.html)
[![Apache Kafka](https://img.shields.io/badge/Apache-Kafka-231F20?style=for-the-badge&logo=apachekafka&logoColor=white)](https://docs.conduktor.io/learn/fundamentals/what-is-apache-kafka)
[![Apache ZooKeeper](https://img.shields.io/badge/Apache-ZooKeeper-EA4335?style=for-the-badge&logo=apache&logoColor=white)](https://docs.conduktor.io/learn/fundamentals/zookeeper)
[![JavaMail SMTP](https://img.shields.io/badge/JavaMail-SMTP-007396?style=for-the-badge&logo=java&logoColor=white)](https://www.digitalocean.com/community/tutorials/javamail-example-send-mail-in-java-smtp)
[![Apache Kafka Mac Setup](https://img.shields.io/badge/Apache%20Kafka-Mac%20Setup-231F20?style=for-the-badge&logo=apachekafka&logoColor=white)](https://docs.conduktor.io/learn/getting-started/install-mac)
[![Apache Kafka Windows Setup](https://img.shields.io/badge/Apache%20Kafka-Windows%20Setup-231F20?style=for-the-badge&logo=apachekafka&logoColor=white)](https://docs.conduktor.io/learn/getting-started/install-windows)
[![Kafka CLI Tutorials](https://img.shields.io/badge/Kafka-CLI%20Tutorials-231F20?style=for-the-badge&logo=apachekafka&logoColor=white)](https://docs.conduktor.io/learn/cli-tutorials/index)

---

## Contributing

Contributions are welcome. Before submitting changes, please review:
- [Contributing Guide](./Contributing.md)
- [Code of Conduct](./CODE_OF_CONDUCT.md)
- [Security Policy](./SECURITY.md)

---

## License
This project is licensed under the [Apache 2.0 License](./LICENSE).

---

## Author

[**Sahil Sharma**](https://github.com/sahil-me)

Thank you for exploring this project. If you find it helpful, consider giving the repository a ⭐ to support its continued development.

