<div align="center">

# Juan Camilo Marín García
### Ingeniero de Sistemas | Arquitectura de Datos, SQL Tuning & Desarrollo Backend (.NET / Python)
📍 **Colombia** (Disponible para proyectos remotos, híbridos o consultoría técnica especializada)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Conectar-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/camilo-marin-ingeniero)
[![Email](https://img.shields.io/badge/Email-Contáctame-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:juancmaringcu@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-DerekMazino-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/DerekMazino)

🌐 **[Versión en Español](#-versión-en-español)** | **[Read in English](#-english-version)**

</div>

---

<a name="-versión-en-español"></a>
## 👨‍💻 Perfil Profesional

Ingeniero de Sistemas (UIS) con **más de 4 años de experiencia** diseñando, optimizando y escalando sistemas transaccionales y arquitecturas de datos de alto volumen en sectores críticos como servicios públicos, banca/finanzas y tecnología.

Combino una sólida especialización en **Ingeniería de Bases de Datos (Oracle PL/SQL, SQL Server, Tuning CBO)** con **Desarrollo Backend (.NET 8, Python)**. Aplico patrones como **CQRS**, **Transactional Outbox** y **Change Data Capture (CDC)** para eliminar cuellos de botella de rendimiento, reducir latencias en procesos analíticos y masivos (facturación electrónica, pipelines de extracción y cierres contables) y asegurar la consistencia transaccional bajo alta concurrencia.

---

## 🛠️ Portafolio de Servicios y Especialización

* **⚡ Optimización y Tuning de Bases de Datos (Oracle / SQL Server):** Diagnóstico profundo de planes de ejecución (`DBMS_XPLAN`), optimización de costos en el CBO, particionamiento físico de grandes volúmenes, índices de cobertura y procesamiento vectorizado por lotes en PL/SQL (`BULK COLLECT` / `FORALL`).
* **🔄 Arquitecturas de Datos Orientadas a Eventos:** Desacoplamiento de motores transaccionales (OLTP) de cargas analíticas mediante **CQRS**, **Transactional Outbox**, mensajería durable con **RabbitMQ** y proyecciones en bases documentales (**MongoDB**).
* **🐍 Pipelines de Datos, CDC & Automatización con Python:** Construcción de flujos ETL/ELT con validación estricta de esquemas (**Pydantic v2**), motores de Change Data Capture para tracking de estados y auditoría histórica, y automatización de reportes (HTML responsivo / Excel).
* **⚙️ Backend Empresarial & Tiempo Real:** Servicios y workers asíncronos en **.NET 8 (C#)**, servidores de comunicación bidireccional de baja latencia vía **WebSockets**, y sistemas de facturación electrónica.
* **🚀 Gobierno Técnico & Versionamiento SQL:** Control de versiones de bases de datos (**Git Flow**, **Redgate**), contenedores reproducibles con **Docker** y documentación técnica exhaustiva.

---

## 📌 Proyectos Destacados (Portafolio Técnico)

### 1. ⚡ [Database Performance Benchmarking & Refactoring Suite](https://github.com/DerekMazino/db-performance-benchmark)
> **Laboratorio reproducible de optimización SQL y tuning físico sobre un libro mayor transaccional de 10,000,000 de registros.**
* **Tecnologías:** `Oracle 23ai Free` | `PL/SQL` | `CBO Tuning` | `Interval Partitioning` | `Docker`
* **Métricas e Impacto Empírico:**
  * **Sargabilidad e Índices de Cobertura:** Reducción de latencia de consulta de **13.60 s a 0.01 s (1,360x más rápido)** y disminución del I/O lógico en memoria RAM en un **99.95%** (de 157,000 a 67 bloques).
  * **Batch Processing Vectorizado en PL/SQL:** Reemplazo de cursores fila-por-fila por `BULK COLLECT LIMIT 5000` + `FORALL ... SAVE EXCEPTIONS`, logrando **2.39x mayor velocidad** y un **99.98% menos context switching** entre motores.
  * **Partition Pruning Físico:** Implementación de particionamiento mensual automático, acelerando reportes analíticos **9.4x (de 10.56 s a 1.12 s)** y reduciendo el I/O de disco en un **91.3%**.

### 2. 🔄 [Event-Driven Read Model Sync (CQRS & Transactional Outbox)](https://github.com/DerekMazino/event-driven-cqrs-sync)
> **Arquitectura desacoplada orientada a eventos para proteger un motor OLTP financiero de alta concurrencia frente al bloqueo por consultas pesadas.**
* **Tecnologías:** `Oracle 23ai` | `.NET 8 Worker Services` | `RabbitMQ (AMQP)` | `MongoDB 7.0` | `Docker`
* **Métricas e Impacto Empírico:**
  * **Entrega Garantizada sin Bloqueos Distribuidos:** Implementación de **Transactional Outbox** atómico en PL/SQL y workers concurrentes en `.NET 8` (`SELECT FOR UPDATE SKIP LOCKED`).
  * **Proyecciones Idempotentes en Lectura:** Sincronización asíncrona de 50k préstamos y 600k cuotas hacia documentos pre-agregados en **MongoDB**.
  * **Diferencial de Rendimiento:** Reducción de latencia de lectura en **más del 99% (de 850 ms en uniones relacionales a 1–5 ms en MongoDB)**, con aislamiento total del motor transaccional ante contención de bloqueos.

### 3. 🏠 [Real Estate Investment Monitor & CDC Engine](https://github.com/DerekMazino/real-estate-monitor)
> **Pipeline automatizado de extracción, Change Data Capture (CDC) y detección de oportunidades de inversión inmobiliaria en Colombia.**
* **Tecnologías:** `Python 3.11+` | `Pydantic v2` | `SQLite Relational` | `CDC Pattern` | `SMTP / Excel`
* **Arquitectura y Capacidades de Negocio:**
  * **Motor CDC para Variaciones de Precio:** Detección de nuevas propiedades y registro histórico de rebajas de precio con cálculo porcentual de descuento almacenado en `price_history`.
  * **Ingeniería de Datos con Validación Estricta:** Ingesta y normalización de listados desde múltiples portales inmobiliarios (Finca Raíz, MetroCuadrado, Ciencuadras) mediante modelos **Pydantic v2** y deduplicación estricta de publicaciones.
  * **Distribución Multicanal Desacoplada:** Generación automática de planillas analíticas estructuradas en `.xlsx` y envíos de alertas programadas vía correo electrónico (HTML responsivo vía SMTP).

### 4. 🚧 Próximo Proyecto: Sistema POS Agnóstico al Negocio *(En Análisis y Planeación)*
> **Arquitectura de Punto de Venta (POS) multi-nicho orientada a la adaptabilidad de dominio y alta fiabilidad transaccional.**
* **Enfoque Técnico:** Modelado de dominio con límites desacoplados y esquemas de metadatos dinámicos para que el núcleo de facturación, impuestos, inventario y sincronización opere sobre retail, servicios o gastronomía sin alterar la lógica de negocio base.

---

## 💻 Stack Tecnológico y Herramientas

<div align="center">

| Especialidad | Tecnologías |
| :--- | :--- |
| **Bases de Datos Relacionales** | ![Oracle 23ai / 19c](https://img.shields.io/badge/Oracle_Database-F80000?style=flat-square&logo=oracle&logoColor=white) ![SQL Server](https://img.shields.io/badge/SQL_Server-CC2927?style=flat-square&logo=microsoft-sql-server&logoColor=white) ![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white) ![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white) |
| **NoSQL & Mensajería** | ![MongoDB](https://img.shields.io/badge/MongoDB_7.0-47A248?style=flat-square&logo=mongodb&logoColor=white) ![RabbitMQ](https://img.shields.io/badge/RabbitMQ_AMQP-FF6600?style=flat-square&logo=rabbitmq&logoColor=white) ![WebSockets](https://img.shields.io/badge/WebSockets-010101?style=flat-square) |
| **Lenguajes de Programación** | ![PL/SQL](https://img.shields.io/badge/PL%2FSQL-F80000?style=flat-square&logo=oracle&logoColor=white) ![SQL](https://img.shields.io/badge/SQL-003B57?style=flat-square&logo=postgresql&logoColor=white) ![Python](https://img.shields.io/badge/Python_3.11+-3776AB?style=flat-square&logo=python&logoColor=white) ![C#](https://img.shields.io/badge/C%23-239120?style=flat-square&logo=c-sharp&logoColor=white) ![Java](https://img.shields.io/badge/Java-007396?style=flat-square&logo=java&logoColor=white) |
| **Frameworks & Modelado** | ![.NET 8](https://img.shields.io/badge/.NET_8_Worker_Services-512BD4?style=flat-square&logo=dotnet&logoColor=white) ![Pydantic v2](https://img.shields.io/badge/Pydantic_v2-E92063?style=flat-square&logo=pydantic&logoColor=white) ![Pandas / OpenPyXL](https://img.shields.io/badge/Excel_Data_Pipelines-217346?style=flat-square&logo=microsoft-excel&logoColor=white) |
| **DevOps & Ciclo de Vida** | ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![Git Flow](https://img.shields.io/badge/Git_Flow-F05032?style=flat-square&logo=git&logoColor=white) ![Redgate](https://img.shields.io/badge/Redgate-CC0000?style=flat-square) ![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black) |

</div>

---

<a name="-english-version"></a>
<details>
<summary><b>🇺🇸 Click here to expand the English Version (Portfolio & Resume Summary)</b></summary>
<br>

### 👨‍💻 Executive Summary
Systems Engineer based in **Colombia** with **4+ years of experience** designing, optimizing, and scaling mission-critical systems and high-volume data architectures. Specialized in combining **Data Engineering (Oracle PL/SQL, SQL Server, CBO Tuning)** with **Backend Development (.NET 8, Python)**—implementing advanced patterns such as **CQRS**, **Transactional Outbox**, and **Change Data Capture (CDC)** to resolve performance bottlenecks and ensure data integrity in high-concurrency environments.

### 🛠️ Core Services & Technical Capabilities
* **⚡ SQL Tuning & Database Architecture:** Execution plan diagnostics (`DBMS_XPLAN`), CBO cost optimization, table partitioning, covering indexes, and vectorized PL/SQL batch processing (`BULK COLLECT` / `FORALL`).
* **🔄 Event-Driven & Decoupled Data Systems:** Protecting OLTP transaction engines from analytical query overhead using **CQRS**, **Transactional Outbox**, **RabbitMQ**, and **MongoDB** read projections.
* **🐍 Python Data Pipelines & CDC Automation:** Automated extraction and transformation pipelines using **Pydantic v2** validation, change data tracking for historical state auditing, and notification workflows (HTML/Excel).
* **⚙️ Enterprise Backend (.NET 8):** Scalable Worker Services, real-time bidirectional communication with **WebSockets**, and mission-critical transactional integrations.
* **🚀 Technical Governance & Lifecycle:** Database versioning (**Git Flow**, **Redgate**), containerized reproducibility (**Docker**), and cross-platform operations.

---

### 📌 Featured Engineering Projects

#### 1. ⚡ [Database Performance Benchmarking & Refactoring Suite](https://github.com/DerekMazino/db-performance-benchmark)
* **Stack:** `Oracle 23ai Free` | `PL/SQL` | `CBO Tuning` | `Interval Partitioning` | `Docker`
* **Key Achievements on a 10M-row Financial Ledger:**
  * **Sargability & Covering Indexes:** Slashed transactional query latency from **13.60s to 0.01s (1,360x faster)** and reduced logical RAM I/O by **99.95%** (157,000 down to 67 blocks).
  * **Vectorized PL/SQL Batch Processing:** Transformed row-by-row cursors to `BULK COLLECT LIMIT 5000` + `FORALL ... SAVE EXCEPTIONS`, delivering **2.39x throughput** and cutting context switches by **99.98%**.
  * **Physical Partition Pruning:** Deployed monthly `INTERVAL` partitioning, speeding analytical reports by **9.4x (10.56s to 1.12s)** and cutting disk I/O by **91.3%**.

#### 2. 🔄 [Event-Driven Read Model Sync (CQRS & Transactional Outbox)](https://github.com/DerekMazino/event-driven-cqrs-sync)
* **Stack:** `Oracle 23ai` | `.NET 8 Worker Services` | `RabbitMQ (AMQP)` | `MongoDB 7.0` | `Docker`
* **Key Achievements:**
  * **Non-Blocking Delivery:** Guaranteed *at-least-once* event delivery with the **Transactional Outbox** pattern inside ACID stored procedures and concurrent `.NET 8` pollers (`SELECT FOR UPDATE SKIP LOCKED`).
  * **Sub-Millisecond Read Projections:** Idempotent `.NET 8` projections converting 3NF relational data (50k loans, 600k schedules) to denormalized **MongoDB** read documents.
  * **Empirical Gain:** Reduced query latency by **>99% (850ms down to 1–5ms)**, fully isolating the OLTP core from read locks.

#### 3. 🏠 [Real Estate Investment Monitor & CDC Engine](https://github.com/DerekMazino/real-estate-monitor)
* **Stack:** `Python 3.11+` | `Pydantic v2` | `SQLite` | `CDC Pattern` | `SMTP / Excel`
* **Key Achievements:**
  * **CDC Engine for Price Tracking:** Detects new listing arrivals and records historical price cuts with discount percentages in `price_history`.
  * **Strict Data Engineering:** Multi-portal ingestion (Finca Raíz, MetroCuadrado, Ciencuadras) validated and normalized through **Pydantic v2** schemas with deduplication.
  * **Decoupled Notification Dispatch:** Automated generation of hyperlinked Excel spreadsheets and scheduled HTML alerts via SMTP.

#### 4. 🚧 Upcoming Project: Business-Agnostic POS Engine *(In Analysis & Planning)*
* **Vision & Scope:** Multi-niche Point of Sale (POS) architecture engineered with clean boundary separation and dynamic metadata schemas so billing, inventory, and sync capabilities adapt to retail, hospitality, or service sectors without modifying core transaction code.

</details>

---

<div align="center">

### 📫 ¿Hablamos sobre tu próximo reto de datos o arquitectura backend?
💼 **[LinkedIn: Juan Camilo Marín](https://www.linkedin.com/in/camilo-marin-ingeniero)** • 📧 **[juancmaringcu@gmail.com](mailto:juancmaringcu@gmail.com)**

</div>
