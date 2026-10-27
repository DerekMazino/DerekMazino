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

Ingeniero de Sistemas (UIS) con **más de 4 años de experiencia** diseñando, optimizando y asegurando sistemas transaccionales críticos y almacenes de datos de alto volumen. Cuento con trayectoria comprobada en sectores de alta exigencia transaccional como servicios públicos, banca, fintech y tecnología.

Combino una especialización profunda en **Ingeniería de Bases de Datos (Oracle PL/SQL, SQL Server, Tuning CBO, Pruebas Unitarias utPLSQL)** con **Arquitectura Backend (.NET 8, Python)**. Implemento patrones como **CQRS**, **Transactional Outbox**, **Change Data Capture (CDC)** y **procesamiento batch resiliente en memoria (PGA)** para suprimir cuellos de botella de E/S, blindar la consistencia ACID de motores financieros y acelerar flujos analíticos y operativos.

---

## 🛠️ Portafolio de Servicios y Especialización

* **⚡ Arquitectura Transaccional y SQL Tuning (Oracle / SQL Server):** Diagnóstico profundo con `DBMS_XPLAN`, afinamiento de reglas de indexación (**E-S-R-O / Index-Only Access**), particionamiento físico de grandes tablas y procesamiento masivo vectorizado en memoria PGA con `BULK COLLECT` y `FORALL ... SAVE EXCEPTIONS`.
* **🧪 Aseguramiento de Calidad y Automatización en Base de Datos:** Pruebas unitarias automatizadas y declarativas para PL/SQL con **utPLSQL v3**, segregación física de segmentos en **tablespaces dedicados** y orquestación de tareas desatendidas con **`DBMS_SCHEDULER`**.
* **🔄 Arquitecturas de Datos Desacopladas y Tiempo Real:** Protección de motores relacionales OLTP frente a degradación analítica mediante **CQRS**, **Transactional Outbox**, mensajería distribuida con **RabbitMQ** y proyecciones optimizadas en **MongoDB**.
* **🐍 Pipelines de Datos, CDC y Automatización con Python:** Modelado de datos estricto con validación tipada (**Pydantic v2**), detección incremental de cambios (CDC) con retención de auditoría histórica y distribución multicanal automatizada (Excel / SMTP).
* **⚙️ Backend Empresarial y Servicios Críticos:** Microservicios y Worker Services asíncronos en **.NET 8 (C#)**, canales de comunicación bidireccional en tiempo real mediante **WebSockets** y soporte a facturación masiva.

---

## 📌 Proyectos Destacados (Portafolio Técnico)

### 1. 💳 [Core Settlement & Cashback Engine (Oracle 23ai)](https://github.com/DerekMazino/fintech-settlement-engine)
> **Backend transaccional de conciliación, liquidación masiva y cashback para pasarelas fintech.**
* **Tecnologías:** `Oracle 23ai Free` | `PL/SQL` | `utPLSQL v3` | `CBO Tuning (E-S-R-O)` | `DBMS_SCHEDULER` | `Docker`
* **Logros e Implementación Técnica:**
  * **Optimización CBO (Index-Only Access):** Diseño del índice compuesto `idx_trx_riesgos_esro` bajo la regla **E-S-R-O**. Logró acceso directo vía `INDEX RANGE SCAN` sin visitas a tabla (`TABLE ACCESS BY INDEX ROWID: 0`) y resolución en **0.01 s con solo 67 buffers**, eliminando operaciones de ordenamiento mediante `SORT GROUP BY NOSORT`.
  * **Batching Resiliente en Memoria (PGA):** Procesamiento en paquetes de 1,000 registros mediante cursores explícitos y `FORALL ... SAVE EXCEPTIONS`. Auditoría atómica de errores (`ORA-24381` / `log_liquidacion_errores`) y segregación determinista en una pasada entre estados `LIQUIDADO` y `RECHAZADO` vía `SQL%BULK_ROWCOUNT`.
  * **Infraestructura y QA:** Segregación física de I/O en tablespaces dedicados (`TS_FINTECH_DATA` vs `TS_FINTECH_IDX`), automatización de jobs recurrentes con `DBMS_SCHEDULER` y suite declarativa de pruebas unitarias automatizadas con **utPLSQL v3**.

### 2. ⚡ [Database Performance Benchmarking & Refactoring Suite](https://github.com/DerekMazino/db-performance-benchmark)
> **Laboratorio reproducible de optimización SQL sobre un libro mayor financiero de 10,000,000 de registros.**
* **Tecnologías:** `Oracle 23ai Free` | `PL/SQL` | `CBO Tuning` | `Interval Partitioning` | `Docker`
* **Impacto y Métricas Empíricas:**
  * **Sargabilidad y Covering Index:** Reducción de latencia en consultas transaccionales de **13.60 s a 0.01 s (1,360x más rápido)** y recorte del I/O lógico en memoria RAM en un **99.95%** (de 157,000 a 67 bloques).
  * **Eliminación de Context Switches:** Refactorización de cursores fila a fila (*row-by-row*) a lotes vectorizados con `BULK COLLECT LIMIT 5000` + `FORALL ... SAVE EXCEPTIONS`, alcanzando **2.39x mayor throughput** y un **99.98% menos context switches** entre PL/SQL y SQL.
  * **Partition Pruning:** Implementación de particionamiento mensual por intervalos (`INTERVAL`), acelerando reportes analíticos masivos **9.4x (de 10.56 s a 1.12 s)** con un **91.3% menos I/O de segmento**.

### 3. 🔄 [Event-Driven Read Model Sync (CQRS & Transactional Outbox)](https://github.com/DerekMazino/event-driven-cqrs-sync)
> **Arquitectura orientada a eventos para proteger un motor financiero OLTP frente a degradación por consultas pesadas.**
* **Tecnologías:** `Oracle 23ai` | `.NET 8 Worker Services` | `RabbitMQ (AMQP)` | `MongoDB 7.0` | `Docker`
* **Impacto y Métricas Empíricas:**
  * **Entrega Garantizada sin Bloqueos Distribuidos:** Implementación de **Transactional Outbox** dentro de los mismos límites ACID de la base de datos y consumo concurrente en `.NET 8` mediante `SELECT FOR UPDATE SKIP LOCKED` sin bloqueos entre instancias.
  * **Proyecciones Asíncronas en Memoria:** Proyección idempotente sobre **MongoDB 7.0** usando `ReplaceOneAsync` a partir de un modelo relacional 3NF (50,000 préstamos y 600,000 cuotas).
  * **Diferencial de Rendimiento:** Reducción de latencia de lectura de **850 ms a 1–5 ms (>99% de mejora)**, liberando al 100% el motor OLTP de contención de locks en buffer.

### 4. 🏠 [Real Estate Investment Monitor & CDC Engine](https://github.com/DerekMazino/real-estate-monitor)
> **Pipeline automatizado de extracción, Change Data Capture (CDC) y detección de oportunidades de inversión inmobiliaria en Colombia.**
* **Tecnologías:** `Python 3.11+` | `Pydantic v2` | `SQLite Relational` | `CDC Pattern` | `SMTP / Excel`
* **Capacidades Implementadas:**
  * **Motor CDC para Variaciones de Precios:** Algoritmo de detección de estados que identifica nuevas publicaciones y rastrea rebajas históricas con cálculo de descuento porcentual en `price_history`.
  * **Modelado Estricto y Normalización:** Validación de esquemas de datos heterogéneos (Finca Raíz, MetroCuadrado, Ciencuadras) mediante modelos **Pydantic v2** y deduplicación estricta de registros.
  * **Reportería y Alertas Desacopladas:** Generación automática de planillas consolidadas en formato `.xlsx` con hipervínculos directos y despachador extensible de alertas por correo HTML vía SMTP.

### 5. 🚧 En Desarrollo: Sistema POS Agnóstico al Negocio *(Planeación & Arquitectura)*
> **Arquitectura de Punto de Venta (POS) multi-nicho orientada a la adaptabilidad de dominio y alta fiabilidad transaccional.**
* **Enfoque:** Modelado modular con límites desacoplados y esquemas de metadatos dinámicos, permitiendo que el núcleo transaccional (inventario, facturación, esquemas tributarios y sincronización) funcione sobre retail, servicios o gastronomía sin modificar la lógica base.

---

## 💻 Stack Tecnológico

<div align="center">

| Área | Tecnologías |
| :--- | :--- |
| **Bases de Datos Relacionales** | ![Oracle 23ai / 19c](https://img.shields.io/badge/Oracle_Database-F80000?style=flat-square&logo=oracle&logoColor=white) ![SQL Server](https://img.shields.io/badge/SQL_Server-CC2927?style=flat-square&logo=microsoft-sql-server&logoColor=white) ![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white) ![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white) |
| **NoSQL & Mensajería** | ![MongoDB](https://img.shields.io/badge/MongoDB_7.0-47A248?style=flat-square&logo=mongodb&logoColor=white) ![RabbitMQ](https://img.shields.io/badge/RabbitMQ_AMQP-FF6600?style=flat-square&logo=rabbitmq&logoColor=white) ![WebSockets](https://img.shields.io/badge/WebSockets-010101?style=flat-square) |
| **Lenguajes** | ![PL/SQL](https://img.shields.io/badge/PL%2FSQL-F80000?style=flat-square&logo=oracle&logoColor=white) ![SQL](https://img.shields.io/badge/SQL-003B57?style=flat-square&logo=postgresql&logoColor=white) ![C#](https://img.shields.io/badge/C%23-239120?style=flat-square&logo=c-sharp&logoColor=white) ![Python](https://img.shields.io/badge/Python_3.11+-3776AB?style=flat-square&logo=python&logoColor=white) ![Java](https://img.shields.io/badge/Java-007396?style=flat-square&logo=java&logoColor=white) |
| **Testing, Frameworks & Modelado** | ![utPLSQL v3](https://img.shields.io/badge/utPLSQL_v3-4EAA25?style=flat-square) ![.NET 8](https://img.shields.io/badge/.NET_8_Worker_Services-512BD4?style=flat-square&logo=dotnet&logoColor=white) ![Pydantic v2](https://img.shields.io/badge/Pydantic_v2-E92063?style=flat-square&logo=pydantic&logoColor=white) ![Pandas / OpenPyXL](https://img.shields.io/badge/Data_Pipelines-217346?style=flat-square&logo=microsoft-excel&logoColor=white) |
| **DevOps & Ciclo de Vida** | ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![Git Flow](https://img.shields.io/badge/Git_Flow-F05032?style=flat-square&logo=git&logoColor=white) ![Redgate](https://img.shields.io/badge/Redgate-CC0000?style=flat-square) ![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black) |

</div>

---

<a name="-english-version"></a>
<details>
<summary><b>🇺🇸 Click here to expand the English Version (Portfolio & Resume Summary)</b></summary>
<br>

### 👨‍💻 Executive Summary
Systems Engineer based in **Colombia** with **4+ years of experience** designing, optimizing, and securing mission-critical transactional platforms and high-volume data architectures. Specialized in connecting deep **Database Engineering (Oracle PL/SQL, SQL Server, CBO Tuning, utPLSQL)** with **Backend Architecture (.NET 8, Python)**—applying enterprise patterns like **CQRS**, **Transactional Outbox**, and **Change Data Capture (CDC)** to resolve severe I/O bottlenecks and maintain strict ACID compliance under heavy concurrency.

### 🛠️ Core Services & Technical Capabilities
* **⚡ Database Architecture & SQL Tuning:** `DBMS_XPLAN` execution diagnostics, compound **E-S-R-O indexing (Index-Only Access)**, large-scale table partitioning, and high-performance PL/SQL PGA batch routines (`BULK COLLECT` / `FORALL ... SAVE EXCEPTIONS`).
* **🧪 Database QA & Automation:** Automated unit testing suites using **utPLSQL v3**, I/O isolation across segregated **tablespaces**, and scheduled job orchestration with **`DBMS_SCHEDULER`**.
* **🔄 Event-Driven & Decoupled Data Systems:** Decoupling OLTP engines from analytics via **CQRS**, **Transactional Outbox**, **RabbitMQ** topic exchanges, and **MongoDB 7.0** read projections.
* **🐍 Python Pipelines & CDC Automation:** Robust data ingestion and schema validation using **Pydantic v2**, price mutation auditing with CDC logic, and programmatic reporting (Excel / SMTP).
* **⚙️ Enterprise Backend (.NET 8):** Scalable Worker Services, low-latency bidirectional protocols via **WebSockets**, and transactional enterprise billing.

---

### 📌 Featured Engineering Portfolio

#### 1. 💳 [Core Settlement & Cashback Engine (Oracle 23ai)](https://github.com/DerekMazino/fintech-settlement-engine)
* **Stack:** `Oracle 23ai Free` | `PL/SQL` | `utPLSQL v3` | `CBO Tuning (E-S-R-O)` | `DBMS_SCHEDULER` | `Docker`
* **Key Achievements:**
  * **CBO Index-Only Access:** Designed `idx_trx_riesgos_esro` following the **E-S-R-O** rule. Reached direct `INDEX RANGE SCAN` with zero table lookups (`TABLE ACCESS BY INDEX ROWID: 0`) and executed in **0.01 s with 67 buffers**, avoiding intermediate sorting via `SORT GROUP BY NOSORT`.
  * **Resilient In-Memory Batching:** Extracted in batches of 1,000 via explicit cursors into PGA memory. Implemented atomic bulk error logging for `ORA-24381` and segregated `LIQUIDADO` vs `RECHAZADO` records in a single pass using `SQL%BULK_ROWCOUNT`.
  * **Storage & Testing:** Segmented storage across dedicated tablespaces (`TS_FINTECH_DATA` vs `TS_FINTECH_IDX`), recurring batch scheduling via `DBMS_SCHEDULER`, and a test suite in **utPLSQL v3**.

#### 2. ⚡ [Database Performance Benchmarking & Refactoring Suite](https://github.com/DerekMazino/db-performance-benchmark)
* **Stack:** `Oracle 23ai Free` | `PL/SQL` | `CBO Tuning` | `Interval Partitioning` | `Docker`
* **Key Achievements (10M-row Ledger):**
  * **Sargability & Covering Indexes:** Reduced query latency from **13.60 s to 0.01 s (1,360x faster)** and cut RAM logical I/O by **99.95%** (157,000 to 67 blocks).
  * **Vectorized PL/SQL Batching:** Slashed context switching by **99.98%** using `BULK COLLECT LIMIT 5000` + `FORALL ... SAVE EXCEPTIONS` (delivering **2.39x throughput**).
  * **Physical Partition Pruning:** Deployed monthly `INTERVAL` partitioning, speeding queries by **9.4x (10.56 s to 1.12 s)** with **91.3% less segment I/O**.

#### 3. 🔄 [Event-Driven Read Model Sync (CQRS & Transactional Outbox)](https://github.com/DerekMazino/event-driven-cqrs-sync)
* **Stack:** `Oracle 23ai` | `.NET 8 Worker Services` | `RabbitMQ` | `MongoDB 7.0` | `Docker`
* **Key Achievements:**
  * **ACID Event Delivery:** Guaranteed *at-least-once* publishing with the **Transactional Outbox** pattern and non-blocking `.NET 8` pollers (`SELECT FOR UPDATE SKIP LOCKED`).
  * **Sub-Millisecond Projections:** Idempotent workers syncing 3NF relations (50k loans, 600k quotas) to **MongoDB 7.0**.
  * **Telemetry Gain:** Slashed read latency from **850 ms down to 1–5 ms (>99% drop)**, isolating the OLTP core from read locks.

#### 4. 🏠 [Real Estate Investment Monitor & CDC Engine](https://github.com/DerekMazino/real-estate-monitor)
* **Stack:** `Python 3.11+` | `Pydantic v2` | `SQLite` | `CDC Pattern` | `SMTP / Excel`
* **Key Achievements:**
  * **CDC Price Drop Engine:** Automated change detection capturing new listings and price drops with historical discount logging.
  * **Typed Normalization:** Multi-portal schema mapping and deduplication enforced with **Pydantic v2**.
  * **Decoupled Reporting:** Automated structured Excel spreadsheet generation and responsive HTML email alerts.

#### 5. 🚧 Upcoming Project: Business-Agnostic POS Engine *(Architecture & Planning)*
* **Vision:** Modular, multi-niche Point of Sale engine engineered with decoupled domain boundaries and metadata schemes to adapt billing, taxes, and inventory across sectors without altering core code.

</details>

---

<div align="center">

### 📫 ¿Hablamos sobre tu próximo reto de datos o arquitectura backend?
💼 **[LinkedIn: Juan Camilo Marín](https://www.linkedin.com/in/camilo-marin-ingeniero)** • 📧 **[juancmaringcu@gmail.com](mailto:juancmaringcu@gmail.com)**

</div>
