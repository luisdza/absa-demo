# ABSA Demo Architecture
## Enterprise Banking Interaction & Analytics Feedback Loop

This repository demonstrates a **modern enterprise banking architecture** that connects operational systems with analytics and decision intelligence.

The demo illustrates how a **business interaction** propagates through enterprise systems and returns **actionable insights** to frontline users.

The architecture showcases several key concepts:

- API-driven enterprise integration
- Service mesh microservice communication
- Event-driven data architecture
- Centralised data warehousing
- Analytics-driven decision support
- Continuous feedback loops to business users

---

# Architecture Overview

Modern banking systems operate as **continuous feedback systems**.

A typical cycle looks like this:

1. A **Business User** interacts with a **CRM system**
2. The CRM triggers backend services through an **API Gateway**
3. Microservices communicate via a **Service Mesh**
4. Operational events and data are captured in the **Enterprise Data Platform**
5. Analytics platforms generate insights and recommendations
6. Insights return to the business through dashboards or decision systems

This creates a **closed loop of learning and optimisation**.

---

# System Architecture

```mermaid
flowchart TD

%% Business Interaction
User[A User] -->|customer interaction| CRM[CRM System]

%% Enterprise Integration Layer
CRM --> API[API Gateway]
API --> Svc[Service Mesh]

%% Operational Services
Svc --> Core[Core Banking Services]
Svc --> Events[Event Streaming Platform]

%% Data Platform
Core --> DW[(Enterprise Data Warehouse)]
Events --> DW

%% Analytics & Intelligence
DW --> BI[BI Dashboard]
DW --> AI[AI / Recommendation Engine]

%% Feedback loop
BI -->|insights| User
AI -->|next best action| CRM


%% Layer Styling
classDef business fill:#dae8fc,stroke:#6c8ebf,stroke-width:2px,color:#000
classDef integration fill:#d5e8d4,stroke:#82b366,stroke-width:2px,color:#000
classDef platform fill:#f8cecc,stroke:#b85450,stroke-width:2px,color:#000
classDef data fill:#fff2cc,stroke:#d6b656,stroke-width:2px,color:#000
classDef analytics fill:#e1d5e7,stroke:#9673a6,stroke-width:2px,color:#000

%% Apply classes
class User,CRM business
class API,Svc integration
class Core,Events platform
class DW data
class BI,AI analytics

