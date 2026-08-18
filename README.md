<div align="center">

# 👨‍💻 Rishi Kundar

### Backend Engineer · Java · Spring Boot · Distributed Systems

<p>
<a href="https://github.com/RishiKundar"><img src="https://img.shields.io/badge/GitHub-RishiKundar-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" /></a>
<a href="https://linkedin.com/in/rishi-kundar"><img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
<a href="https://leetcode.com/u/RishiKundar"><img src="https://img.shields.io/badge/LeetCode-Solve-FFA116?style=for-the-badge&logo=leetcode&logoColor=black" alt="LeetCode" /></a>
<a href="mailto:rishi200117@gmail.com"><img src="https://img.shields.io/badge/Email-Contact-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>
</p>

**Java 21 · Spring Boot 3 · Microservices · Kafka · PostgreSQL · Redis**

</div>

---

## ⚡ About Me

I'm a **Backend Engineer at Tata Consultancy Services (TCS)** focused on building reliable Java backend systems and solving problems around **performance, concurrency, data consistency, and distributed workflows**.

### Engineering Focus

- 🧩 **Backend Architecture** — Spring Boot, REST APIs, microservices
- ⚡ **Concurrency** — race conditions, pessimistic locking, transactions
- 🔄 **Distributed Systems** — asynchronous workflows and event-driven architecture
- 📨 **Messaging** — Apache Kafka, event processing and retries
- 🗄️ **Data Systems** — PostgreSQL, Oracle and SQL optimization
- 🚀 **Performance** — caching and database optimization
- 🔐 **Security** — JWT, RBAC and API authentication
- 💳 **Financial Integrations** — payment and transaction workflows

> I enjoy understanding **why a system fails under load**, not just making it work under normal conditions.

---

## 🧠 Engineering Principles

```text
Correctness before optimization.

Design APIs to survive retries.

Database constraints are part of application correctness.

Make distributed failures explicit.

Measure performance instead of guessing.
```

---

# 🚆 Featured Engineering Project

<div align="center">

## Distributed Train Reservation & Payment Platform

<a href="https://github.com/RishiKundar/train-booking-system">
<img src="https://img.shields.io/badge/View%20Repository-181717?style=for-the-badge&logo=github&logoColor=white" alt="View Repository" />
</a>

</div>

A production-style **event-driven train reservation platform** designed to explore real-world backend problems such as concurrent bookings, payment consistency, idempotency, asynchronous processing, and distributed service communication.

### 🏗️ Architecture

```text
                         ┌──────────────────┐
                         │      Client      │
                         └────────┬─────────┘
                                  │
                                  ▼
                    ┌─────────────────────────┐
                    │      API Gateway        │
                    │ JWT · RBAC · RateLimit  │
                    └────────────┬────────────┘
                                 │
             ┌───────────────────┼───────────────────┐
             │                   │                   │
             ▼                   ▼                   ▼
       ┌───────────┐       ┌───────────┐       ┌───────────┐
       │   User    │       │   Train   │       │  Booking  │
       │  Service  │       │  Service  │       │  Service  │
       └───────────┘       └───────────┘       └─────┬─────┘
                                                      │
                                                      ▼
                                             ┌────────────────┐
                                             │ Apache Kafka   │
                                             └───────┬────────┘
                                                     │
                                      ┌──────────────┼──────────────┐
                                      │              │              │
                                      ▼              ▼              ▼
                               ┌────────────┐ ┌────────────┐ ┌────────────┐
                               │  Payment   │ │Notification│ │  Consumers │
                               │  Service   │ │  Service   │ │  / Events  │
                               └─────┬──────┘ └────────────┘ └────────────┘
                                     │
                                     ▼
                                ┌───────────┐
                                │ Razorpay  │
                                └───────────┘
```

### 🔥 Engineering Problems Solved

**1. Preventing Double Booking**

Concurrent requests can attempt to reserve the same seat simultaneously. The booking service uses database-level pessimistic locking to serialize competing updates.

```java
@Lock(LockModeType.PESSIMISTIC_WRITE)
Optional<SeatInventory> findById(Long seatId);
```

**2. Idempotent Booking Requests**

Clients can retry requests because of network failures or timeouts. An `idempotencyKey` prevents the same logical booking request from being processed multiple times.

```text
Request → idempotencyKey → Existing result? → Return existing result
                         ↘ New request    → Process booking
```

**3. Database + Kafka Consistency**

Kafka event dispatch is coordinated with successful local transaction completion using transaction synchronization, reducing the risk of publishing an event for a database transaction that later rolls back.

**4. Asynchronous Processing**

