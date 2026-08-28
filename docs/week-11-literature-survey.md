# Week 11: Literature Survey

**Week:** 11
**Topic:** Literature Survey for 2 Selected System Design Problems

---

# 1. Objective

The objective of this week's work is to study existing research related to the two problems shortlisted in Week 10.

The literature survey focuses on:

* Existing systems and approaches
* System architecture
* Technologies and algorithms
* Security and scalability
* Advantages
* Limitations
* Research gaps
* Opportunities for improvement

---

# 2. Selected Problems

## Project 01

**Online Quiz / Examination Management System**

## Project 02

**Food Delivery Ordering System**

---

# 3. Project 01 — Online Quiz / Examination Management System

## 3.1 Problem Overview

Online examination systems enable institutions to conduct assessments digitally without requiring students and instructors to be physically present at the same location.

The major system design challenges include:

* Authentication
* Examination integrity
* Concurrent users
* Secure question delivery
* Reliable answer submission
* Automatic grading
* Cheating detection
* Privacy
* Scalability

Existing research shows that online examination security and academic integrity remain major challenges, particularly because technology can both enable and mitigate dishonest behaviour.

---

# 3.2 Literature Search Keywords

The following keywords were used to identify relevant research:

* Online Examination System
* Online Assessment System
* Online Exam Security
* E-Learning Assessment
* Cloud-Based Examination System
* Automated Grading
* Online Exam Proctoring
* Academic Integrity
* Examination Security
* Machine Learning Online Examination
* AI Proctored Examination
* Scalable Online Examination

---

# 3.3 Research Paper 1

## A Systematic Review of Online Examinations: A Pedagogical Innovation for Scalable Authentication and Integrity

**Authors:** Kerryn Butler-Henderson, Joseph Crawford

**Journal:** Computers & Education

**Volume:** 159

**Article:** 104024

**Year:** 2020

**DOI:** 10.1016/j.compedu.2020.104024

### Research Objective

The study systematically reviews research related to online examinations and investigates challenges and opportunities associated with online assessment.

The review examined 36 papers and identified themes including:

* Student perceptions
* Student performance
* Anxiety
* Cheating
* Staff perceptions
* Authentication
* Security
* Interface design
* Technology issues

### Major Findings

The study found that online examinations can provide benefits in terms of logistics and convenience.

However, authentication, security, cheating prevention, interface design, and technology remain important considerations.

The research also highlights that online examinations require careful consideration of both technical and pedagogical factors.

### Limitations / Research Gap

The review identified a lack of discussion around broader pedagogical and governance issues.

This indicates that designing an online examination platform requires more than simply digitizing traditional examinations.

### Relevance to Proposed System

This research supports the inclusion of:

* Strong authentication
* Secure examination sessions
* Anti-cheating mechanisms
* Reliable examination interfaces
* Scalable infrastructure

---

# 3.4 Research Paper 2

## A Systematic Literature Review on Online Assessment Security: Current Challenges and Integrity Strategies

**Journal:** Computers & Security

**Volume:** 113

**Article:** 102544

**Year:** 2022

**DOI:** 10.1016/j.cose.2021.102544

### Research Objective

The research investigates security and integrity problems in online assessments.

The study reviewed research published between 2016 and 2021 and investigated:

1. Why students engage in dishonest behaviour
2. How students engage in dishonest behaviour
3. Strategies used to prevent and detect cheating
4. The role of machine learning in detecting dishonest behaviour

### Major Findings

The research identifies academic dishonesty as one of the major challenges of online assessment.

Two major categories of integrity strategies were identified:

* Prevention
* Detection

The study also found increasing use of machine learning techniques to detect dishonest behaviour.

### Research Gap

A major opportunity exists to combine prevention and detection mechanisms into a unified examination architecture.

The system should consider multiple stakeholders including:

* Platform administrators
* Educational institutions
* Teachers
* Students

### Relevance to Proposed System

The proposed architecture can incorporate:

* Authentication
* Role-based access
* Behaviour monitoring
* Suspicious activity detection
* Secure examination sessions
* Audit logging

---

# 3.5 Research Paper 3

## A Systematic Review of Online Exams Solutions in E-Learning: Techniques, Tools, and Global Adoption

