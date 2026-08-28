# Week 12: High-Level Architecture (2 Problems)

**Week:** 12  

## Objective

Design high-level architecture (HLD) for the 2 selected problems, including diagrams, component descriptions, data flow, and cloud service mappings.

The two selected problems are:

1. **Cloud-Based Expense Tracking & Analytics System**  
2. **Online Quiz / Exam Management System**

---

## Problem 1: Cloud-Based Expense Tracking & Analytics System

### 1.1 Problem Statement

Individuals and small businesses struggle to track daily expenses, categorize transactions, and gain actionable financial insights. Existing solutions are either too complex, lack predictive analytics, or do not leverage cloud scalability for cost-effective operations.

### 1.2 Proposed Solution

A cloud-native expense tracking web application that enables users to:

- Log income and expenses with customizable categories.  
- Upload receipts and attachments for record-keeping.  
- View interactive dashboards with spending trends, budget alerts, and anomaly detection.  
- Receive AI-driven monthly predictions and personalized savings recommendations.

### 1.3 IEEE Base Paper

- **Title:** Expense Management System  
- **Publication:** IEEE Conference Publication  
- **Link:** https://ieeexplore.ieee.org/abstract/document/10353348  
- **Key Contribution:** An app-based system for methodical monitoring of financial inflows and outflows, providing foundational concepts for expense tracking applications.

### 1.4 High-Level Architecture

The system follows a **microservices architecture** deployed on cloud infrastructure.

#### Architecture Diagram

*(Insert your diagram here – export from Draw.io/Excalidraw as PNG/SVG and place in `docs/assets/`)*

![Expense Tracker HLD](assets/expense-tracker-hld.png)

#### Architecture Style

- **Frontend:** React.js / Next.js single-page application.  
- **Hosting:** Cloud static hosting (AWS S3 + CloudFront, Azure Static Web Apps, or GCP Cloud Storage + CDN).  
- **Backend:** Containerized microservices (Docker) on Kubernetes or serverless.

#### Key Components

1. **Frontend (React/Next.js)**  
   - Hosted on AWS S3 + CloudFront / Azure Static Web Apps / GCP Cloud Storage + CDN.  
   - Communicates with backend via REST/GraphQL APIs.

2. **API Gateway**  
   - AWS API Gateway / Azure API Management / GCP Cloud Endpoints.  
   - Handles routing, rate limiting, and JWT authentication.

3. **Microservices:**  
   - **Auth Service:** User registration, login, JWT issuance, role-based access control.  
   - **Transaction Service:** CRUD for income/expenses, categorization, receipt uploads.  
   - **Analytics Service:** Aggregation, trend analysis, budget calculations.  
   - **Prediction Service:** ML model for monthly expense forecasting and anomaly detection.

4. **Database:**  
   - Managed relational DB (AWS RDS PostgreSQL / Azure SQL / GCP Cloud SQL) for transactional data.  
   - Redis cache (AWS ElastiCache / Azure Redis / GCP Memorystore) for dashboards.

5. **Storage:**  
   - Object storage (AWS S3 / Azure Blob / GCP Cloud Storage) for receipts with pre-signed URLs.

6. **Message Queue:**  
   - AWS SQS / Azure Service Bus / GCP Pub/Sub for async tasks (e.g., receipt OCR, email notifications).

#### Data Flow

1. User logs in → Auth Service validates credentials → JWT issued.  
2. User adds transaction → Transaction Service stores in DB.  
3. Analytics Service aggregates data → Dashboard updated in real-time.  
4. Prediction Service runs nightly batch → Updates forecasts in DB.

#### Scalability & Security

- Auto-scaling backend services based on CPU/memory.  
- Database read replicas for high read traffic.  
- HTTPS everywhere, encrypted data at rest/in transit, IAM least-privilege access.

---

## Problem 2: Online Quiz / Exam Management System

### 2.1 Problem Statement

Educational institutions, training organizations, and corporate HR departments need secure, scalable platforms to conduct remote exams with auto-grading, anti-cheating measures, and performance analytics. Traditional exam systems lack flexibility, scalability, and intelligent grading capabilities.

### 2.2 Proposed Solution

A web-based examination platform that enables:

- Instructors to create quizzes/exams with diverse question types (MCQs, coding challenges, descriptive answers).  
- Students to take timed exams remotely with a secure interface.  
- Automatic grading for objective questions and AI-assisted grading for descriptive answers.  
- Analytics dashboards for performance tracking, question difficulty analysis, and student progress reports.  
- Anti-cheating measures such as tab-switch detection, randomized question orders, and optional AI-based proctoring.

### 2.3 IEEE Base Paper

