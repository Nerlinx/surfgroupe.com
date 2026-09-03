# Surfgroupe Architecture

## Overview

Surfgroupe is an e-commerce and marketplace platform designed for the Haitian market.

The platform is currently built around a PHP and MySQL application, with multiple modular components covering commerce, marketplace operations, customer accounts, payments, delivery, logistics, search, and administration.

The long-term technical direction is to evolve Surfgroupe into a **modern, scalable, service-oriented platform** based on TypeScript, Node.js, modern frontend applications, microservices, event-driven architecture, data infrastructure, and AI.

The migration is designed to be incremental. Existing commerce capabilities can continue operating while individual domains are progressively extracted into independent services.

---

# Current Architecture

Surfgroupe currently follows a **modular monolith architecture**.

```text
                         SURFGROUPE
                              │
             ┌────────────────┴────────────────┐
             │                                 │
        Presentation                       Application
             │                                 │
     PHP / HTML / CSS / JS                    PHP 8.2
     Bootstrap / jQuery                       │
             │                                 │
             └────────────────┬────────────────┘
                              │
       ┌──────────────────────┼──────────────────────┐
       │                      │                      │
   Commerce               Identity              Marketplace
       │                      │                      │
   Catalog                Accounts              Sellers
   Products               Authentication        Reviews
   Cart                   Addresses
   Checkout
   Orders
   Payments
       │
       ├───────────────────┐
       │                   │
   Delivery             Search
       │                   │
   DeliveryContext    Search infrastructure
   Shipping
   Relay Points
   Delivery Estimates
       │
       └──────────────┬──────────────────────────────┘
                      │
                    MySQL
```

This architecture provides a practical foundation for developing the initial commerce platform while allowing individual domains to become more independent over time.

---

# Current Technology Stack

## Backend

* PHP 8.2
* MySQL
* Composer
* PHP-FPM

## Frontend

* HTML
* CSS
* JavaScript
* jQuery
* Bootstrap

## Application Components

The current codebase contains dedicated areas for:

* Commerce
* Authentication
* Customer accounts
* Sellers
* Orders
* Checkout
* Payments
* Shipping
* Delivery
* Relay points
* APIs
* Administration

## Supporting Infrastructure

The development environment also includes:

* Node.js
* npm
* Docker-based components
* Search infrastructure

Some modern technologies are currently used only in specific components or are part of the platform's transition strategy. They should not be interpreted as the current architecture of the entire application.

---

# Target Architecture

The long-term architecture is designed around **independent business domains and scalable services**.

```text
                         SURFGROUPE PLATFORM
                                  │
                    ┌─────────────┴─────────────┐
                    │                           │
              Web Applications             Mobile Apps
                    │                           │
             React / Next.js             React Native
             TypeScript                  TypeScript
                    │                           │
                    └─────────────┬─────────────┘
                                  │
                                  ▼
                         API Gateway / BFF
                                  │
        ┌─────────────────────────┼─────────────────────────┐
        │                         │                         │
        ▼                         ▼                         ▼
   Identity Services       Commerce Services       Marketplace Services
        │                         │                         │
   Authentication          ┌──────┼──────┐           Seller Service
   Users                    │      │      │           Vendor Operations
   Profiles              Catalog  Cart  Orders
   Addresses
        │
        └─────────────────────────────────────────────────────────┐
                                                                  │
        ┌─────────────────────────┬───────────────────────────────┤
        │                         │                               │
        ▼                         ▼                               ▼
 Logistics Services       Payment Services              Notification Services
        │                         │                               │
 Delivery                     Payment Providers            Email / SMS
 Shipping                     Payment Processing            Push
 Relay Points
 Tracking
        │
        └─────────────────────────┬───────────────────────────────┘
                                  │
                                  ▼
                         Event / Message Bus
                                  │
              ┌───────────────────┼───────────────────┐
              │                   │                   │
              ▼                   ▼                   ▼
        Search Service       Data Platform       Analytics Services
              │                   │                   │
         Search Engine       Data Pipelines       Dashboards
         Product Indexing    Data Warehouse       BI
                                  │
                                  ▼
                            AI Platform
                                  │
                 ┌────────────────┼────────────────┐
                 │                │                │
                 ▼                ▼                ▼
           Recommendations   Forecasting     AI Assistant
           Personalization   Demand          Customer Support
           Discovery         Inventory       Seller Assistance
```

---

# Microservices Domains

The target architecture separates services according to business responsibility.

## Identity Service

Responsible for:

* Authentication
* User identity
* Customer accounts
* Seller identities
* Authorization
* Sessions and security

## Catalog Service

Responsible for:

* Products
* Categories
* Product attributes
* Product media
* Availability
* Product metadata

## Cart Service

Responsible for:

* Shopping carts
* Cart items
* Quantities
* Cart persistence
* Cart calculations

## Order Service

Responsible for:

* Orders
* Order lifecycle
* Order status
* Order items
* Order history

## Marketplace Service

Responsible for:

* Sellers
* Seller profiles
* Seller products
* Seller operations
* Marketplace rules

## Payment Service

Responsible for:

* Payment workflows
* Payment provider integrations
* Payment status
* Transaction records
* Payment events

Payment providers remain isolated from the rest of the platform through service boundaries.

## Logistics Service

Responsible for:

* Delivery locations
* Delivery methods
* Delivery pricing
* Delivery estimates
* Shipping routes
* Relay points
* Shipment tracking

This service is particularly important for Surfgroupe because delivery infrastructure must reflect the geographic and operational realities of the Haitian market.

## Search Service

Responsible for:

* Product indexing
* Product discovery
* Search queries
* Filtering
* Ranking
* Search suggestions

The search layer can evolve independently from the core commerce database.

## Notification Service

