# Phase 1: Product Vision & State of the Art Proposal

**Course:** Software Engineering / Architectural Patterns  
**Project Name:** MangoFilter  
**Team Name:** TouchMyAPI
**Team Members:**  
- Juan Pablo Mora - 0000352321
- Jusselth Chica - 0000351896  
- Santiago Alvarez - 0000348842  
**Submission Date:** 16/8/2026  

---

## Section 1: Executive Summary & Product Vision

### Project Name & Tagline
* **Project Name:** MangoFilter
* **Tagline:** A unified, multi-domain aggregation engine for real-time product price comparison and service deals.

### Core Purpose
MangoFilter is a full-stack web application designed to streamline consumer purchasing and procurement decisions by centralizing real-time price comparisons, delivery speed evaluations, and promotional service bundles from multiple external e-commerce platforms and service providers into a single interface. The platform addresses market fragmentation by leveraging REST APIs and data normalization patterns to provide individual users and businesses with actionable, filtered choices across physical retail and digital/on-demand services.

### Target Audience
* **Primary Persona — Value-Conscious Individual Shoppers:**
  * **Background:** Tech-savvy consumers and university students who frequently purchase products online and subscribe to digital streaming services.
  * **Goals:** Find the best overall deal (product price + shipping fee + delivery speed) without spending excessive time manually cross-checking multiple retail websites.
  * **Pain Points:** Information overload, unexpected shipping costs at checkout, and fragmented promotional bundles across different market portals.
* **Secondary Persona — Small and Medium Enterprises (SMEs / Pequeñas Empresas):**
  * **Background:** Office managers, procurement personnel, and small business owners purchasing operational supplies, hardware, and recurring commercial services.
  * **Goals:** Minimize operational expenses through efficient procurement of equipment and reliable, cost-effective maintenance/cleaning services.
  * **Pain Points:** Time wasted negotiating with fragmented vendor portals and the absence of consolidated pricing tools for recurring commercial expenses.
* **Tertiary Persona — Service & Subscription Seekers:**
  * **Background:** Users looking for cost-effective household services (e.g., domestic cleaning platforms) or optimized streaming bundle plans (e.g., Mercado Play / HBO options).
  * **Goals:** Maximize subscription perks and service quality while minimizing monthly fees.
  * **Pain Points:** Difficulty discovering bundled discounts or comparing non-standardized service tiers.

---

## Section 2: Problem Statement & Motivation

### The Problem
The contemporary e-commerce and digital services landscape suffers from extreme vendor fragmentation. When individual consumers or small business procurement staff search for a specific item or service, they must navigate through multiple isolated platforms, manually track fluctuating prices, compute varied shipping fees, and verify seller credibility. Existing niche comparison tools focus exclusively on narrow verticals (such as specialized computer hardware or smartphone plans), leaving general retail products, office supplies, and local on-demand services without a unified comparison framework.

### Evidence & Context
E-commerce market research consistently indicates that unexpected delivery fees and excessive research time are primary drivers of cart abandonment and purchasing delays. Furthermore, service platforms (such as telecom/streaming packages or commercial maintenance rates) lack standardized data structures, forcing users to evaluate complex offer tiers manually. Standard search engines compound this inefficiency by prioritizing sponsored results and vendor ads over objective user-centric metrics like lowest total cost or fastest delivery time.

### Proposed Solution High-Level Overview
MangoFilter directly solves these inefficiencies through a multi-domain filtering platform:
1. **API-Driven Retail Aggregation:** Connects directly via REST APIs (such as Mercado Libre API and Fake Store API) to dynamically query inventory, pricing, and shipping logistics from merchant catalogs.
2. **Multi-Criteria Optimization Engine:** Enables users to filter and rank search results based on *total landed cost* (base price + shipping fee) and guaranteed *delivery windows*.
3. **Service & Subscription Comparison Vertical:** Extends comparison algorithms to service ecosystems and bundled offerings (e.g., Mercado Play streaming bundles and home cleaning platforms), mapping non-standardized perks into unified comparison cards.

---

## Section 3: Competitive Analysis

### Competitors
1. **Google Shopping (Generalist Product Aggregator):** Large-scale product indexing backed by sponsored search rankings.
2. **PcComponentes / Comprasmartphone.com (Niche Comparison Platforms):** Domain-specific comparison platforms focused on consumer electronics, hardware, and mobile contracts.
3. **Keepa / CamelCamelCamel (Price Tracking Tools):** Amazon-focused tracking software specializing in historical price trend charts.

