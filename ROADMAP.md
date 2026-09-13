# The Roadmap — BAM-First, Fallback-Ready

**Master Strategy:** Become an elite candidate for Bank Al-Maghrib's Core Banking recruitment, while building a profile that is automatically strong for CDG, Ministries, and major banks. BAM is the primary target. Everything else is a launchpad or safety net.

**Mental Model:** Compounding despite imperfect execution. Patience + daily discipline.

**Financial Rule:** Lifestyle works on salary alone. Everything else is upside. Do not anchor on unverified numbers.

---

## Reality of BAM

- BAM recruits through position-specific recruitment competitions/processes.
- The exact written/oral process depends on each announcement.
- Some openings are formal concours on emploi-public.ma; others are application → présélection → interview.
- Read each arrêté carefully.
- Recent openings: Core Banking (2), E&D/Support (4), Cloud (2), Infrastructure (2), Systems (2), Networks & Telecom.
- Eligibility: Moroccan national, Bac+5 in CS/IS or equivalent.
- Compensation: not publicly disclosed by specialization. Do not anchor on an assumed number. Verify during recruitment.

---

## The System

- Weekly unit: one concept → one small project → one written explanation → one interview question.
- Every day: one commit.
- Never two days off in a row. Bad days get 10 minutes, not zero.
- Every concept used three times: learn → exercise same day → real project within a week.
- Notes in your own words: what it is, what problem it solves, a snippet you wrote, when you'd use it, when you wouldn't, one failure mode.
- 12-year-old test: close the notes, explain out loud. Stumble = you don't have it.
- Sunday checkpoint (20 min): Does it run? Can I explain it without notes? Is my energy okay? Two bad Sundays → cut scope, not increase effort.
- Monthly review (60 min): Portfolio, CV, applications, gaps, energy.
- Debugging journal: symptom → cause → fix → prevention.
- From Month 3: applications are part of the weekly unit.

---

## The 6-Month Program

4–5h/day. One hour English daily. Competence, not calendar.

### Month 1 — Java + SQL + Git + Linux + Networking

| Week | Learn | Build |
|------|-------|-------|
| 1 | Types, control flow, methods, classes. Git, terminal. Linux basics. | Tiny calculator |
| 2 | OOP: interfaces, inheritance vs composition, packages | Small inventory model |
| 3 | Collections, generics, equals/hashCode | Phone book app |
| 4 | Exceptions, file I/O, JUnit. SQL: joins, subqueries, aggregation, constraints. Networking: TCP/IP, DNS, HTTP/HTTPS, TLS, ports, sockets | CSV parser + SQL queries |

Concours track: Bookmark bkam.csod.com and emploi-public.ma. Check weekly. Begin degree equivalence if needed.

### Month 2 — Spring Boot + PostgreSQL + Transactions

| Week | Learn | Build |
|------|-------|-------|
| 5 | Maven, Spring Core, DI, beans, configuration | Spring CLI or REST hello-world |
| 6 | Spring Web, REST, validation, error handling, OpenAPI | CRUD REST API |
| 7 | JPA/Hibernate, entities, relations, N+1, PostgreSQL, Flyway | Persist API to PostgreSQL |
| 8 | Database internals: indexes, B-trees, execution plans, locking, MVCC, isolation levels, deadlocks, optimistic/pessimistic locking, connection pools | Project 1 deployed |

Project 1 must include: Spring Boot REST API, PostgreSQL, JPA, validation + error handling, JUnit tests, Dockerfile/compose, README, OpenAPI, live URL, clean commits.

Checkpoint: trace request → controller → service → repository → PostgreSQL. Explain isolation levels and concurrent updates.

### Month 3 — Security, Architecture, Scrum, Apply

| Week | Focus |
|------|-------|
| 9 | Spring Security: JWT, auth, roles. CI with GitHub Actions. |
| 10 | Architecture: SOLID, composition, dependency inversion, layered + hexagonal. UML: class and sequence diagrams. Scrum: roles, ceremonies, artifacts, user stories. |
| 11 | LeetCode easy (30–50). Java/Spring interview questions. CV French + English. LinkedIn. GitHub profile. |
| 12 | Apply: 30–40 applications. ESNs, startups, CDG ecosystem, internships, alternance, junior roles. |

Month 3 checkpoint: clean OOP and collections, Spring Boot REST + JPA + PostgreSQL, JUnit + Mockito, Git/Maven/Docker basics, SQL joins/indexes/transactions/isolation, deployed live project, LeetCode easy, basic architecture, 10-minute project explanation without notes.

### Month 4 — Banking + Payments + Messaging

| Week | Learn | Build |
|------|-------|-------|
| 13 | Banking: account/journal, debit/credit, double-entry, settlement, clearing, reconciliation, rejects, reversals, auditability, transaction lifecycle | Extend Project 1 with ledger concepts |
| 14 | Payments: ISO 20022, SWIFT concepts, ISO 8583 basics, payment messaging, settlement/reconciliation | Simple payment message parser |
| 15 | Messaging: Kafka — queues, producer/consumer, retries, ordering, DLQ, idempotent consumers. IBM MQ: acknowledgement, persistence, delivery semantics, DLQ, transaction/message coupling, MQ vs Kafka | Kafka producer/consumer with DLQ |
| 16 | Integration: REST, gRPC, API gateways, event streaming. Enterprise file transfer / batch integration concepts | Document integration patterns |

