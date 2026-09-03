# Surfgroupe Architecture

## Overview

Surfgroupe currently follows a **modular monolith architecture** built around a PHP and MySQL application.

The platform combines e-commerce, marketplace, customer accounts, seller management, payments, delivery, logistics, search, and administrative operations within a single application.

The architecture is progressively evolving toward more modular services and APIs while maintaining the existing commerce infrastructure.

## High-Level Architecture

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
       ┌───────────────────────┼───────────────────────┐
       │                       │                       │
   Commerce                Identity               Marketplace
       │                       │                       │
   Catalog                 Accounts                Sellers
   Products                Authentication          Reviews
   Cart                    Addresses
   Checkout
   Orders
   Payments
       │
       ├───────────────────────┐
       │                       │
   Delivery                  Search
       │                       │
   DeliveryContext       Search infrastructure
   Shipping
   Relay Points
   Delivery Estimates
       │
       └────────────────┬──────────────────────────────┘
                        │
                      MySQL
```

## Main Application Areas

### Commerce

The commerce layer handles the core shopping experience:

* Product catalog
* Product details
* Shopping cart
* Checkout
* Orders
* Product reviews

### Identity & Accounts

The platform includes account and authentication components for customers and sellers.

These components cover:

* Authentication
* User accounts
* Seller accounts
* Address management
* Account management
* Validation

### Marketplace

The marketplace layer provides functionality for managing sellers and their products.

The platform is designed to support multiple sellers while maintaining a unified customer shopping experience.

### Delivery & Logistics

Delivery is one of the platform's core domain areas.

Surfgroupe includes a location-aware delivery context that can determine the customer's delivery location and use it throughout the shopping experience.

The delivery infrastructure includes:

* Delivery locations
* Cities and postal codes
* Delivery methods
* Delivery prices
* Delivery estimates
* Shipping routes
* Relay points
* Location-aware checkout

The delivery context can persist a customer's selected location through session and cookie-based state, and can also associate a preferred location with a user account.

### APIs

The application includes API endpoints used by different parts of the platform.

Examples include:

* Location search
* Location updates
* Product-related API endpoints
* Search-related endpoints
* Vendor-related endpoints

The API layer is part of the ongoing transition toward a more service-oriented architecture.

### Search

The project contains search infrastructure intended to support more scalable product discovery.

The search architecture is still evolving, so search components are treated as an independent area rather than being presented as a fully separated production microservice.

## Data Layer

MySQL is currently the primary database system.

The application contains domain-specific data structures for areas such as:

* Products
* Users
* Sellers
* Orders
* Delivery locations
* Delivery prices
* Delivery methods
* Relay points
* Transit routes
* Delivery estimates

Database access is handled through PHP database components, including reusable connection and statement-handling layers.

## Application Structure

The codebase is organized around several application domains and reusable components.

Examples include:

```text
core/
src/
api/
includes/
checkout/
orders/
payment/
shipping/
livraison/
surfrelais/
sellers/
admin/
```

The project also contains older and transitional components. These are progressively being consolidated as the platform evolves.

## Current Architecture

```text
PHP + MySQL
     │
     ├── Modular application components
     ├── APIs
     ├── Delivery infrastructure
     ├── Marketplace functionality
     └── Administrative tooling
```

This architecture allows the platform to continue developing without requiring an immediate migration to a distributed system.

## Evolution Strategy

The intended architectural direction is:

```text
PHP / MySQL Monolith
        ↓
Modular Application
        ↓
Services & APIs
        ↓
Service-Oriented Architecture
        ↓
Node.js / React / Mobile
        ↓
Data + AI
```

The goal is not to introduce microservices simply for the sake of complexity.

Instead, individual domains can become more independent when scale, maintainability, reliability, or product requirements justify the transition.

## Infrastructure

The development and server environment includes:

* Linux
* PHP-FPM
* PHP 8.2
* MySQL
* Composer
* Node.js / npm
* Docker-based components

## Design Principles

The architecture is guided by several principles:

1. **Modularity**
   Keep business domains separated where practical.

2. **Incremental evolution**
   Modernize the platform without rewriting the entire system at once.

3. **API readiness**
   Move reusable functionality toward clearly defined interfaces.

4. **Local-first commerce**
   Delivery, payment, and customer workflows must reflect the realities of the Haitian market.

5. **Scalability through separation**
   Extract services when there is a clear technical or business reason to do so.

6. **Data-driven development**
   Build the foundation required for future analytics and AI capabilities.