### Comparison Matrix

| Feature / Criteria | Google Shopping | PcComponentes / Comprasmartphone | Keepa / CamelCamelCamel | **MangoFilter (Proposed)** |
| :--- | :--- | :--- | :--- | :--- |
| **Domain Scope** | General E-commerce | Specific Niche (Tech/Mobile) | Single Platform (Amazon) | **Multi-domain (Retail + Services)** |
| **Real-Time API Fetching** | Merchant Feed Based | Internal Vendor Catalog | Scraped Amazon Data | **Hybrid API / Federated Querying** |
| **Filter by Delivery Speed** | Basic / Limited | Merchant-dependent | No | **First-class Filter Criterion** |
| **Service & Bundle Support** | No | Limited (Telecom only) | No | **Yes (Digital bundles & On-demand)** |
| **Target Audience** | General Consumers | Tech Enthusiasts | Amazon Power Users | **Consumers & SMEs (Pequeñas Empresas)** |
| **Monetization Model** | CPC Ads / Merchant Fee | Direct Sales / Affiliate | Premium Subscriptions | **Affiliate (CPA/CPC) & B2B Partnerships** |

### Gaps in Current Solutions
* **Siloed Verticals:** Existing aggregators force users and small businesses to rely on separate tools for physical retail products versus subscription or home services.
* **Opaque Total Costs:** Current platforms frequently obscure shipping durations and logistics surcharges until late in the checkout workflow.
* **Ad-Biased Rankings:** Major general search portals prioritize paid advertiser placements over true value optimization for the user.

---

## Section 4: State of the Art & Innovation Strategy

### Technical & Domain Research
MangoFilter implements modern architectural patterns for low-latency API aggregation and federated data processing:
* **API Gateway & Microservices Pattern:** Facilitates concurrent querying of heterogeneous third-party APIs without blocking user requests (Fowler, 2014; Richardson, 2018).
* **In-Memory Caching (Redis Layer):** Implemented to store high-frequency product query results, reducing external API rate-limit usage while guaranteeing responsive performance.
* **Data Normalization Adapters:** Utilizes the Adapter/Strategy software design pattern (Gamma et al., 1994) to translate unstructured JSON payloads from third-party REST APIs (e.g., Mercado Libre REST API) into a standardized internal data schema for rapid filtering and sorting.

### Differentiators & Innovation (Unique Value Proposition - UVP)
1. **Cross-Domain Integration:** Unifies physical consumer goods with digital subscription bundles and local service platforms within a single dashboard for individuals and SMEs.
2. **Dual-Metric Optimization:** Simultaneous sorting by total landed cost (item price + logistics) and guaranteed delivery timeframe.
3. **Structured Service Normalization:** Converts non-linear service features (such as streaming perks or service hours) into standardized value scores.

### Initial Feasibility Assessment & Scope Boundaries
* **Technical Constraints & Risks:**
  * *API Rate Limits & Throttling:* Heavy dependence on external endpoints requires robust caching mechanisms and graceful fallback UI degradation.
  * *Data Heterogeneity:* Structuring disparate service types (e.g., streaming subscriptions vs. domestic maintenance) demands a flexible relational/NoSQL schema design.
* **Scope Boundaries for Semester Schedule:**
  * **In Scope (MVP):**
    * Full-stack web application with responsive user interface.
    * Real-time integration with public APIs (Mercado Libre API and DummyJSON API) for product filtering.
    * Integration/Mocking of 1 service ecosystem (e.g., streaming bundle offers or domestic services).
    * Core filtering features based on total cost and delivery speed.
  * **Out of Scope (Future Work):**
    * Native mobile applications (iOS/Android).
    * Web scraping bots for sites lacking public APIs.
    * In-app payment processing for third-party merchants.

---

## References

1. DummyJSON. (2024). *DummyJSON: Free fake REST API for JSON data*. https://dummyjson.com/
2. Fowler, M. (2014). *Microservices: A definition of this new architectural term*. IEEE Software. https://martinfowler.com/articles/microservices.html
3. Gamma, E., Helm, R., Johnson, R., & Vlissides, J. (1994). *Design patterns: Elements of reusable object-oriented software*. Addison-Wesley.
4. Mercado Libre. (2024). *Mercado Libre Developers API Documentation*. https://developers.mercadolibre.com/
5. Richardson, C. (2018). *Microservices patterns: With examples in Java*. Manning Publications.
