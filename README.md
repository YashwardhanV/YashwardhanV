# Hi, I'm Yashwardhan Verma 👋

### Backend Software Engineer | Java 21 • Spring Boot • PostgreSQL • React

I build backend systems that stay correct under concurrency and failure, and I measure them to prove it.

## About me

- B.Tech in Computer Science Engineering (2026), IPS Academy, Indore.
- Java Developer Intern at Codec Technologies (Jun–Aug 2026): used ExecutorService, Spring Cache and the Strategy pattern to cut report generation time by ~40% and API latency by ~30%.
- I care about the hard parts of backend work: race conditions, idempotency, retries, batch processing and transactional state.
- Every project here is tested against a real PostgreSQL (Testcontainers) and ships with measured numbers, not just a feature list.

## Featured projects

### [SignalDock](https://github.com/YashwardhanV/SignalDock): webhook delivery service
*Java 21 · Spring Boot · PostgreSQL · React · Docker*
- Idempotent event ingestion and a `SKIP LOCKED` queue, with exactly-once claiming verified across 8 concurrent workers and 300 deliveries.
- Cut batch delivery time about 4x (4 s to ~1 s across 4 slow receivers) using virtual threads, and capped each endpoint at 2 in-flight sends so one failing receiver can't starve the others.
- Leases, claim tokens, exponential backoff with jitter, a 6 s hard deadline and auto-pause after 5 consecutive dead deliveries, backed by 85 tests including real-PostgreSQL Testcontainers tests.

### [BalanceTrail](https://github.com/YashwardhanV/Balance-Trail): payment reconciliation engine
*Java 21 · Spring Batch · PostgreSQL · Gemini API · React*
- Checks gateway files against the ledger in both directions and labels every row with one of 8 outcomes. Processes 100K-row settlement files in about 10 seconds, and re-uploading the same file is safe.
- Batched ledger lookups per chunk, cutting database queries 99% (100K to 1K) and runtime 7.5x under network latency. Diagnosed a stale query-plan regression, cutting the first run after a large ledger import from 59 s to 13 s.
- Gemini-assisted column mapping for messy gateway files (masked data, schema-validated output, human sign-off), plus Levenshtein-based typo-pair detection that scans 7K×2K unmatched rows in 0.12 s.

### [LinePilot](https://github.com/YashwardhanV/Line-Pilot): real-time queue platform
*Java 21 · Spring Boot · PostgreSQL · React · Server-Sent Events · Twilio*
- Race-free token allocation using `SELECT FOR UPDATE SKIP LOCKED` and partial unique indexes, cutting contended call-next latency from 2.3 s to 2 ms.
- Live queue boards over Server-Sent Events, with position math moved to the client, removing about 4 SQL queries per viewer on every update.
- 41 automated tests, including Testcontainers race tests on real PostgreSQL. Fixed a 1.5x wait-time overestimate for two-staff desks and added after-commit SMS/WhatsApp alerts.

## Tech stack

**Languages:** Java, SQL, TypeScript, JavaScript, C++, C  
**Backend:** Spring Boot, Spring Batch, Spring Security, JPA/Hibernate, REST APIs, Virtual Threads, Spring Cache, Server-Sent Events  
**Databases:** PostgreSQL, MySQL, Flyway, ACID transactions, row-level locking (`SKIP LOCKED`), partial unique indexes  
**Frontend:** React, TypeScript, Vite, Tailwind CSS  
**AI & integrations:** Google Gemini API (structured JSON output), Twilio SMS/WhatsApp, HMAC-SHA256 signed webhooks  
**Tools & testing:** Docker, Docker Compose, Git, GitHub Actions (CI/CD), Maven, JUnit 5, Testcontainers, Postman

## Let's connect

I'm always open to thoughtful conversations, interesting collaborations, and ambitious ideas that deserve to become working software.

[LinkedIn](https://www.linkedin.com/in/yashwardhanv/) · [Portfolio](https://yashwardhan-verma-portfolio.vercel.app) · [Résumé](https://drive.google.com/file/d/1Dx8c6DWl2aaxfu95zWf4DYsE-aG00vpT/view?usp=drivesdk)
