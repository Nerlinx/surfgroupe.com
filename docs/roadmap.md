# Surfgroupe Roadmap

Surfgroupe is evolving from a local e-commerce and marketplace application into a scalable technology platform combining commerce, marketplace infrastructure, logistics, data, and artificial intelligence.

The roadmap is intentionally incremental.

The goal is not to replace the existing platform overnight, but to progressively introduce modern architecture where it provides measurable technical or business value.

---

# Phase 1 · Commerce Foundation

**Status: In progress / operational foundation**

Build and stabilize the core commerce platform.

* [x] Product catalog
* [x] Product details
* [x] Shopping cart
* [x] Customer accounts
* [x] Authentication
* [x] Address management
* [x] Checkout
* [x] Orders
* [x] Product reviews
* [x] Seller infrastructure

---

# Phase 2 · Localized Commerce & Logistics

**Status: In progress**

Build delivery infrastructure adapted to the Haitian market.

* [x] Delivery locations
* [x] City and postal-code support
* [x] Delivery methods
* [x] Delivery pricing
* [x] Delivery estimates
* [x] Location-aware customer experience
* [x] Relay-point infrastructure
* [x] Shipping routes
* [ ] Expand the relay-point network
* [ ] Improve shipment tracking
* [ ] Improve logistics operations
* [ ] Introduce logistics analytics

---

# Phase 3 · Platform Stabilization

**Status: In progress**

Strengthen the existing platform before large-scale architectural extraction.

* [ ] Consolidate legacy components
* [ ] Improve module boundaries
* [ ] Standardize application conventions
* [ ] Improve API design
* [ ] Improve authentication architecture
* [ ] Improve validation
* [ ] Improve error handling
* [ ] Improve automated testing
* [ ] Improve observability
* [ ] Strengthen security practices
* [ ] Improve deployment workflows

---

# Phase 4 · API-First Platform

**Status: Planned**

Move toward a stronger API-first architecture.

* [ ] Define domain APIs
* [ ] Standardize API contracts
* [ ] Introduce API versioning
* [ ] Introduce centralized authentication
* [ ] Introduce API Gateway / BFF
* [ ] Establish shared TypeScript contracts
* [ ] Prepare web and mobile clients
* [ ] Decouple frontend applications from legacy presentation logic

Target direction:

```text
Web
Mobile
Admin
Partners
   │
   ▼
API Gateway / BFF
   │
   ▼
Domain Services
```

---

# Phase 5 · Modern TypeScript Stack

**Status: Planned**

Introduce the modern application stack progressively.

## Backend

* [ ] Node.js services
* [ ] TypeScript
* [ ] NestJS or comparable service framework
* [ ] REST APIs
* [ ] Background workers
* [ ] Shared service libraries

## Frontend

* [ ] React
* [ ] Next.js
* [ ] TypeScript
* [ ] Modern component architecture
* [ ] Shared UI system

## Mobile

* [ ] React Native
* [ ] Shared API contracts
* [ ] Mobile commerce experience

---

# Phase 6 · Microservices Architecture

**Status: Planned**

Gradually extract business domains into independently deployable services.

Potential services:

```text
Identity Service
Catalog Service
Cart Service
Order Service
Marketplace Service
Payment Service
Logistics Service
Search Service
Notification Service
Analytics Services
```

Priorities will be based on:

* Business value
* Traffic
* Team ownership
* Reliability requirements
* Deployment frequency
* Domain boundaries

The objective is **selective microservices adoption**, not microservices for their own sake.

---

# Phase 7 · Event-Driven Platform

**Status: Planned**

Introduce asynchronous communication for workflows that benefit from event-driven processing.

Potential events:

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

Potential architecture:

```text
                    Domain Service
                          │
                          ▼
                  Event / Message Bus
                          │
             ┌────────────┼────────────┐
             ▼            ▼            ▼
        Notifications  Logistics    Analytics
```

This will create a foundation for scalable background processing, real-time workflows, analytics, and AI.

---

# Phase 8 · Search Platform

**Status: Planned / evolving**

Improve product discovery independently from the transactional commerce system.

