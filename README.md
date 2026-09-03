# Surfgroupe

### E-commerce & Marketplace Platform

Surfgroupe is a commerce platform designed to make online buying and selling more accessible in Haiti.

The platform combines **e-commerce, marketplace capabilities, localized delivery, payment integrations, and logistics infrastructure** with a long-term vision toward a scalable, data-driven and AI-enabled platform.

> **Build for today's market. Architect for tomorrow's scale.**

---

## 🚀 Overview

Surfgroupe addresses practical challenges of digital commerce in Haiti, including:

* Local product discovery
* Online purchasing and selling
* Cash-based and local payment workflows
* Location-aware delivery
* Pickup and relay-point logistics
* Seller and customer management
* Order and delivery tracking
* Marketplace operations

The platform is being developed progressively, starting from a **PHP/MySQL modular architecture** and evolving toward a modern platform built around **TypeScript, Node.js, React, mobile applications, APIs, data engineering and AI**.

---

## ✨ Core Capabilities

### 🛍️ Commerce

* Product catalog
* Product discovery and search
* Product details
* Shopping cart
* Checkout
* Orders
* Customer accounts
* Seller workflows

### 🏪 Marketplace

* Seller management
* Seller products
* Marketplace-oriented commerce workflows
* Product and seller discovery
* Commission-oriented business model

### 📍 Localized Commerce

Surfgroupe is designed around the realities of local commerce in Haiti.

* Delivery locations
* Cities and postal codes
* Location-aware availability
* Delivery pricing
* Delivery estimates
* Delivery methods
* Pickup / relay points
* Location-aware checkout

### 🚚 Logistics

The platform includes foundations for a localized logistics system, including:

* Delivery management
* Shipping routes
* Delivery estimates
* Relay-point infrastructure
* Delivery pricing
* Order tracking

The long-term goal is to evolve this into a dedicated logistics platform capable of supporting a broader commerce ecosystem.

### 💳 Payments

The platform is designed to support payment methods adapted to the local market, including cash-based and local digital payment workflows.

### 📊 Data & Analytics

Data is becoming a core part of the platform's evolution.

Future capabilities include:

* Business intelligence
* Product analytics
* Seller analytics
* Customer behavior analysis
* Demand forecasting
* Operational analytics
* Data pipelines
* Machine learning

### 🤖 AI

AI is part of the long-term product strategy rather than a claim that every capability is already deployed.

Potential applications include:

* Product recommendations
* Intelligent search
* Demand forecasting
* Seller insights
* Customer assistance
* Automated categorization
* Commerce intelligence

---

## 🏗️ Architecture

### Current Architecture

The current platform is primarily a **PHP/MySQL modular application**, with progressively separated components for commerce, accounts, delivery, APIs and operational tooling.

```text
                    SURFGROUPE
                         │
              ┌──────────┴──────────┐
              │                     │
           Customers             Sellers
              │                     │
              └──────────┬──────────┘
                         │
                    Web Platform
                         │
              ┌──────────┴──────────┐
              │                     │
           Commerce             Marketplace
              │                     │
        ┌─────┼─────┐         ┌─────┴─────┐
        │     │     │         │           │
     Catalog Cart Orders    Sellers     Products
        │
        ▼
     Delivery
        │
   ┌────┼─────┐
   │    │     │
Locations Prices Relay Points
```

### Target Architecture

The long-term architecture moves toward a service-oriented and eventually microservices-based platform.

```text
                    SURFGROUPE PLATFORM
                            │
             ┌──────────────┴──────────────┐
             │                             │
        Web / Mobile                  External APIs
             │                             │
     React / Next.js                 Partners
     React Native
             │
             ▼
       API Gateway / BFF
             │
     ┌───────┼────────┬──────────┐
     │       │        │          │
     ▼       ▼        ▼          ▼
 Identity  Commerce Marketplace Logistics
 Service   Services   Services   Services
             │                     │
       ┌─────┼─────┐          ┌────┼────┐
       │     │     │          │    │    │
    Catalog Cart Orders     Shipping Relay Tracking
             │
             ▼
       Event / Message Bus
             │
      ┌──────┼────────┬──────────┐
      ▼      ▼        ▼          ▼
   Search   Data  Notifications Payments
   Service Platform   Service    Services
              │
              ▼
         AI Platform
              │
      ┌───────┼────────┐
      ▼       ▼        ▼
 Recommendations Forecasting AI Assistant
```

The architecture will evolve progressively. Microservices, event-driven infrastructure, cloud orchestration and other advanced components will be introduced when they provide clear operational or scalability benefits.

See [`docs/architecture.md`](docs/architecture.md) for more details.

---

## 🧰 Technology Direction

### Current

* PHP 8.2
* MySQL
* Composer
* PHP-FPM
* JavaScript
* jQuery
* Bootstrap
* AJAX
* REST-style APIs
* Docker-based components

### Evolving Toward

* TypeScript
* Node.js
* NestJS
* React
* Next.js
* React Native
* REST APIs
* Event-driven architecture
* Microservices
* Python
* R
* Data pipelines
* Machine learning / AI
* Docker
* CI/CD
* Cloud infrastructure
* Observability

The technology roadmap is intentionally progressive rather than a wholesale rewrite.

---

## 🗺️ Roadmap

Surfgroupe is being developed through successive architectural stages:

```text
PHP / MySQL Application
          │
          ▼
   Modular Application
          │
          ▼
      APIs & Services
          │
          ▼
Service-Oriented Architecture
          │
          ▼
TypeScript / Node.js / React
          │
          ▼
 Event-Driven Platform
          │
          ▼
    Data Platform
          │
          ▼
      AI Platform
```

Detailed roadmap:

* [`Architecture`](docs/architecture.md)
* [`Features`](docs/features.md)
* [`Roadmap`](docs/roadmap.md)

---

## 🔐 Repository Scope

This repository is a **public engineering and product showcase**, not a mirror of the production server.

It intentionally excludes:

* Credentials and secrets
* Environment configuration
* Database dumps
* Customer and seller data
* Payment credentials
* Private operational data
* Server logs
* Sensitive administration code
* Internal infrastructure configuration
* Proprietary business logic

Selected source code and technical examples may be added progressively after being reviewed and sanitized for public release.

---

## 📈 Project Status

**Status: Active development**

Surfgroupe is an evolving product and engineering project.

The current priority is to strengthen the commerce foundation, improve the delivery and marketplace infrastructure, establish cleaner APIs and progressively introduce the technologies required for larger-scale operations.

---

## 🎯 Vision

The long-term vision is to build more than an online store.

Surfgroupe aims to become a **technology platform for digital commerce in Haiti**, connecting:

**Customers → Sellers → Commerce → Payments → Logistics → Data → AI**

The goal is to build infrastructure that can progressively support more sellers, more products, more locations and increasingly intelligent commerce experiences.

---

## 👨‍💻 Project

**Surfgroupe**
E-commerce & Marketplace Platform

Built as an independent technology and entrepreneurship project with a focus on **software engineering, scalable systems, data and AI**.