Concours track: 2–3h/week on general IT knowledge, logic, QCMs, algorithms, SQL, Java, networks, OS, databases, software engineering, cybersecurity, logical reasoning.

### Month 5 — Core Banking Flagship + System Design + Debugging

Core Banking Simulation:

    Customer → Account → Journal → Transaction → Posting → Balance
    Payment message → Validation → Posting → Journal → Settlement → Reconciliation

Simulate: duplicate message, message delivered twice, failed DB transaction, partial processing, reversal, invalid account, insufficient funds, out-of-order message, EOD failure, reconciliation mismatch.

EOD/EOM processing:

    EOD → Validate → Close business day → Generate journal outputs → Reconcile → Produce exceptions → Archive

Make it safe to rerun. Ask: EOD crashes at 70%. What happens on restart?

System design: consistency, availability, idempotency, partitioning, retries, ordering, eventual consistency, isolation, caching, backpressure, failure recovery. Outbox, saga, CQRS, event sourcing, DLQ, circuit breakers.

Debugging: break things deliberately — connection failures, slow queries, deadlocks, rollbacks, duplicate requests, stale data, expired JWTs, failed migrations, timeouts, webhooks twice, container restarts.

Concours track: if BAM opens, switch to 30–40% concours preparation immediately.

### Month 6 — Distributed Systems + Production + Concours/Interviews

- LeetCode medium
- Spring + system design interview prep
- CV polished around 3 projects with live links
- 60–100 applications sent
- Freelance first offer: "Spring Boot REST API with auth, tests and deployment," 2,000–4,000 DH
- Depth (prioritized): Kafka, JVM profiling, database internals, observability, Linux, networking
- Secondary: Kubernetes, Terraform, Prometheus/Grafana, contract/mutation/load testing, Redis
- Rest, review, fill gaps
- Concours application: if a BAM or MEF opening appears, apply immediately

---

## Flagship Architecture

    Payment API
        ↓
    PostgreSQL
        ↓
    Outbox
        ↓
    Kafka
        ↓
    Transaction Processor
        ↓
    Ledger
        ↓
    Reconciliation

    Kafka → Retry → DLQ

Demonstrates: transactional database + event-driven architecture + financial consistency.

---

## Concours Track

Normal period: 2–3h/week on general IT knowledge, logic, QCMs, algorithms, SQL, Java, networks, OS, databases, software engineering, cybersecurity fundamentals, logical reasoning.

Once BAM opens: switch to 30–40% concours preparation while maintaining the technical program.

Study the exact written-exam format, duration, and subjects from the arrêté attached to each BAM opening. The announcement is authoritative.

Prepare dossier early: diploma copies, CV, administrative documents. Begin degree equivalence in Month 1–2.

Oral interview prep: Core Banking simulation is the strongest asset. Practice a 10-minute explanation focused on failure modes, idempotency, reconciliation, EOD.

---

## Fallback & Secondary Targets

- CDG Group (DXC CDG) — Best first-job target. Junior Java (1–3 years exp), Java/Spring/Spring Boot/REST.
- Ministries (MEF, Interior, Foreign Affairs) — Ingénieur d'État, IT development, Génie Logiciel. Diplôme d'Ingénieur d'État or equivalent, age < 45. Monitor emploi-public.ma.
- Other banks (CIH, SG ATS, Attijariwafa) — Strong brands, financial domain experience. Apply from Month 3.
- ESNs (Capgemini, ALTEN, NTT DATA, Sopra Steria, Devoteam) — Volume hiring, brand prestige. Stay 1–2 years, move up.

---

## Career Progression

- Year 1 — Own a service, not tickets. On-call. Domain: settlement, reconciliation, ISO 20022, ISO 8583, PCI-DSS. Emergency fund 6–12 months. Problems file. Keep one small client alive.
- Year 2 — Identity: "Java backend — payments/financial systems." Kafka, Redis, distributed systems, observability. Write publicly. Contacts at 2–3 institutions. Freelance 1,500–2,500 DH/day.
- Year 3 — Switch when market value justifies it. Targets: CDG Capital, BAM, AMMC.
- Years 4–15 — Architecture → mentor → staff/principal or chef de service.

Primary identity: Java Backend Engineer → Financial Systems → Core Banking/Payments → Distributed Systems → Senior/Expert/Architect.

---

## What Decides the Outcome

1. The system — daily commits, weekly unit, two-day rule, visible progress.
2. Completing the program — competence, not calendar.
3. English daily, converted into technical communication.
4. Specialized identity by end of Year 2.
5. Owning production systems — hard to replace, AI-durable.
6. Switching when the curve stalls.
7. Energy, sleep, health.
8. Network and public proof.
9. Patience with BAM — it's a recruitment process, a long game.