**Authors:** Abdul Wahab Muzaffar, Muhammad Tahir, Muhammad Waseem Anwar, Qaiser Chaudry, Shamaila Rasheed Mir, Yawar Rasheed

**Journal:** IEEE Access

**Volume:** 9

**Year:** 2021

**DOI:** 10.1109/ACCESS.2021.3060192

### Research Objective

The study conducted a systematic literature review of online examination solutions.

It analyzed **53 studies** published during the previous five years. The research examined:

* Online exam features
* Development approaches
* Techniques
* Algorithms
* Datasets
* Examination tools
* Global adoption factors

### Major Findings

The study identified:

* 16 important techniques/algorithms
* 11 datasets
* 21 proposed online examination tools
* 25 existing tools used in the reviewed studies

### Research Gap

The research indicates that online examination solutions differ significantly depending on infrastructure, cost, security requirements, and desired features.

Therefore, a scalable architecture should be modular enough to support different examination requirements.

### Relevance to Proposed System

The proposed system can use a modular service architecture containing:

* Authentication Service
* Examination Service
* Question Service
* Submission Service
* Grading Service
* Monitoring Service
* Result Service

---

# 3.6 Research Paper 4

## An Automated Essay Scoring Systems: A Systematic Literature Review

**DOI:** 10.1007/s10462-021-10068-2

**Publication:** Artificial Intelligence Review

**Year:** 2021/2022

### Research Objective

This research investigates automated essay and short-answer evaluation using Artificial Intelligence and Machine Learning.

Traditional computer-based examinations commonly handle multiple-choice questions well, while automated evaluation of essays and short answers remains challenging.

### Major Findings

The study identifies challenges in evaluating:

* Content relevance
* Coherence
* Development of ideas
* Writing style
* Semantic meaning

### Research Gap

A comprehensive automated evaluation system capable of reliably handling different types of examination questions remains challenging.

### Relevance to Proposed System

The proposed system can initially support:

* MCQ auto-grading
* Programming-question evaluation

Future versions could introduce:

* NLP-based short-answer evaluation
* AI-assisted essay scoring

---

# 3.7 Research Paper 5

## Ensuring Academic Integrity Through Automated Online Exam Proctoring: A Decade Long Systematic Review

**Authors:** Manit Malhotra, Indu Chhabra

**Journal:** Discover Education

**Year:** 2026

**Volume:** 5

**Article:** 207

**DOI:** 10.1007/s44217-026-01224-3

### Research Objective

The study reviews research on automated online exam proctoring between 2014 and 2024.

It investigates the use of:

* Machine Learning
* Deep Learning
* IoT
* Computer Vision
* Biometric authentication
* Automated proctoring

### Major Findings

The review analyzed 80 studies and highlights the increasing role of AI-based techniques for detecting suspicious behaviour.

Important evaluation areas include:

* Accuracy
* Precision
* Recall
* AUC
* Ethical considerations
* Deployment challenges

### Research Gap

AI-based proctoring introduces additional challenges:

* Privacy
* Algorithmic bias
* False positives
* User acceptance
* Technical limitations

### Relevance to Proposed System

AI proctoring should therefore be designed as an optional modular service rather than tightly coupling the entire examination platform to a single AI model.

---

# 3.8 Online Examination Literature Comparison

| Paper                             | Main Focus            | Approach          | Major Finding                                            | Limitation / Gap                     |
| --------------------------------- | --------------------- | ----------------- | -------------------------------------------------------- | ------------------------------------ |
| Butler & Crawford (2020)          | Online examinations   | Systematic review | Security, authentication and technology are major themes | Governance and pedagogical gaps      |
| Online Assessment Security (2022) | Academic integrity    | Systematic review | Prevention and detection are key                         | Need integrated integrity strategy   |
| Muzaffar et al. (2021)            | Online exam solutions | SLR of 53 studies | Many tools, techniques and algorithms exist              | Feature and infrastructure variation |
| Automated Essay Scoring           | Automated grading     | AI/ML review      | Automated essay evaluation remains difficult             | Content/coherence evaluation         |
| Malhotra & Chhabra (2026)         | AI proctoring         | SLR of 80 studies | AI improves cheating detection potential                 | Privacy, bias and false positives    |

---

# 3.9 Identified Research Gap — Online Examination