- **Title:** Online Examination System with Measures for Prevention of Cheating along with Rapid Assessment and Automatic Grading  
- **Publication:** IEEE Conference  
- **Link:** https://ieeexplore.ieee.org/document/10039552  
- **Key Contribution:** A remote exam system with cheating prevention mechanisms, rapid assessment capabilities, and automatic grading features.

### 2.4 High-Level Architecture

The system adopts a **microservices architecture** with cloud-native components.

#### Architecture Diagram

*(Insert your diagram here – export from Draw.io/Excalidraw as PNG/SVG and place in `docs/assets/`)*

![Exam System HLD](assets/exam-system-hld.png)

#### Architecture Style

- **Frontend:** React.js / Angular responsive web application.  
- **Hosting:** Cloud static hosting with CDN for global access.  
- **Backend:** Containerized microservices on Kubernetes + serverless for event-driven tasks.

#### Key Components

1. **Frontend (React/Angular)**  
   - Hosted on cloud static hosting with CDN for global access.

2. **API Gateway**  
   - Managed API Gateway for routing, authentication, and rate limiting.

3. **Microservices:**  
   - **Auth Service:** User authentication, role management (instructor, student, admin), JWT tokens.  
   - **Exam Service:** Exam creation, scheduling, question bank management, exam lifecycle.  
   - **Attempt Service:** Handle exam attempts, timer management, auto-save every 30s.  
   - **Grading Service:** Rule-based grading for MCQs, code execution sandbox for programming, NLP for descriptive answers.  
   - **Analytics Service:** Performance reports, question difficulty, student progress tracking.  
   - **Proctoring Service (Optional):** AI-based proctoring with face detection, tab-switch monitoring.

4. **Database:**  
   - Managed relational DB (PostgreSQL / MySQL) for users, exams, questions, results.  
   - NoSQL DB (MongoDB / DynamoDB) for exam attempts and logs.

5. **Code Execution Sandbox:**  
   - Isolated Docker containers for running user-submitted code securely with time/memory limits.

6. **Message Queue:**  
   - AWS SQS / Azure Service Bus / GCP Pub/Sub for async grading, notifications, analytics.

7. **Caching:**  
   - Managed Redis for active exams, question caches, and leaderboards.

#### Data Flow

1. Student starts exam → Attempt Service creates attempt record with timer.  
2. Frontend auto-saves answers every 30s → Attempt Service updates DB.  
3. Student submits → Grading Service processes (MCQs instantly, code in sandbox, descriptive via NLP).  
4. Results stored → Analytics Service generates reports.

#### Scalability & Security

- Auto-scaling during peak exam periods (e.g., 1000+ concurrent students).  
- Database read replicas for result viewing.  
- Secure code execution in isolated containers.  
- Anti-cheating features: tab-switch detection, randomized question orders.

---

## Cloud Deployment Strategy (Both Projects)

### Infrastructure as Code (IaC)

- Terraform / CloudFormation scripts to provision VPC, subnets, security groups, databases, and compute resources.

### Containerization & Orchestration

- Dockerize all microservices.  
- Deploy on managed Kubernetes (AWS EKS / Azure AKS / GCP GKE) for scalability and resilience.  
- Use serverless (AWS Lambda / Azure Functions) for event-driven tasks (e.g., grading, notifications).

### CI/CD Pipeline

- GitHub Actions / GitLab CI for automated testing and deployment.  
- Separate staging and production environments with automated rollback on failures.

### Monitoring & Logging

- Cloud-native monitoring (CloudWatch / Azure Monitor / GCP Cloud Monitoring) for system health.  
- Centralized logging (ELK Stack / CloudWatch Logs) for debugging and audit trails.  
- Alerting on critical metrics (exam submission failures, grading errors, high latency).

### Scalability

- Auto-scaling policies for backend services during peak loads.  
- Database read replicas for handling high read traffic.  
- CDN for static assets and exam content delivery.

### Disaster Recovery

- Automated backups for databases and object storage.  
- Multi-region deployment for high availability (optional advanced feature).

---

## Expected Outcomes

- A fully functional, cloud-deployed expense tracker accessible via web browser.  
- A production-ready, cloud-deployed exam management platform.  
- Demonstrated skills in cloud architecture, microservices, serverless computing, and data analytics.  
- Portfolio pieces showcasing end-to-end system design, from requirements to deployment.  
- Foundation for advanced features like multi-currency support, bank API integrations, AI-based proctoring, and LMS integrations.

---

## Next Steps (Week 13+)

- Begin implementation of core features for both projects.  
- Set up CI/CD pipelines and infrastructure-as-code (Terraform/CloudFormation).  
- Start coding auth, transaction/exam services, and basic UI.  
- Create implementation repos (`project-1-expense-tracker/`, `project-2-exam-system/`).

**Deliverable:** Implementation repos with initial codebase and deployment scripts.
