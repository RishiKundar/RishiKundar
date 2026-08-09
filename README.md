<div align="center">

# 👨‍💻 Rishi Kundar
### Backend Engineer • Distributed Systems • High-Concurrency Architectures

<a href="https://git.io/typing-svg">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&duration=3000&pause=1000&color=38BDF8&center=true&vCenter=true&width=650&lines=Java+21+%7C+Spring+Boot+3+%7C+Microservices;Apache+Kafka+%7C+PostgreSQL+%7C+Redis;High-Concurrency+%26+Pessimistic+Locking;Enterprise+Banking+Integrations+%40+TCS" alt="Typing SVG" />
</a>

<br/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/rishi-kundar)
[![LeetCode](https://img.shields.io/badge/LeetCode-FFA116?style=for-the-badge&logo=leetcode&logoColor=black)](https://leetcode.com/u/RishiKundar)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:rishi200117@gmail.com)
[![Microsoft Certified](https://img.shields.io/badge/Azure%20Data%20Engineer-0089D6?style=for-the-badge&logo=microsoftazure&logoColor=white)](https://learn.microsoft.com/)

</div>

---

### ⚡ Professional Summary

- 💼 **Software Developer** at **Tata Consultancy Services (TCS)**, engineering high-throughput banking payment pipelines (scaling throughput from **2.5K to 6K TPS** with PostgreSQL query optimization & Redis caching).
- 🚆 **Creator of [Train Booking System](https://github.com/RishiKundar/train-booking-system):** A 6-service event-driven platform handling concurrent ticket reservations using **Apache Kafka**, **Pessimistic Locking (`SELECT ... FOR UPDATE`)**, and **Razorpay** integration.
- 🎯 **Specialized In:** High-concurrency race condition resolution, idempotent API design, distributed transaction synchronization, and reactive edge gateways.

---

### 🛠️ Technical Arsenal

<table>
  <tr>
    <td width="20%"><b>Core & Languages</b></td>
    <td>
      <img src="https://img.shields.io/badge/Java%2021-ED8B00?style=flat-square&logo=openjdk&logoColor=white" />
      <img src="https://img.shields.io/badge/Java%208%2B-ED8B00?style=flat-square&logo=openjdk&logoColor=white" />
      <img src="https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white" />
      <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" />
    </td>
  </tr>
  <tr>
    <td><b>Frameworks & Backend</b></td>
    <td>
      <img src="https://img.shields.io/badge/Spring%20Boot%203-6DB33F?style=flat-square&logo=springboot&logoColor=white" />
      <img src="https://img.shields.io/badge/Spring%20Cloud%20Gateway-6DB33F?style=flat-square&logo=spring&logoColor=white" />
      <img src="https://img.shields.io/badge/Spring%20WebFlux-6DB33F?style=flat-square&logo=spring&logoColor=white" />
      <img src="https://img.shields.io/badge/Spring%20Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white" />
      <img src="https://img.shields.io/badge/Spring%20Data%20JPA-6DB33F?style=flat-square&logo=hibernate&logoColor=white" />
      <img src="https://img.shields.io/badge/Hibernate-59666C?style=flat-square&logo=hibernate&logoColor=white" />
    </td>
  </tr>
  <tr>
    <td><b>Distributed Systems & Messaging</b></td>
    <td>
      <img src="https://img.shields.io/badge/Apache%20Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white" />
      <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white" />
      <img src="https://img.shields.io/badge/Caffeine%20Cache-FF7043?style=flat-square&logo=coffeescript&logoColor=white" />
      <img src="https://img.shields.io/badge/Event--Driven%20Architecture-4B32C3?style=flat-square" />
    </td>
  </tr>
  <tr>
    <td><b>Databases & Migrations</b></td>
    <td>
      <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" />
      <img src="https://img.shields.io/badge/Neon%20DB-00E599?style=flat-square&logo=postgresql&logoColor=black" />
      <img src="https://img.shields.io/badge/Flyway%20Migration-CC0200?style=flat-square&logo=flyway&logoColor=white" />
    </td>
  </tr>
  <tr>
    <td><b>DevOps, Cloud & Tooling</b></td>
    <td>
      <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" />
      <img src="https://img.shields.io/badge/Docker%20Compose-2496ED?style=flat-square&logo=docker&logoColor=white" />
      <img src="https://img.shields.io/badge/Kubernetes%20(Basic)-326CE5?style=flat-square&logo=kubernetes&logoColor=white" />
      <img src="https://img.shields.io/badge/Jenkins-D24939?style=flat-square&logo=jenkins&logoColor=white" />
      <img src="https://img.shields.io/badge/GitLab%20CI-FC6D26?style=flat-square&logo=gitlab&logoColor=white" />
      <img src="https://img.shields.io/badge/OpenShift-EE0000?style=flat-square&logo=redhatopenshift&logoColor=white" />
      <img src="https://img.shields.io/badge/Swagger%20%2F%20OpenAPI%203-85EA2D?style=flat-square&logo=swagger&logoColor=black" />
    </td>
  </tr>
</table>

---

### 🚀 Featured Engineering Project

<div align="center">
  <h3>🚆 <a href="https://github.com/RishiKundar/train-booking-system">Distributed Train Reservation & Payment Platform</a></h3>
</div>

> **Architecture:** 6 Decoupled Microservices (`API Gateway`, `User`, `Train`, `Booking`, `Payment`, `Notification`) + Apache Kafka + Neon PostgreSQL.

- 🔒 **Zero-Overselling Concurrency Engine:** Solved seat booking race conditions with database-level pessimistic locking (`@Lock(LockModeType.PESSIMISTIC_WRITE)`) and `idempotencyKey` checks to eliminate double reservations.
- ⚡ **Asynchronous Event Ingestion:** Kafka-backed event bus returning non-blocking `202 Accepted` responses for instant client feedback under burst traffic.
- 🔄 **Transactional Dual-Write Protection:** Enforced `TransactionSynchronizationManager.registerSynchronization(afterCommit)` to guarantee Kafka event dispatch strictly succeeds local DB commits.
- 💳 **Automated Payment & Compensation:** Razorpay payment lifecycle handling with webhook HMAC-SHA256 signature verification and automated seat rollback on failure.
- 🛡️ **Reactive Edge Gateway:** Spring Cloud Gateway with JWT authentication, RBAC context injection (`X-User-Id`), and Token-Bucket rate limiting via **Bucket4j + Caffeine**.

---

### 📈 Activity & Problem Solving

<div align="center">

#### ⚡ Commit & Contribution Streak
<img src="https://streak-stats.demolab.com?user=RishiKundar&theme=tokyonight&hide_border=true&background=0D1117&ring=38BDF8&fire=38BDF8&currStreakLabel=38BDF8&currStreakNum=38BDF8&sideLabels=94A3B8&sideNums=38BDF8" alt="Rishi's GitHub Streak" width="80%" />

<br/><br/>

#### 📊 12-Month Activity Graph
<img src="https://github-readme-activity-graph.vercel.app/graph?username=RishiKundar&theme=react-dark&bg_color=0D1117&color=38BDF8&line=38BDF8&point=FFFFFF&area=true&hide_border=true" width="90%" alt="Rishi's Contribution Graph" />

<br/><br/>

#### 💡 LeetCode Problem Solving Stats
<a href="https://leetcode.com/u/RishiKundar">
  <img src="https://leetcard.jacoblin.cool/RishiKundar?theme=nord&font=Fira%20Code&ext=heatmap" width="70%" alt="Rishi's LeetCode Stats" />
</a>

</div>

---

<div align="center">
  <b>Looking for a high-impact Backend Engineer?</b><br/>
  📫 Let's connect: <a href="mailto:rishi200117@gmail.com">rishi200117@gmail.com</a> • <a href="https://linkedin.com/in/rishi-kundar">LinkedIn</a>
</div>
