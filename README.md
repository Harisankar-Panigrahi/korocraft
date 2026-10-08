# KoroCraft — Automated Dropshipping & Multi-Channel Sourcing Platform

An enterprise-grade automated dropshipping and multi-channel fulfillment engine designed for high-throughput online merchants, integrating supplier APIs, real-time inventory tracking, and dynamic order dispatching.

> **Proprietary Client Project — Portfolio Case Study**  
> *This repository is maintained exclusively for portfolio demonstration, evaluation, and professional reference. The production application source code and infrastructure configuration are proprietary and intentionally excluded.*

---

## Overview

**KoroCraft** is an automated e-commerce operations and supply-chain middleware platform engineered for international merchants scaling high-velocity dropshipping operations.

The platform eliminates manual order processing, stock desynchronization, and fulfillment delays by directly connecting online storefronts with global manufacturer and dropshipping supplier networks (including CJ Dropshipping API). 

It automates the complete operational lifecycle:
- **Merchant Onboarding:** Secure OAuth/token-based store verification and multi-channel store authentication.
- **Inventory Sync:** Automated polling and webhooks keeping stock counts and price adjustments synchronized across all channels.
- **Automated Order Routing:** Sub-second ingestion of customer purchases with automatic line-item purchase order generation sent directly to supplier fulfillment lines.
- **Tracking Aggregation:** Real-time collection and customer notification of international package tracking numbers without human intervention.

---

## Project Highlights

- **Automated Supplier API Integration:** Seamless, authenticated handshake with supplier APIs (e.g., CJ Dropshipping) for automated catalog import and order creation.
- **Real-Time Two-Way Sync:** Sub-second inventory count and price adjustment synchronization, eliminating costly out-of-stock orders.
- **Event-Driven Webhook Pipeline:** High-throughput order ingestion processing hundreds of concurrent purchases during sales spikes.
- **Dynamic Profit Margin Engine:** Automated pricing rules factoring in supplier base costs, shipping tiers, payment processing fees, and target margins.
- **Intelligent SKU Normalization:** Multi-variant product catalog mapping linking merchant store variants to supplier manufacturer SKUs.
- **Tracking Number Aggregation:** Automatic tracking code polling and instant status updates dispatched to customers via email and SMS.
- **Resilient Background Job Queue:** Redis-backed worker architecture with exponential retry backoff and fault-tolerant rate-limit throttling.
- **Merchant Operations Telemetry:** Real-time analytics dashboard monitoring fulfillment cycle times, supplier fulfillment rates, and margin performance.

---

## Business Problem

Growing e-commerce businesses face severe operational bottlenecks when scaling dropshipping models:

- **Inventory Desynchronization:** Out-of-stock items on the supplier side remain listed on storefronts, causing failed customer orders, refund fees, and chargeback penalties.
- **Manual Fulfillment Bottlenecks:** Staff spending hours manually copying customer shipping addresses into supplier portals, creating 24–48 hour fulfillment delays.
- **Fragmented Tracking Numbers:** Multi-item orders shipped from different supplier warehouses require manual coordination, leading to high support ticket volumes.
- **Currency & Margin Volatility:** Fluctuating international exchange rates and supplier base price shifts silently erode merchant profitability without automated price guardrails.

---

## Solution

The platform resolves these vulnerabilities by replacing fragmented manual operations with an automated, synchronized digital workflow:

1. **Authenticated Store Connection:** Merchants authenticate their storefront with encrypted API tokens and automated store verification.
2. **Automated Catalog Sourcing:** Products and variants are imported with normalized SKU mappings and dynamic profit margin calculations.
3. **Instant Order Ingestion:** New customer orders trigger authenticated webhooks, queuing line-item orders into a high-concurrency Redis worker pool.
4. **Autonomous Supplier Dispatch:** The engine formats, validates, and dispatches purchase orders directly to supplier fulfillment APIs.
5. **Continuous Tracking Loop:** Background workers monitor fulfillment milestones and push tracking codes back to the merchant storefront and customer.

---

## Key Features

- **Store Verification & Authorization:** Secure API token verification and active store status management.
- **Dynamic SKU Mapping Engine:** Multi-variant product mapping linking merchant variants to supplier catalog IDs.
- **Automated Order Routing:** Autonomous order submission directly to supplier fulfillment queues upon payment capture.
- **Currency & Profit Margin Rules:** Dynamic markup rules based on product categories, base costs, and shipping weights.
- **Failover & Retry Architecture:** Resilient worker queues handling supplier API downtime with exponential backoff and dead-letter queues.
- **Order Status Telemetry:** Complete audit log tracking every stage from order creation to supplier fulfillment and courier handover.
- **Customer Notification Dispatch:** Automatic order status and tracking email triggers with localized tracking URLs.

---

## Architecture & Technology Stack

The platform implements an event-driven microservices architecture:

- **Presentation Layer:** Responsive React & TypeScript operations portal built with Tailwind CSS and Vite.
- **API & Integration Gateway:** Node.js / Express RESTful engine with JWT authentication and multi-tenant store isolation.
- **Queue & Worker Engine:** Redis-backed asynchronous worker queues (BullMQ) managing rate-limited supplier API communications.
- **Data & Persistence Layer:** PostgreSQL database with Prisma ORM managing normalized order states, vendor credentials, and immutable synchronization audit logs.

---

## My Role

As the **Lead Full-Stack & Integration Engineer**, I architected and implemented the end-to-end KoroCraft platform:

- **Integration Architecture:** Designed the supplier API integration pipeline, authentication token state machines, and webhook dispatchers.
- **Resilient Worker Queue:** Engineered high-concurrency background job processing with rate-limiting compliance and retry mechanisms.
- **Database Architecture:** Modeled the relational database schema for multi-store merchants, product variant mappings, and order logs.
- **Operations Dashboard:** Developed the responsive merchant dashboard in React and TypeScript for real-time fulfillment telemetry.
- **API Security:** Implemented cryptographic signature verification on incoming storefront webhooks and secure credential storage.
