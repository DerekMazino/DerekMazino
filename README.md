<div align="center">

# Juan Camilo Marín García
### Ingeniero de Sistemas | Arquitectura de Datos, SQL Tuning & Desarrollo Backend (.NET / Python)
📍 **Colombia** (Disponible para proyectos remotos, híbridos o consultoría especializada)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Conectar-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/camilo-marin-ingeniero)
[![Email](https://img.shields.io/badge/Email-Contáctame-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:juancmaringcu@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-DerekMazino-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/DerekMazino)

🌐 **[Versión en Español](#-versión-en-español)** | **[Read in English](#-english-version)**

</div>

---

<a name="-versión-en-español"></a>
## 👨‍💻 Perfil Profesional

Ingeniero de Sistemas (UIS) con **más de 4 años de experiencia** diseñando, optimizando y escalando sistemas críticos y bases de datos transaccionales de alto volumen en sectores como servicios públicos, financiero y tecnología. 

Me especializo en la intersección entre la **Ingeniería de Datos (Oracle PL/SQL, SQL Server, Tuning SQL)** y la **Arquitectura Backend (.NET, Python)**, implementando patrones modernos como **CQRS**, **Transactional Outbox** y **CDC** para eliminar cuellos de botella de rendimiento, reducir tiempos de respuesta en procesos masivos (como facturación electrónica y cierres contables) y garantizar la integridad de la información bajo alta concurrencia.

---

## 🛠️ Portafolio de Servicios y Especialización

* **⚡ Optimización y Tuning de Bases de Datos (Oracle / SQL Server):** Diagnóstico profundo de planes de ejecución (`DBMS_XPLAN`), optimización del Cost-Based Optimizer (CBO), particionamiento físico de tablas millonarias, diseño de índices de cobertura y procesamiento masivo por lotes en PL/SQL (`BULK COLLECT` / `FORALL`).
* **🔄 Arquitecturas de Datos Desacopladas & Tiempo Real:** Protección de motores transaccionales (OLTP) frente a consultas analíticas pesadas mediante **CQRS**, **Transactional Outbox**, mensajería asíncrona con **RabbitMQ** y motores de lectura rápida en **MongoDB**.
* **⚙️ Desarrollo Backend & Automatización de Procesos:** Construcción de servicios asíncronos y Worker Services en **.NET 8 (C#)**, servidores de comunicación bidireccional en tiempo real (**WebSockets**), facturación electrónica y pipelines **ETL/ELT automatizados con Python**.
* **🚀 Calidad, Gobierno Técnico y Versionamiento SQL:** Control de versiones de bases de datos (**Git**, **Redgate**), levantamiento de fichas técnicas, aseguramiento de calidad (QA de datos) y despliegues reproducibles con **Docker** en entornos Linux y Windows.

---

## 📌 Proyectos Destacados (Casos de Estudio con Métricas Reales)

### 1. ⚡ [Database Performance Benchmarking & Refactoring Suite](https://github.com/DerekMazino/db-performance-benchmark)
> **Laboratorio reproducible de ingeniería de bases de datos y optimización SQL sobre un libro mayor financiero de 10,000,000 de registros.**
* **Tecnologías:** `Oracle 23ai Free` | `PL/SQL` | `CBO Tuning` | `Interval Partitioning` | `Docker`
* **Impacto y Resultados Medidos:**
  * **Sargabilidad e Índices de Cobertura:** Reducción de latencia en consultas transaccionales de **13.60 s a 0.01 s (1,360x más rápido)** y disminución del consumo de memoria RAM (I/O lógico) en un **99.95%** (de 157,000 a solo 67 bloques).
  * **Procesamiento Masivo por Lotes (Batch):** Refactorización de cursores fila-por-fila hacia `BULK COLLECT LIMIT 5000` + `FORALL ... SAVE EXCEPTIONS`, logrando **2.39x mayor velocidad de procesamiento** y reduciendo el *context switching* en un **99.98%**.
  * **Partition Pruning Físico:** Implementación de particionamiento mensual automático, acelerando reportes analíticos **9.4x (de 10.56 s a 1.12 s)** y reduciendo la lectura de disco/segmento en un **91.3%**.

### 2. 🔄 [Event-Driven Read Model Sync (CQRS & Transactional Outbox)](https://github.com/DerekMazino/event-driven-cqrs-sync)
> **Arquitectura orientada a eventos que protege un motor OLTP financiero de alta concurrencia contra bloqueos provocados por consultas y reportes complejos.**
* **Tecnologías:** `Oracle 23ai` | `.NET 8 Worker Services` | `RabbitMQ (AMQP)` | `MongoDB 7.0` | `Docker`
* **Impacto y Resultados Medidos:**
  * **Consistencia sin Bloqueos Distribuidos:** Entrega garantizada de eventos (*at-least-once*) mediante el patrón **Transactional Outbox** en procedimientos PL/SQL atómicos y workers concurrentes en `.NET 8` (`SELECT FOR UPDATE SKIP LOCKED`).
  * **Proyecciones de Lectura Ultra-Rápidas:** Sincronización asíncrona e idempotente de un esquema normalizado 3NF (50,000 préstamos y 600,000 cuotas) hacia documentos pre-agregados en **MongoDB**.
  * **Diferencial de Rendimiento:** Reducción de latencia de consulta en **más del 99% (pasando de 850 ms en uniones relacionales a 1–5 ms en MongoDB)**, eliminando por completo la contención de *locks* en la base de datos transaccional.

### 3. 🚧 Próximo Proyecto: Sistema POS Agnóstico al Negocio *(En Análisis y Planeación)*
> **Arquitectura de Punto de Venta (POS) multi-nicho diseñada para alta adaptabilidad de dominio y confiabilidad transaccional.**
* **Enfoque Arquitectónico:** Actualmente en etapa de análisis de requerimientos y modelado de dominio. Diseñado bajo principios de arquitectura limpia y metadatos dinámicos para que su motor transaccional base (inventario, facturación, impuestos y sincronización) se adapte a distintos tipos de comercio (retail, gastronomía, servicios) sin necesidad de reescribir el núcleo del sistema.

---

## 💻 Stack Tecnológico y Herramientas

<div align="center">

| Categoría | Tecnologías |
| :--- | :--- |
| **Lenguajes** | ![SQL](https://img.shields.io/badge/SQL-003B57?style=flat-square&logo=postgresql&logoColor=white) ![PL/SQL](https://img.shields.io/badge/PL%2FSQL-F80000?style=flat-square&logo=oracle&logoColor=white) ![C#](https://img.shields.io/badge/C%23-239120?style=flat-square&logo=c-sharp&logoColor=white) ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![Java](https://img.shields.io/badge/Java-007396?style=flat-square&logo=java&logoColor=white) |
| **Bases de Datos** | ![Oracle 23ai / 19c](https://img.shields.io/badge/Oracle_Database-F80000?style=flat-square&logo=oracle&logoColor=white) ![SQL Server](https://img.shields.io/badge/SQL_Server-CC2927?style=flat-square&logo=microsoft-sql-server&logoColor=white) ![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white) ![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white) |
| **Backend & Mensajería** | ![.NET 8](https://img.shields.io/badge/.NET_8-512BD4?style=flat-square&logo=dotnet&logoColor=white) ![RabbitMQ](https://img.shields.io/badge/RabbitMQ-FF6600?style=flat-square&logo=rabbitmq&logoColor=white) ![WebSockets](https://img.shields.io/badge/WebSockets-010101?style=flat-square) |
| **Arquitectura & DevOps** | ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![Git Flow](https://img.shields.io/badge/Git_Flow-F05032?style=flat-square&logo=git&logoColor=white) ![Redgate](https://img.shields.io/badge/Redgate-CC0000?style=flat-square) ![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black) |

</div>

---

<a name="-english-version"></a>
<details>
<summary><b>🇺🇸 Click here to expand the English Version (Portfolio & Resume Summary)</b></summary>
<br>

### 👨‍💻 Executive Summary
Systems Engineer based in **Colombia** with **4+ years of experience** designing, optimizing, and scaling mission-critical systems and high-volume relational databases. Specialized in the intersection of **Data Engineering (Oracle PL/SQL, SQL Tuning)** and **Backend Architecture (.NET, Python)**—implementing modern patterns like **CQRS**, **Transactional Outbox**, and **Change Data Capture (CDC)** to eliminate performance bottlenecks and ensure data integrity in high-concurrency environments.

### 🛠️ Core Services & Expertise
* **⚡ Database Performance & SQL Tuning:** Execution plan analysis (`DBMS_XPLAN`), Cost-Based Optimizer (CBO) tuning, physical partitioning, covering indexes, and high-throughput PL/SQL batch processing (`BULK COLLECT` / `FORALL`).
* **🔄 Distributed Data Patterns & Event-Driven Sync:** Decoupling OLTP write workloads from analytical/read queries using **CQRS**, **Transactional Outbox**, **RabbitMQ**, and NoSQL read stores (**MongoDB**).
* **⚙️ Backend Development & Automation:** Asynchronous microservices and Worker Services in **.NET 8 (C#)**, real-time bidirectional communication via **WebSockets**, mission-critical electronic invoicing, and **Python** ETL/ELT automation.
* **🚀 Database Lifecycle & DevOps:** Database versioning (**Git**, **Redgate**), containerized local reproducibility (**Docker**), and cross-platform deployments.

### 📌 Featured Engineering Portfolio

#### 1. ⚡ [Database Performance Benchmarking & Refactoring Suite](https://github.com/DerekMazino/db-performance-benchmark)
* **Stack:** `Oracle 23ai Free` | `PL/SQL` | `CBO Tuning` | `Interval Partitioning` | `Docker`
* **Key Achievements on a 10M-row Financial Dataset:**
  * **Sargability & Covering Indexes:** Reduced transactional query latency from **13.60s to 0.01s (1,360x faster)** and cut logical I/O RAM buffers by **99.95%** (157,000 to 67 blocks).
  * **Vectorized PL/SQL Batch Processing:** Refactored row-by-row cursors into `BULK COLLECT LIMIT 5000` + `FORALL ... SAVE EXCEPTIONS`, achieving **2.39x throughput** and reducing context switches by **99.98%**.
  * **Physical Partition Pruning:** Implemented monthly `INTERVAL` partitioning, accelerating analytical reporting by **9.4x (10.56s to 1.12s)** and reducing segment I/O by **91.3%**.

#### 2. 🔄 [Event-Driven Read Model Sync (CQRS & Transactional Outbox)](https://github.com/DerekMazino/event-driven-cqrs-sync)
* **Stack:** `Oracle 23ai` | `.NET 8 Worker Services` | `RabbitMQ (AMQP)` | `MongoDB 7.0` | `Docker`
* **Key Achievements:**
  * **Zero Distributed Locks:** Guaranteed *at-least-once* event delivery using the **Transactional Outbox** pattern within ACID stored procedures and concurrent `.NET 8` pollers (`SELECT FOR UPDATE SKIP LOCKED`).
  * **Sub-Millisecond Read Projections:** Idempotent `.NET 8` projectors syncing 3NF relational data (50k loans, 600k schedules) into denormalized **MongoDB** documents.
  * **Empirical Impact:** Reduced read latency by **>99% (from 850ms in coupled 3NF joins down to 1–5ms)** while completely isolating the OLTP engine from read lock contention.

#### 3. 🚧 Upcoming Project: Business-Agnostic POS Engine *(In Analysis & Planning)*
* **Vision & Scope:** Multi-niche Point of Sale (POS) architecture currently in the domain modeling and specification phase. Designed with clean, decoupled boundaries so the core transactional engine can adapt to retail, hospitality, or service niches without rewriting core business logic.

</details>

---

<div align="center">

### 📫 ¿Hablamos sobre tu próximo proyecto o reto de datos?
💼 **[LinkedIn: Juan Camilo Marín](https://www.linkedin.com/in/camilo-marin-ingeniero)** • 📧 **[juancmaringcu@gmail.com](mailto:juancmaringcu@gmail.com)**

</div>
