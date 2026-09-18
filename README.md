<div align="center">

# 👨‍💻 Rishi Kundar
### Backend Engineer • Distributed Systems • High-Concurrency Architectures

<a href="https://git.io/typing-svg">
<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&duration=3000&pause=1000&color=38BDF8&center=true&vCenter=true&width=700&lines=Java+21+%7C+Spring+Boot+3+%7C+Microservices;Apache+Kafka+%7C+PostgreSQL+%7C+Redis;Concurrency+%7C+Transactions+%7C+Idempotency;Building+Reliable+Backend+Systems" alt="Typing SVG" />
</a>

<br/>

<a href="https://linkedin.com/in/rishi-kundar"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
<a href="https://leetcode.com/u/RishiKundar"><img src="https://img.shields.io/badge/LeetCode-FFA116?style=for-the-badge&logo=leetcode&logoColor=black" alt="LeetCode" /></a>
<a href="mailto:rishi200117@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>
<a href="https://learn.microsoft.com/"><img src="https://img.shields.io/badge/Azure%20Data%20Engineer-0089D6?style=for-the-badge&logo=microsoftazure&logoColor=white" alt="Azure Data Engineer" /></a>

</div>

---

## ⚡ Professional Summary

- 💼 **Software Developer at Tata Consultancy Services (TCS)** working on enterprise banking and payment platforms, with experience in backend performance optimization and production systems.
- 🚆 **Creator of [Distributed Train Reservation & Payment Platform](https://github.com/RishiKundar/train-booking-system)** and **[Scheduly: Distributed Job Scheduler](https://github.com/RishiKundar/scheduly)**.
- 🎯 **Focused on:** concurrency, race-condition prevention, transaction consistency, idempotent APIs, asynchronous processing and resilient backend architecture.

> I enjoy understanding **why systems fail under load** and designing the backend so those failures are handled intentionally.

---

## 🧠 Engineering Focus

```text
                    Backend Engineering
                           │
        ┌──────────────────┼──────────────────┐
        ▼                  ▼                  ▼
 Distributed Systems   Concurrency       Performance
        │                  │                  │
     Kafka              Locking          SQL / Cache
     Events          Idempotency         Optimization
        │                  │                  │
        └──────────────────┼──────────────────┘
                           ▼
                  Reliable Backend Systems
```

---

# 🚀 Featured Engineering Projects

<div align="center">

## 1. Scheduly: Distributed Job Scheduler

<a href="https://github.com/RishiKundar/scheduly"><img src="https://img.shields.io/badge/View%20Repository-181717?style=for-the-badge&logo=github&logoColor=white" alt="View Repository" /></a>

</div>

An **enterprise-grade distributed job scheduling engine** built to handle massive scale. It guarantees at-least-once delivery of HTTP webhooks and prevents duplicate executions across multiple worker nodes using advanced database locking and event streaming.

### 🏗️ Architecture

```text
                     ┌──────────────────┐
                     │ React UI (Vite)  │
                     └────────┬─────────┘
                              │
                              ▼
                ┌──────────────────────────┐
                │      API / Scheduler     │
                │ JWT • SSRF Check • AES   │
                └─────────────┬────────────┘
                              │
             ┌────────────────┼────────────────┐
             ▼                ▼                ▼
     ┌─────────────┐   ┌────────────┐   ┌────────────┐
     │ PostgreSQL  │   │   Kafka    │   │ PostgreSQL │
     │  (Jobs)     │   │ (Outbox)   │   │(Executions)│
     └──────┬──────┘   └──────┬─────┘   └──────┬─────┘
            │                 │                │
            └─────────┐       │       ┌────────┘
                      ▼       ▼       ▼
                  ┌───────────────────────┐
                  │ Worker Nodes (Scale)  │
                  │ FOR UPDATE SKIP LOCKED│
                  └───────────┬───────────┘
                              │
                              ▼
                      ┌───────────────┐
                      │ Target Webhook│
                      └───────────────┘
```

### 🔥 Engineering Problems Solved

**📥 Transactional Outbox Pattern** — Solves the dual-write problem by saving jobs and `OutboxEvent`s in a single ACID transaction, ensuring no data loss before reaching Kafka.

**🔒 Atomic Database Leasing** — Worker nodes utilize pessimistic locking (`FOR UPDATE SKIP LOCKED`) to acquire atomic 30-second leases on jobs, guaranteeing exactly-once execution semantics across distributed workers.

**♻️ Resiliency & Auto-Recovery** — Built-in exponential backoff for failed webhooks, plus a dedicated recovery loop that reclaims "orphaned" jobs if a worker node crashes mid-execution.

**🔐 Bank-Grade Security** — Multi-Tenant JWT authentication and AES-GCM encryption at rest for sensitive API keys and headers.


<br/>

<div align="center">

## 2. Distributed Train Reservation & Payment Platform

<a href="https://github.com/RishiKundar/train-booking-system"><img src="https://img.shields.io/badge/View%20Repository-181717?style=for-the-badge&logo=github&logoColor=white" alt="View Repository" /></a>

</div>

A production-style **event-driven train reservation platform** built to explore real-world backend challenges around concurrent bookings, payment consistency, idempotency, asynchronous workflows and distributed service communication.

### 🏗️ Architecture

```text
                         ┌──────────────────┐
                         │      Client      │
                         └────────┬─────────┘
                                  │
                                  ▼
                    ┌─────────────────────────┐
                    │      API Gateway        │
                    │ JWT • RBAC • RateLimit  │
                    └────────────┬────────────┘
                                 │
             ┌───────────────────┼───────────────────┐
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

**🔒 Concurrent Seat Booking** — Database-level pessimistic locking prevents competing transactions from reserving the same inventory.

```java
@Lock(LockModeType.PESSIMISTIC_WRITE)
Optional<SeatInventory> findById(Long seatId);
```

**🔑 Idempotent APIs** — `idempotencyKey` handling makes retries safe and prevents duplicate logical bookings.

**📨 Event-Driven Processing** — Kafka decouples booking, payment and notification workflows and absorbs burst traffic.

**🔄 Transaction + Event Consistency** — Kafka dispatch is coordinated with successful local transaction completion using Spring transaction synchronization.

**💳 Payment Compensation** — Razorpay webhook verification plus seat rollback handles payment failure after inventory allocation.

**🛡️ Reactive Gateway** — Spring Cloud Gateway provides JWT authentication, RBAC context propagation and token-bucket rate limiting with Bucket4j + Caffeine.

---

# 🛠️ Technical Arsenal

<table>
<tr><td><b>Core & Languages</b></td><td>
<img src="https://img.shields.io/badge/Java%2021-ED8B00?style=flat-square&logo=openjdk&logoColor=white" />
<img src="https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white" />
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" />
</td></tr>
<tr><td><b>Backend</b></td><td>
<img src="https://img.shields.io/badge/Spring%20Boot%203-6DB33F?style=flat-square&logo=springboot&logoColor=white" />
<img src="https://img.shields.io/badge/Spring%20Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white" />
<img src="https://img.shields.io/badge/Spring%20Cloud%20Gateway-6DB33F?style=flat-square&logo=spring&logoColor=white" />
<img src="https://img.shields.io/badge/Spring%20Data%20JPA-6DB33F?style=flat-square&logo=spring&logoColor=white" />
</td></tr>
<tr><td><b>Distributed Systems</b></td><td>
<img src="https://img.shields.io/badge/Apache%20Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white" />
<img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white" />
<img src="https://img.shields.io/badge/Caffeine%20Cache-FF7043?style=flat-square" />
</td></tr>
<tr><td><b>Databases</b></td><td>
<img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" />
<img src="https://img.shields.io/badge/Oracle-F80000?style=flat-square&logo=oracle&logoColor=white" />
<img src="https://img.shields.io/badge/Flyway-CC0200?style=flat-square&logo=flyway&logoColor=white" />
</td></tr>
<tr><td><b>DevOps & Tooling</b></td><td>
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" />
<img src="https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white" />
<img src="https://img.shields.io/badge/Jenkins-D24939?style=flat-square&logo=jenkins&logoColor=white" />
<img src="https://img.shields.io/badge/OpenShift-EE0000?style=flat-square&logo=redhatopenshift&logoColor=white" />
<img src="https://img.shields.io/badge/GitLab%20CI-FC6D26?style=flat-square&logo=gitlab&logoColor=white" />
<img src="https://img.shields.io/badge/Swagger%20%2F%20OpenAPI-85EA2D?style=flat-square&logo=swagger&logoColor=black" />
</td></tr>
</table>

---

# 💼 Professional Experience

### Tata Consultancy Services — Software Developer
**Backend Engineering · Banking & Enterprise Systems**

- Developed and maintained Java/Spring Boot backend services for enterprise platforms.
- Worked with Oracle/PostgreSQL for transactional data processing and backend workflows.
- Optimized database queries and processing pipelines for performance.
- Implemented scheduled processing for payment workflows and enterprise integrations.
- Investigated production issues involving performance, failures and data consistency.
- Worked with CI/CD and enterprise deployment infrastructure in Agile environments.

> **Focus:** reliability · performance · maintainability · production-grade backend engineering

---

# 📈 Activity & Problem Solving

<div align="center">

### ⚡ GitHub Contribution Streak
<img src="https://streak-stats.demolab.com/?user=RishiKundar&theme=tokyonight&hide_border=true&background=0D1117&ring=38BDF8&fire=38BDF8&currStreakLabel=38BDF8&currStreakNum=38BDF8&sideLabels=94A3B8&sideNums=38BDF8" width="80%" alt="Rishi's GitHub Streak" />

<br/><br/>

### 📊 GitHub Activity
<img src="https://github-readme-activity-graph.vercel.app/graph?username=RishiKundar&theme=react-dark&bg_color=0D1117&color=38BDF8&line=38BDF8&point=FFFFFF&area=true&hide_border=true" width="90%" alt="Rishi's GitHub Contribution Graph" />

<br/><br/>

### 💡 LeetCode Progress
<a href="https://leetcode.com/u/RishiKundar">
<img src="https://leetcard.jacoblin.cool/RishiKundar?theme=nord&font=Fira%20Code&ext=heatmap" width="70%" alt="Rishi's LeetCode Stats" />
</a>

</div>

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
