System Overview

REST API for public product browsing

Admin-only endpoints for product management

Designed for scalability, security, and performance

Request Lifecycle

Client sends request

Rate limiting applied

Authentication (if required)

Authorization check for admin routes

Cache lookup for read endpoints

Database query on cache miss

Response returned to client

Authentication & Authorization

JWT access tokens used for admin authentication

Tokens contain user ID and role

Role-based access control enforced at route level

Admin users are created via secure seeding

Caching Strategy

Product list and product detail endpoints cached

Cache keys include pagination and filter parameters

Time-based expiration (TTL)

Cache invalidated on product create/update/delete

Rate Limiting Strategy

IP-based limits for public endpoints

User-based limits for authenticated endpoints

Redis used for distributed rate limit counters

Data Modeling Decisions

Products are not user-owned

Soft deletes used for product deactivation

Indexed fields for common filters (category, price, active status)

API Versioning

All endpoints namespaced under /v1

Breaking changes introduced via new versions

Tradeoffs & Non-Goals

No full-text search

No user ordering system

No admin UI (API-only)