Based on the literature, the following combined research gap is identified:

```text
Existing Online Examination Systems
                │
                ├── Authentication
                ├── Examination Management
                ├── Automated Grading
                ├── Online Proctoring
                └── Cloud Deployment
                        │
                        ▼
              Existing Limitations
                        │
          ┌─────────────┼─────────────┐
          ▼             ▼             ▼
      Security      Scalability     Privacy
          │             │             │
          └─────────────┼─────────────┘
                        ▼
                RESEARCH GAP
                        │
                        ▼
       Integrated Secure Cloud-Based
          Examination Architecture
```

### Proposed Direction

The proposed system should combine:

* Cloud scalability
* Secure authentication
* Examination management
* Reliable submission
* Automated grading
* Behaviour monitoring
* Audit logging
* Modular AI proctoring
* Fault-tolerant services

---

# 4. Project 02 — Food Delivery Ordering System

## 4.1 Problem Overview

Online food delivery systems connect customers, restaurants, delivery agents, payment services, and location services.

The main system design challenges include:

* High order volume
* Dynamic order assignment
* Delivery route optimization
* Real-time tracking
* Restaurant preparation time
* Payment processing
* Rider availability
* Peak-hour scalability
* Service reliability

Recent research increasingly treats online food delivery as a complex optimization and distributed-service problem involving order assignment, routing, uncertain demand, and real-time decisions.

---

# 4.2 Literature Search Keywords

* Online Food Delivery
* Food Delivery System
* Food Ordering System
* Food Delivery Optimization
* Order Dispatching
* Delivery Route Optimization
* Real-Time Delivery
* Last-Mile Delivery
* Microservices Food Delivery
* Cloud Food Delivery
* Rider Assignment
* Vehicle Routing Problem

---

# 4.3 Research Paper 1

## Methodological Advances in Online Food Delivery: A Systematic Review, Taxonomy, and Research Outlook

**Authors:** Mohammadamin Tavasoli, Roberto Baldacci, Vahid Kayvanfar, Yu Zhang, Chefi Triki, Adel Elomri

**Journal:** Transportation Research Part E: Logistics and Transportation Review

**Volume:** 213

**Article:** 104972

**Year:** 2026

**DOI:** 10.1016/j.tre.2026.104972

### Research Objective

The study provides a systematic review of quantitative optimization research in online food delivery.

It develops a classification based on:

* Decision level
* Problem setting
* Analytical approach

### Major Findings

The research highlights the increasing operational complexity of online food delivery and the importance of Operations Research for modeling and optimizing food delivery systems.

### Research Gap

The rapid introduction of new technologies creates new operational and modeling challenges.

Important future areas include:

* Dynamic optimization
* Data-driven decision making
* Real-time systems
* Emerging technologies

### Relevance to Proposed System

The architecture should separate core transactional services from optimization services.

For example:

```text
Order Service
      │
      ▼
Dispatch Service
      │
      ▼
Optimization Engine
      │
      ▼
Delivery Assignment
```

---

# 4.4 Research Paper 2

## Optimizing Order Bundling and Dispatching in Online Food Delivery for Enhanced Delivery Efficiency

**Journal:** Computers & Operations Research

**Volume:** 189

**Article:** 107387

**Year:** 2026

**DOI:** 10.1016/j.cor.2026.107387

### Research Objective

The study investigates how food delivery platforms can optimize courier-order matching.

Instead of assigning only one order to a courier, the research investigates concurrent order dispatching involving:

* Order bundling
* Courier matching
* Route planning

### Major Challenge

Food delivery platforms receive many orders within short time periods.

The platform therefore needs to efficiently match:

```text
Orders
   +
Couriers
   +
Restaurants
   +
Routes
```

### Research Gap

Simple one-order-to-one-courier assignment can become inefficient when order volume increases.

### Relevance to Proposed System

A dedicated Dispatch and Optimization Service can be included in the architecture.

---

# 4.5 Research Paper 3

## A Q-Learning Based Large Neighborhood Search Algorithm for Solving Food Delivery Routing Problem with Uncertain Demand and Service Time

**Journal:** Computers & Industrial Engineering

**Volume:** 210

**Article:** 111547

**Year:** 2025

**DOI:** 10.1016/j.cie.2025.111547

