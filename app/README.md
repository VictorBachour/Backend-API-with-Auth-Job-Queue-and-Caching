Scalable REST API for public product browsing with authenticated admin management, caching, and rate limiting.

Features

Public product listing and product detail endpoints

Paginated and filterable product queries

JWT-based authentication for admin users

Role-based access control (admin vs user)

Redis caching for read-heavy endpoints

User- and IP-based rate limiting

PostgreSQL as primary datastore

OpenAPI (Swagger) documentation

API versioning (/v1)

Tech Stack

Backend: FastAPI (Python)

Database: PostgreSQL

Cache / Rate Limiting: Redis

Authentication: JWT (access tokens)

API Docs: OpenAPI / Swagger

Architecture Overview

Requests flow through rate limiting and authentication

Public product reads are served from Redis cache when available

PostgreSQL is the source of truth

Cache invalidation occurs on product create/update/delete

Authorization is enforced at the API boundary

Security Decisions

Product browsing is public

Admin users authenticate via JWT

Admin accounts are provisioned via database seeding

No API endpoint exists for role elevation

Passwords are securely hashed

Performance & Scaling

Redis caching reduces database load on read-heavy endpoints

Pagination prevents unbounded queries

Rate limiting protects against abuse

API Documentation

Interactive Swagger UI available at runtime