Kafka decouples booking, payment and notification workflows so downstream processing does not have to remain inside the original request path.

**5. Payment Failure Compensation**

```text
Seat Reserved → Payment Started
                    │
             ┌──────┴──────┐
             ▼             ▼
          Success        Failure
             │             │
             ▼             ▼
          Confirm       Release Seat
```

**6. API Gateway Security**

- JWT authentication
- RBAC context propagation
- Request filtering
- Rate limiting
- Service routing

---

# 🛠️ Tech Stack

### Languages

<p>
<img src="https://img.shields.io/badge/Java%2021-ED8B00?style=flat-square&logo=openjdk&logoColor=white" alt="Java 21" />
<img src="https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white" alt="SQL" />
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" alt="JavaScript" />
</p>

### Backend

<p>
<img src="https://img.shields.io/badge/Spring%20Boot%203-6DB33F?style=flat-square&logo=springboot&logoColor=white" alt="Spring Boot" />
<img src="https://img.shields.io/badge/Spring%20Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white" alt="Spring Security" />
<img src="https://img.shields.io/badge/Spring%20Cloud%20Gateway-6DB33F?style=flat-square&logo=spring&logoColor=white" alt="Spring Cloud Gateway" />
<img src="https://img.shields.io/badge/Spring%20Data%20JPA-6DB33F?style=flat-square&logo=spring&logoColor=white" alt="Spring Data JPA" />
</p>

### Distributed Systems

<p>
<img src="https://img.shields.io/badge/Apache%20Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white" alt="Apache Kafka" />
<img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white" alt="Redis" />
<img src="https://img.shields.io/badge/Caffeine%20Cache-FF7043?style=flat-square" alt="Caffeine Cache" />
</p>

### Databases

<p>
<img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" alt="PostgreSQL" />
<img src="https://img.shields.io/badge/Oracle-F80000?style=flat-square&logo=oracle&logoColor=white" alt="Oracle" />
<img src="https://img.shields.io/badge/Flyway-CC0200?style=flat-square&logo=flyway&logoColor=white" alt="Flyway" />
</p>

### DevOps & Infrastructure

<p>
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker" />
<img src="https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white" alt="Kubernetes" />
<img src="https://img.shields.io/badge/Jenkins-D24939?style=flat-square&logo=jenkins&logoColor=white" alt="Jenkins" />
<img src="https://img.shields.io/badge/OpenShift-EE0000?style=flat-square&logo=redhatopenshift&logoColor=white" alt="OpenShift" />
<img src="https://img.shields.io/badge/GitLab%20CI-FC6D26?style=flat-square&logo=gitlab&logoColor=white" alt="GitLab CI" />
</p>

---

# 💼 Professional Experience

### Tata Consultancy Services — Software Developer

**Backend Engineering · Banking & Enterprise Systems**

- Developed and maintained Java/Spring Boot backend services for enterprise platforms.
- Worked with **Oracle/PostgreSQL** for transactional data processing.
- Optimized database queries and backend processing pipelines.
- Implemented scheduled processing for payment workflows.
- Integrated enterprise authentication and external systems.
- Investigated production issues involving performance, data consistency and failures.
- Worked with CI/CD and enterprise deployment infrastructure in Agile environments.

> **Focus:** reliability · performance · maintainability · production-grade backend engineering

---

# 📌 Featured Links

| Resource | Link |
|---|---|
| 🚆 Train Booking System | [Repository](https://github.com/RishiKundar/train-booking-system) |
| 💻 GitHub | [RishiKundar](https://github.com/RishiKundar) |
| 🧠 LeetCode | [RishiKundar](https://leetcode.com/u/RishiKundar) |
| 💼 LinkedIn | [Rishi Kundar](https://linkedin.com/in/rishi-kundar) |

---

# 🎯 Currently Exploring

```text
✓ Java & JVM Internals
✓ Spring Boot & Spring Security
✓ Distributed Systems
✓ Apache Kafka
✓ Database Concurrency
✓ SQL Optimization
✓ System Design
→ Advanced Distributed Transactions
→ Observability & Resilience Patterns
→ Kubernetes & Cloud-Native Architecture
```

---

<div align="center">

### 💬 Let's Build Something Reliable

<a href="mailto:rishi200117@gmail.com">Email</a> ·
<a href="https://linkedin.com/in/rishi-kundar">LinkedIn</a> ·
<a href="https://github.com/RishiKundar">GitHub</a> ·
<a href="https://leetcode.com/u/RishiKundar">LeetCode</a>

<br/><br/>

**Java · Spring Boot · Distributed Systems · Backend Engineering**

</div>