### Research Objective

The research addresses food delivery routing under uncertainty.

The uncertainty includes:

* Customer demand
* Rider service time
* Delivery conditions

The study proposes a Q-learning-based Large Neighborhood Search approach.

### Major Findings

The proposed approach was reported to improve scalability and solution quality compared with traditional approaches in larger instances.

The study also shows that robust optimization can improve resilience to changing demand and service times.

### Research Gap

Real-world delivery environments are dynamic and uncertain.

A static route calculated once may become inefficient when:

* New orders arrive
* Riders become unavailable
* Traffic conditions change
* Restaurant preparation is delayed

### Relevance to Proposed System

The architecture should support dynamic re-optimization.

```text
New Order
   │
   ▼
Dispatch Service
   │
   ▼
Optimization Engine
   │
   ├── Rider Location
   ├── Restaurant Status
   ├── Delivery Time
   └── Current Orders
   │
   ▼
Updated Route
```

---

# 4.6 Research Paper 4

## Cross Regional Online Food Delivery: Service Quality Optimization and Real-Time Order Assignment

**Journal:** Computers & Operations Research

**Year:** 2024

### Research Objective

The study investigates cross-regional food delivery and proposes an architecture involving real-time order assignment and optimization.

The system includes:

* Order confirmation
* Meeting-point assignment
* Transfer vehicles
* Riders
* Order routing
* Service-delay prediction

### Major Findings

The research demonstrates how order assignment and routing can be combined with service-delay prediction.

### Research Gap

Cross-region delivery introduces additional complexity because the system must coordinate multiple delivery stages and resources.

### Relevance to Proposed System

This supports separating:

* Order Service
* Dispatch Service
* Delivery Service
* Tracking Service
* Optimization Service

---

# 4.7 Research Paper 5

## Decentralizing Online Food Delivery Services: A Blockchain and IoT Model for Smart Cities

**Authors:** Ulpan Tokkozhina, Bruno Miguel Mataloto, Ana Lucia Martins, Joao C. Ferreira and others

**Journal:** Mobile Networks and Applications

**Publication:** 2023 / Volume 29, 2024

### Research Objective

The study investigates a decentralized food delivery architecture using:

* Blockchain
* IoT
* LoRa networks
* Sensors
* Smart contracts

The goal is to improve transparency, traceability, and decentralization in food delivery.

### Major Findings

Blockchain can provide:

* Distributed records
* Traceability
* Transparency
* Smart-contract-based transactions

IoT can provide sensor-based monitoring of delivery processes.

### Research Gap

Blockchain and IoT can increase system complexity and infrastructure requirements.

Therefore, they may be more appropriate for specific use cases rather than every component of a food delivery platform.

### Relevance to Proposed System

Optional IoT tracking could be introduced in future versions for:

* Temperature monitoring
* Food condition monitoring
* Delivery verification

---

# 4.8 Research Paper 6

## Feature Fusion Attention-Based Deep Reinforcement Learning for Multidepot O2O Food Delivery Route Optimization

**Journal:** International Journal of Intelligent Systems

**Year:** 2026

**DOI:** 10.1155/int/3716055

### Research Objective

The research addresses online-to-offline food delivery route planning as a complex vehicle routing problem involving:

* Multiple depots
* Capacity constraints
* Pickup and delivery
* Time windows

The proposed approach uses attention mechanisms, Graph Neural Networks, and Deep Reinforcement Learning.

### Major Findings

The research reports improvements over state-of-the-art heuristic and reinforcement-learning approaches in solution quality and computation time.

It also evaluates the approach using real-world delivery data.

### Research Gap

Advanced optimization models can provide better routes, but they require significant computational resources and high-quality data.

### Relevance to Proposed System

The optimization engine should be independently scalable so that expensive route calculations do not block normal ordering operations.

---

# 4.9 Food Delivery Literature Comparison