* [ ] Dedicated search service
* [ ] Product indexing pipeline
* [ ] Advanced filtering
* [ ] Ranking
* [ ] Search suggestions
* [ ] Semantic search
* [ ] Multilingual search
* [ ] AI-assisted discovery

---

# Phase 9 · Data Platform

**Status: Planned**

Build a data platform capable of transforming operational data into actionable intelligence.

```text
Operational Services
        │
        ▼
Events / Data Pipelines
        │
        ▼
Data Platform
        │
   ┌────┼────┐
   ▼    ▼    ▼
  BI  Analytics ML
```

Planned capabilities:

* [ ] Data collection
* [ ] Data pipelines
* [ ] Data warehouse / lakehouse
* [ ] Business intelligence
* [ ] Product analytics
* [ ] Seller analytics
* [ ] Customer analytics
* [ ] Delivery analytics
* [ ] Demand analysis
* [ ] Inventory intelligence

Potential technologies:

* Python
* SQL
* R
* Data processing frameworks
* Cloud data infrastructure

---

# Phase 10 · AI Platform

**Status: Planned**

Build AI capabilities on top of the platform's data and service architecture.

## Commerce AI

* [ ] Product recommendations
* [ ] Personalized discovery
* [ ] Intelligent product search
* [ ] Similar-product discovery

## Forecasting

* [ ] Demand forecasting
* [ ] Inventory prediction
* [ ] Sales forecasting

## Customer AI

* [ ] AI shopping assistant
* [ ] Intelligent customer support
* [ ] Personalized experiences

## Seller AI

* [ ] Catalog enrichment
* [ ] Product description assistance
* [ ] Seller insights
* [ ] Demand insights

## Logistics AI

* [ ] Delivery prediction
* [ ] Route optimization
* [ ] Demand-aware logistics
* [ ] Operational anomaly detection

---

# Phase 11 · Cloud & Infrastructure Scaling

**Status: Planned**

Prepare the platform for larger workloads and geographically distributed operations.

Potential capabilities:

* [ ] Containerized services
* [ ] CI/CD pipelines
* [ ] Infrastructure as Code
* [ ] Cloud deployment
* [ ] Kubernetes where justified
* [ ] Horizontal service scaling
* [ ] Distributed caching
* [ ] Message brokers
* [ ] Object storage
* [ ] Centralized logging
* [ ] Metrics
* [ ] Distributed tracing
* [ ] Automated security scanning

Infrastructure choices will remain driven by actual platform requirements.

---

# Target Technology Direction

```text
Frontend
├── TypeScript
├── React
├── Next.js
└── React Native

Backend
├── Node.js
├── TypeScript
├── NestJS
├── REST APIs
├── Event-driven services
└── Microservices

Data
├── SQL
├── Python
├── R
├── Data Pipelines
└── Data Warehouse / Lakehouse

AI
├── Python
├── Machine Learning
├── LLM-based services
├── Recommendation Systems
└── Forecasting

Infrastructure
├── Docker
├── CI/CD
├── Cloud Infrastructure
├── Kubernetes
├── Observability
└── Infrastructure as Code
```

These represent the **target technology direction**. They should not be interpreted as technologies already deployed across the entire Surfgroupe platform.

---

# Long-Term Architecture

The long-term vision is:

```text
                    SURFGROUPE
                         │
          ┌──────────────┼──────────────┐
          │              │              │
         Web           Mobile         APIs
          │              │              │
          └──────────────┼──────────────┘
                         │
                  API Gateway / BFF
                         │
          ┌──────────────┼──────────────┐
          │              │              │
      Commerce      Marketplace     Logistics
          │              │              │
          └──────────────┼──────────────┘
                         │
                  Event / Message Bus
                         │
          ┌──────────────┼──────────────┐
          │              │              │
       Search          Data       Notifications
                         │
                         ▼
                    AI Platform
```

---

# Vision

The long-term objective is to transform Surfgroupe into a scalable technology platform combining:

**Commerce + Marketplace + Logistics + Data + AI**

The initial focus is Haiti.

The architecture is being designed so that the platform can progressively support larger transaction volumes, more sellers, more locations, additional applications, and potentially new markets.

The guiding principle remains:

> **Scale the architecture with the product, not ahead of it.**