Responsible for:

* Email notifications
* SMS notifications
* Push notifications
* Order notifications
* Delivery notifications
* Seller notifications

## Analytics Service

Responsible for collecting and processing platform events for operational and business analytics.

Potential data includes:

* Sales
* Orders
* Products
* Sellers
* Customer behavior
* Delivery performance
* Search behavior

---

# Event-Driven Architecture

As the platform grows, services should communicate through events where asynchronous processing provides clear benefits.

```text
Order Service
      │
      │ OrderCreated
      ▼
 Event / Message Bus
      │
      ├──────────────► Payment Service
      │
      ├──────────────► Notification Service
      │
      ├──────────────► Logistics Service
      │
      └──────────────► Analytics Pipeline
```

Example events may include:

```text
UserCreated
ProductCreated
ProductUpdated
OrderCreated
OrderPaid
OrderCancelled
ShipmentCreated
ShipmentUpdated
DeliveryCompleted
SellerRegistered
```

Event-driven communication can reduce coupling between services and provide a foundation for real-time processing, analytics, automation, and AI.

---

# Data Architecture

The target platform is expected to use a **polyglot data architecture** where each data technology is selected according to its purpose.

Potential components include:

```text
Operational Databases
        │
        ├── PostgreSQL / MySQL
        │
        ▼
Event / Streaming Layer
        │
        ▼
Data Pipelines
        │
        ├── Python
        ├── SQL
        └── Data Processing
        │
        ▼
Data Warehouse / Lakehouse
        │
        ├── Business Intelligence
        ├── Analytics
        └── Machine Learning
```

The exact database and infrastructure choices will depend on scale, operational requirements, and the evolution of the platform.

---

# AI Architecture

AI will be treated as a platform capability rather than embedded directly into every business service.

```text
                    AI PLATFORM
                         │
        ┌────────────────┼────────────────┐
        │                │                │
        ▼                ▼                ▼
 Recommendation     Forecasting      AI Assistant
 Engine             Engine           Services
        │                │                │
        └────────────────┼────────────────┘
                         │
                         ▼
                    Data Platform
```

Potential AI capabilities include:

* Product recommendations
* Intelligent search
* Personalized discovery
* Demand forecasting
* Inventory prediction
* Customer assistance
* Seller assistance
* Catalog enrichment
* Logistics optimization

Python will be used where appropriate for machine learning, data processing, experimentation, and AI services.

---

# Frontend Architecture

The long-term frontend stack is designed around TypeScript.

```text
                    Frontend Platform
                           │
             ┌─────────────┼─────────────┐
             │             │             │
             ▼             ▼             ▼
        Next.js Web   React Applications  Mobile
             │                         React Native
             └─────────────┬───────────────┘
                           │
                       TypeScript
                           │
                           ▼
                     API Platform
```

The objective is to share reliable types, API contracts, validation rules, and reusable components across web and mobile applications where practical.

---

# Backend Technology Direction

The backend evolution is expected to move progressively toward:

* Node.js
* TypeScript
* NestJS or comparable service frameworks
* REST APIs
* Event-driven communication
* Background workers
* Distributed services

PHP will continue to play an important role during the migration period.

The migration does not require rewriting the platform in one step. Existing PHP modules can remain operational while new services are introduced around clearly defined domains.

---

# Infrastructure & DevOps

The target infrastructure is designed for scalable deployment and operational visibility.

Potential components include:

```text
Source Control
      │
      ▼
CI/CD
      │
      ▼
Containerized Services
      │
      ▼
Container Orchestration
      │
      ▼
Cloud Infrastructure
      │
      ├── Databases
      ├── Caches
      ├── Message Brokers
      ├── Search
      └── Object Storage
```

The long-term platform may adopt:

* Docker
* Kubernetes
* CI/CD pipelines
* Cloud infrastructure
* Infrastructure as Code
* Centralized logging
* Metrics
* Distributed tracing
* Automated testing
* Security scanning

These technologies represent the target infrastructure direction and are not all currently deployed across Surfgroupe.

---

# Scalability Strategy

Surfgroupe will prioritize scalability at the architectural boundaries that matter most.

Key principles include:

### Horizontal Scaling

Services should be independently scalable when traffic requires it.

### Service Isolation

A failure in one domain should have limited impact on unrelated domains.

### Asynchronous Processing

Long-running or non-critical operations should move to background workers and event-driven workflows when appropriate.

### Caching

Frequently accessed data can be cached to reduce database load and improve response times.

### Independent Deployment

Services should eventually be deployable independently when the operational maturity of the platform supports it.

### Observability

The platform should provide visibility into:

* Requests
* Errors
* Latency
* Infrastructure health
* Business events
* Service dependencies

---

# Migration Strategy

The transition from the current architecture to the target architecture will be incremental.

```text
Current PHP / MySQL Application
              │
              ▼
      Modularize Domains
              │
              ▼
        Introduce APIs
              │
              ▼
      Extract First Services
              │
              ▼
     Introduce Event Bus
              │
              ▼
     Independent Services
              │
              ▼
     Data & AI Platform
```

The first services should be extracted according to real business and technical needs rather than architectural fashion.

Potential early candidates include:

* Search
* Notifications
* Authentication
* Logistics
* Payments
* Catalog

---

# Architectural Principles

Surfgroupe follows these long-term principles:

1. **Modular by domain**
2. **API-first**
3. **Type-safe where possible**
4. **Cloud-ready**
5. **Event-driven where useful**
6. **Independently scalable services**
7. **Observable systems**
8. **Security by design**
9. **Data-driven decision making**
10. **AI as a product capability**
11. **Incremental migration**
12. **Avoid premature complexity**

The objective is to build an architecture that can scale with the product, the market, and the engineering team.