| Paper                        | Main Focus           | Approach                     | Major Finding                             | Limitation / Gap                            |
| ---------------------------- | -------------------- | ---------------------------- | ----------------------------------------- | ------------------------------------------- |
| Tavasoli et al. (2026)       | OFD optimization     | Systematic review            | OFD has complex optimization requirements | Emerging technologies create new challenges |
| Order Bundling (2026)        | Dispatching          | Joint order/courier matching | Bundling can improve delivery efficiency  | Dynamic assignment complexity               |
| Q-Learning Routing (2025)    | Route optimization   | Q-learning + LNS             | Handles uncertain demand/service time     | Computational complexity                    |
| Cross-Regional OFD (2024)    | Real-time assignment | Optimization + prediction    | Supports complex delivery coordination    | Multi-stage delivery complexity             |
| Blockchain + IoT (2023/2024) | Decentralization     | Blockchain + IoT + LoRa      | Improves traceability potential           | Infrastructure and complexity               |
| FADRL (2026)                 | Route optimization   | GNN + Deep RL                | Improves route solution quality/time      | Requires data and computational resources   |

---

# 4.10 Identified Research Gap — Food Delivery

The literature indicates that food delivery systems have evolved from simple ordering applications into complex real-time distributed platforms.

```text
Traditional Food Delivery
          │
          ▼
     Online Ordering
          │
          ▼
     Order Management
          │
          ▼
      Delivery
          │
          ▼
     Route Planning
          │
          ▼
      Optimization
```

However, several challenges remain:

```text
             FOOD DELIVERY
                   │
       ┌───────────┼───────────┐
       ▼           ▼           ▼
   Scalability   Real-Time   Optimization
       │           │           │
       ▼           ▼           ▼
 Peak Traffic   Tracking    Dynamic Routes
       │           │           │
       └───────────┼───────────┘
                   ▼
             RESEARCH GAP
                   │
                   ▼
       Scalable Real-Time Cloud
       Food Delivery Architecture
```

### Proposed Direction

The proposed system should combine:

* Microservices
* API Gateway
* Event-driven communication
* Real-time tracking
* Dynamic order assignment
* Route optimization
* Distributed caching
* Auto-scaling
* Fault tolerance
* Secure payment processing

---

# 5. Overall Literature Comparison

| Category                 | Online Examination                    | Food Delivery                          |
| ------------------------ | ------------------------------------- | -------------------------------------- |
| Primary Domain           | Education                             | E-Commerce / Logistics                 |
| Main Users               | Students, Teachers, Admins            | Customers, Restaurants, Riders         |
| Main Challenge           | Security & Integrity                  | Real-Time Delivery                     |
| Scalability              | High                                  | Very High                              |
| Real-Time Processing     | Medium–High                           | Very High                              |
| Security Requirement     | Very High                             | High                                   |
| Optimization Requirement | Medium                                | Very High                              |
| AI/ML Potential          | High                                  | High                                   |
| Cloud Potential          | Very High                             | Very High                              |
| Distributed Architecture | High                                  | Very High                              |
| Main Research Gap        | Integrated secure scalable assessment | Integrated real-time scalable delivery |

---

# 6. Combined Research Gap

The literature survey reveals that both selected systems require architectures capable of handling dynamic workloads.

## Online Examination

```text
High Concurrent Users
        +
Security
        +
Academic Integrity
        +
Automated Evaluation
        +
Cloud Scalability
        ↓
Secure Scalable Examination Platform
```

## Food Delivery

```text
High Order Volume
        +
Real-Time Tracking
        +
Dynamic Dispatch
        +
Route Optimization
        +
Cloud Scalability
        ↓
Real-Time Scalable Food Delivery Platform
```

---

# 7. Proposed System Design Direction

## Project 01 — Online Examination

The proposed architecture will focus on:

```text
Student
   ↓
Web / Mobile Client
   ↓
API Gateway
   ↓
Authentication
   ↓
Examination Service
   ↓
Question Service
   ↓
Submission Service
   ↓
Message Queue
   ↓
Grading Service
   ↓
Result Service
   ↓
Database
```

Additional modules:

* AI-assisted proctoring
* Behaviour analysis
* Audit logging
* Redis caching
* Monitoring
* Auto-scaling

---

## Project 02 — Food Delivery

The proposed architecture will focus on:

```text
Customer
   ↓
Web / Mobile Client
   ↓
API Gateway
   ↓
Order Service
   ├── Restaurant Service
   ├── Payment Service
   ├── Dispatch Service
   ├── Tracking Service
   └── Notification Service
             │
             ▼
       Message Queue
             │
             ▼
    Optimization Engine
             │
             ▼
       Delivery Service
             │
             ▼
          Database
```

