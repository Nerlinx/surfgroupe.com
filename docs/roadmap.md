# Surfgroupe Roadmap

Surfgroupe is being developed incrementally, starting with a local commerce foundation and progressively moving toward a broader technology platform combining commerce, logistics, data, and AI.

## Phase 1 · Commerce Foundation

**Status: In progress / operational foundation**

Core commerce capabilities:

* [x] Product catalog
* [x] Product details
* [x] Shopping cart
* [x] Customer accounts
* [x] Authentication
* [x] Checkout
* [x] Orders
* [x] Product reviews
* [x] Seller infrastructure

## Phase 2 · Localized Delivery

**Status: In progress**

Build a delivery infrastructure adapted to the Haitian market.

* [x] Delivery locations
* [x] City and postal-code support
* [x] Delivery methods
* [x] Delivery pricing
* [x] Delivery estimates
* [x] Location-aware customer experience
* [x] Relay-point infrastructure
* [x] Shipping routes
* [ ] Expand relay-point network
* [ ] Improve delivery tracking
* [ ] Improve logistics analytics

## Phase 3 · Platform Engineering

**Status: In progress**

Strengthen the technical foundation as the platform grows.

* [ ] Consolidate legacy components
* [ ] Improve module boundaries
* [ ] Expand API coverage
* [ ] Improve authentication architecture
* [ ] Improve error handling
* [ ] Improve observability
* [ ] Improve automated testing
* [ ] Strengthen deployment workflows
* [ ] Improve search infrastructure

## Phase 4 · Service-Oriented Architecture

**Status: Planned**

Gradually extract high-value domains from the monolithic application when justified by scale and complexity.

Potential service boundaries include:

```text
Commerce
   │
   ├── Catalog
   ├── Orders
   └── Payments

Marketplace
   │
   └── Sellers

Logistics
   │
   ├── Delivery
   ├── Shipping
   └── Relay Points

Platform
   │
   ├── Authentication
   └── Notifications

Search
   │
   └── Product Discovery
```

The objective is selective separation rather than premature microservices.

## Phase 5 · Modern Web & Mobile Stack

**Status: Planned**

Introduce modern application clients and services where they provide clear value.

* [ ] Node.js services
* [ ] React-based web interfaces
* [ ] Mobile application
* [ ] Shared API layer
* [ ] Improved real-time capabilities
* [ ] Scalable background processing

## Phase 6 · Data Platform

**Status: Planned**

Turn operational data into useful business intelligence.

* [ ] Analytics infrastructure
* [ ] Data pipelines
* [ ] Business dashboards
* [ ] Sales analytics
* [ ] Seller analytics
* [ ] Product analytics
* [ ] Delivery performance analytics
* [ ] Demand analysis
* [ ] Inventory intelligence

Potential technologies may include Python, SQL, R, and modern data-processing tools depending on the use case.

## Phase 7 · AI-Powered Commerce

**Status: Planned**

Introduce AI where it creates measurable value for customers, sellers, and operations.

Potential capabilities:

* [ ] Intelligent product search
* [ ] Product recommendations
* [ ] Personalized discovery
* [ ] Demand forecasting
* [ ] Catalog enrichment
* [ ] AI shopping assistant
* [ ] Seller assistant
* [ ] Logistics optimization

## 🌍 Long-Term Vision

The long-term objective is to evolve Surfgroupe from a commerce application into a broader technology platform combining:

```text
Commerce
   +
Marketplace
   +
Logistics
   +
Data
   +
AI
```

The initial market focus is Haiti.

The technical architecture, however, is being designed with the possibility of supporting broader markets and more complex commerce operations over time.

## Guiding Principle

Surfgroupe will prioritize **useful complexity over architectural complexity**.

New technologies and services should be introduced when they solve a real product, scaling, data, or operational problem.

