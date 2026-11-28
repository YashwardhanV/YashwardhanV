# Hi, I'm Yashwardhan Verma 👋

### Backend Software Engineer | Java 21 • Spring Boot • PostgreSQL • REST APIs • Multithreading

Backend Software Engineer (B.Tech CSE, 2026) skilled in Java 21, Spring Boot, PostgreSQL, REST APIs and multithreading. Built and tested a webhook delivery service, a Spring Batch reconciliation engine with Gemini AI, and a real-time queue platform.

## About me

- B.Tech in Computer Science Engineering (2026), IPS Academy, Indore.
- Java Developer Intern at Codec Technologies (Jun–Aug 2026):
  - Parallelized independent report queries on a bounded ExecutorService, so reports waited only on the slowest query.
  - Centralized error handling with @RestControllerAdvice: one JSON error format, proper status codes, no leaked stack traces.
  - Cached rarely-changing reference data with Spring Cache, evicting on update so users never saw stale values.
  - Refactored if-else validation into the Strategy pattern, so supporting a new request type meant adding one class.
- I care about the hard parts of backend work: race conditions, idempotency, retries, batch processing and transactional state.
- Every project here is tested against a real PostgreSQL (Testcontainers) and ships with measured numbers, not just a feature list.

## Featured projects

### [SignalDock](https://github.com/YashwardhanV/SignalDock): webhook delivery service
*Java 21 · Spring Boot · PostgreSQL · Docker*
- Engineered a webhook delivery service with idempotent ingestion and a SKIP LOCKED queue; exactly-once claiming verified across 8 concurrent workers and 300 deliveries.
- Cut batch delivery time ~4x (4 s to ~1 s across 4 slow receivers) using virtual threads, and capped each endpoint at 2 in-flight sends so one failing receiver cannot starve the others.
- Hardened reliability with leases, claim tokens, exponential backoff with jitter, a 6 s hard deadline and auto-pause after 5 consecutive dead deliveries, backed by 85 tests including PostgreSQL Testcontainers tests.

### [BalanceTrail](https://github.com/YashwardhanV/Balance-Trail): payment reconciliation engine
*Java 21 · Spring Batch · PostgreSQL · Gemini API*
- Built a Spring Batch payment reconciliation engine that checks gateway files against the ledger in both directions and labels every row with one of 8 outcomes, processing 100K-row settlement files in ~10 s; re-uploading the same file is safe.
- Batched ledger lookups per chunk, cutting database queries 99% (100K to 1K) and runtime 7.5x under network latency; diagnosed a stale query-plan regression, cutting the first run after a large ledger import from 59 s to 13 s.
- Designed Gemini-assisted column mapping for messy gateway files (masked data, schema-validated output, human sign-off), plus Levenshtein-based typo-pair detection that scans 7K x 2K unmatched rows in 0.12 s.

### [LinePilot](https://github.com/YashwardhanV/Line-Pilot): real-time queue platform
*Java 21 · Spring Boot · PostgreSQL · React · Twilio*
- Implemented race-free queue token allocation using SELECT FOR UPDATE SKIP LOCKED and partial unique indexes, cutting contended call-next latency from 2.3 s to 2 ms.
- Streamed live queue boards over SSE and moved position math to the client, saving ~4 SQL queries per viewer per update.
- Wrote 41 automated tests, including Testcontainers race tests on real PostgreSQL; fixed a 1.5x wait-time overestimate for two-staff desks and added after-commit SMS/WhatsApp alerts.

## Tech stack

**Languages:** Java, SQL, TypeScript, JavaScript, C++, C  
**Backend:** Spring Boot, Spring MVC, Spring Data JPA, Hibernate, Spring Batch, Spring Security, REST APIs, Bean Validation  
**Databases:** PostgreSQL, MySQL, Flyway, ACID Transactions, Row-Level Locking, Indexing, Query Optimization  
**Frontend:** React.js, TypeScript, Vite, Tailwind CSS, HTML5, CSS3  
**AI & APIs:** Google Gemini API, Swagger/OpenAPI, Server-Sent Events (SSE), Twilio SMS/WhatsApp, HMAC-SHA256 webhooks  
**Tools & Testing:** Docker, Docker Compose, Git, GitHub Actions (CI/CD), Maven, JUnit 5, Testcontainers, Postman  
**Concepts:** Multithreading, Concurrency, Caching, Design Patterns, Data Structures & Algorithms, OOP, DBMS, System Design

## Achievements

- Team Lead, 1st Runner-Up (2nd place) at HackSangam, a city-wide Hackathon (30+ teams)

## Let's connect

I'm always open to thoughtful conversations, interesting collaborations, and ambitious ideas that deserve to become working software.

[LinkedIn](https://www.linkedin.com/in/yashwardhanv/) · [Portfolio](https://yashwardhan-verma-portfolio.vercel.app) · [Résumé](https://drive.google.com/file/d/1Dx8c6DWl2aaxfu95zWf4DYsE-aG00vpT/view?usp=drivesdk)