Additional modules:

* Redis caching
* Real-time location updates
* Route optimization
* Auto-scaling
* Monitoring
* Fault tolerance

---

# 8. Final Literature Findings

## Project 01 — Online Examination

### Existing Research Shows

* Online examination security is a major research area.
* Authentication and academic integrity are important.
* Machine learning is increasingly used for cheating detection.
* Automated grading remains challenging for essays and short answers.
* Large-scale online examinations require scalable infrastructure.

### Identified Gap

There is an opportunity to integrate:

**Security + Scalability + Automated Evaluation + Monitoring**

into a unified cloud architecture.

---

## Project 02 — Food Delivery

### Existing Research Shows

* Food delivery is a complex optimization problem.
* Order dispatch and courier matching are critical.
* Dynamic demand creates routing challenges.
* Real-time optimization is increasingly important.
* Advanced ML/RL methods can improve routing.
* Cloud and distributed architectures can support large-scale operations.

### Identified Gap

There is an opportunity to integrate:

**Cloud Scalability + Real-Time Tracking + Dynamic Dispatch + Route Optimization**

into a unified architecture.

---

# 9. Conclusion

The literature survey establishes the technical foundation for both shortlisted projects.

The research indicates that:

1. **Online Examination Systems** require strong security, authentication, academic-integrity mechanisms, reliable submission, automated evaluation, and scalable infrastructure.

2. **Food Delivery Systems** require distributed services, real-time communication, dynamic dispatch, route optimization, payment processing, and scalable cloud infrastructure.

The identified research gaps will be used to design the **High-Level Architecture (HLD)** for both projects in Week 12.

---

# 10. References

1. Butler, K., & Crawford, J. (2020). *A systematic review of online examinations: A pedagogical innovation for scalable authentication and integrity*. Computers & Education, 159, 104024. DOI: 10.1016/j.compedu.2020.104024.

2. *A systematic literature review on online assessment security: Current challenges and integrity strategies*. Computers & Security, 113, 102544 (2022). DOI: 10.1016/j.cose.2021.102544.

3. Muzaffar, A. W., Tahir, M., Anwar, M. W., Chaudry, Q., Mir, S. R., & Rasheed, Y. (2021). *A Systematic Review of Online Exams Solutions in E-Learning: Techniques, Tools and Global Adoption*. IEEE Access, 9. DOI: 10.1109/ACCESS.2021.3060192.

4. *An automated essay scoring systems: A systematic literature review*. Artificial Intelligence Review. DOI: 10.1007/s10462-021-10068-2.

5. Malhotra, M., & Chhabra, I. (2026). *Ensuring academic integrity through automated online exam proctoring a decade long systematic review*. Discover Education, 5, 207. DOI: 10.1007/s44217-026-01224-3.

6. Tavasoli, M., Baldacci, R., Kayvanfar, V., Zhang, Y., Triki, C., & Elomri, A. (2026). *Methodological Advances in Online Food Delivery: A Systematic Review, Taxonomy, and Research Outlook*. Transportation Research Part E, 213, 104972. DOI: 10.1016/j.tre.2026.104972.

7. *Optimizing order bundling and dispatching in online food delivery for enhanced delivery efficiency*. Computers & Operations Research, 189, 107387 (2026). DOI: 10.1016/j.cor.2026.107387.

8. *A Q-learning based large neighborhood search algorithm for solving food delivery routing problem with uncertain demand and service time*. Computers & Industrial Engineering, 210, 111547 (2025). DOI: 10.1016/j.cie.2025.111547.

9. *Cross regional online food delivery: Service quality optimization and real-time order assignment*. Computers & Operations Research (2024).

10. Tokkozhina, U., Mataloto, B. M., Martins, A. L., Ferreira, J. C., et al. *Decentralizing Online Food Delivery Services: A Blockchain and IoT Model for Smart Cities*. Mobile Networks and Applications, 29, 59–69 (2024).

11. Zou et al. (2026). *Feature Fusion Attention-Based Deep Reinforcement Learning for Multidepot O2O Food Delivery Route Optimization*. International Journal of Intelligent Systems. DOI: 10.1155/int/3716055.
