# Week 10: Problem Shortlisting

**Week:** 10
**Topic:** Selection of 2 Problems from 5 System Design Problems

---

## 🎯 Objective

Evaluate the five system design problems identified in Week 09 and shortlist the **best 2 problems** for detailed literature survey and High-Level Architecture (HLD) design.

The selection is based on technical complexity, scalability, cloud deployment potential, research availability, innovation, security, and implementation feasibility.

---

# 📋 Problems Identified in Week 09

| # | Problem                                         |
| - | ----------------------------------------------- |
| 1 | Cloud-Based Expense Tracking & Analytics System |
| 2 | Online Quiz / Examination Management System     |
| 3 | Real-Time Collaborative Whiteboard System       |
| 4 | Food Delivery Ordering System                   |
| 5 | Splitwise-Style Expense Splitting System        |

---

# 📊 Evaluation Criteria

Each problem is evaluated on a **1–5 scale**.

| Score | Meaning   |
| ----: | --------- |
|     1 | Very Low  |
|     2 | Low       |
|     3 | Medium    |
|     4 | High      |
|     5 | Very High |

### Criteria

* **System Complexity** – Technical and architectural complexity
* **Scalability** – Ability to support increasing users and workload
* **Cloud Potential** – Suitability for cloud deployment
* **Research Potential** – Availability of research papers and studies
* **Innovation** – Scope for improvements and new features
* **Security** – Security challenges and design opportunities
* **Feasibility** – Practicality of implementation

---

# 📈 Problem Evaluation

| Problem                      | Complexity | Scalability | Cloud | Research | Innovation | Security | Feasibility |  Total |
| ---------------------------- | ---------: | ----------: | ----: | -------: | ---------: | -------: | ----------: | -----: |
| Expense Tracking & Analytics |          4 |           5 |     5 |        4 |          4 |        4 |           4 | **30** |
| Online Examination System    |          5 |           5 |     5 |        5 |          4 |        5 |           4 | **33** |
| Collaborative Whiteboard     |          5 |           5 |     5 |        4 |          5 |        4 |           3 | **31** |
| Food Delivery System         |          5 |           5 |     5 |        5 |          4 |        4 |           5 | **33** |
| Expense Splitting System     |          3 |           3 |     3 |        4 |          3 |        3 |           5 | **24** |

---

# 🏆 Ranking

| Rank | Problem                                         |  Score |
| ---: | ----------------------------------------------- | -----: |
| 🥇 1 | Online Quiz / Examination Management System     | **33** |
| 🥇 1 | Food Delivery Ordering System                   | **33** |
| 🥉 3 | Real-Time Collaborative Whiteboard System       | **31** |
|    4 | Cloud-Based Expense Tracking & Analytics System | **30** |
|    5 | Splitwise-Style Expense Splitting System        | **24** |

---

# ✅ Shortlisted Problem 1

## Online Quiz / Examination Management System

### Why Selected?

The Online Examination System provides significant system design challenges related to:

* High concurrent users
* Cloud scalability
* Authentication and authorization
* Secure examination management
* Automatic grading
* Real-time examination monitoring
* Reliable answer submission
* Secure code execution

### Research Potential

The problem has strong research potential in areas such as:

* Online assessment systems
* E-learning platforms
* Secure online examinations
* Automated grading
* Cloud-based education systems
* Examination security

### Architecture Potential

The system can be designed using:

* API Gateway
* Authentication Service
* Examination Service
* Question Service
* Submission Service
* Grading Service
* Result Service
* Redis Cache
* Message Queue
* Relational Database
* Cloud infrastructure

---

# ✅ Shortlisted Problem 2

## Food Delivery Ordering System

### Why Selected?

The Food Delivery System provides a strong distributed-system design problem involving multiple users, services, and real-time operations.

### Key Challenges

* Restaurant management
* Menu management
* Order processing
* Payment processing
* Delivery assignment
* Real-time location tracking
* Order status management
* Notification systems
* High traffic during peak hours

### Research Potential

The problem has research potential in:

* Distributed systems
* Microservices
* Cloud computing
* Location-based services
* Route optimization
* Real-time tracking
* Recommendation systems
* Scalable e-commerce platforms

### Architecture Potential

The system can be designed using:

* API Gateway
* Authentication Service
* Restaurant Service
* Menu Service
* Order Service
* Payment Service
* Delivery Service
* Tracking Service
* Notification Service
* Redis Cache
* Message Queue
* Database
* Cloud infrastructure

---

# ❌ Non-Shortlisted Problems

## 3. Real-Time Collaborative Whiteboard System

**Score:** 31

### Reason for Not Shortlisting

Although the system has strong scalability and real-time communication challenges, its implementation complexity and synchronization requirements make it less suitable than the two selected problems for the current project scope.

---

## 4. Cloud-Based Expense Tracking & Analytics System

**Score:** 30

### Reason for Not Shortlisting

The system provides good cloud and analytics opportunities, but the overall distributed-system complexity and research scope are comparatively lower than the shortlisted problems.

---

## 5. Splitwise-Style Expense Splitting System

**Score:** 24

### Reason for Not Shortlisting

The system is useful for understanding domain modeling and algorithms, but it provides comparatively fewer opportunities for large-scale cloud architecture and distributed system design.

---

# 🎯 Final Selection

After evaluating all five problems, the following two problems are selected:

```text
┌────────────────────────────────────────────┐
│              FINAL SELECTION               │
├────────────────────────────────────────────┤
│                                            │
│  PROJECT 01                                │
│  Online Quiz / Examination Management      │
│  System                                    │
│                                            │
│  PROJECT 02                                │
│  Food Delivery Ordering System             │
│                                            │
└────────────────────────────────────────────┘
```

---

# 🔄 Week 10 Decision Flow

```text
                 5 PROBLEMS
                     │
                     ▼
        ┌─────────────────────────┐
        │     EVALUATION          │
        │                         │
        │ Complexity              │
        │ Scalability             │
        │ Cloud Potential         │
        │ Research Potential      │
        │ Innovation              │
        │ Security                │
        │ Feasibility             │
        └────────────┬────────────┘
                     │
                     ▼
               RANKING
                     │
              ┌──────┴──────┐
              ▼             ▼
       PROJECT 01      PROJECT 02
       Online Exam     Food Delivery
              │             │
              └──────┬──────┘
                     ▼
               WEEK 11
          Literature Survey
```

---

# 📌 Week 10 Conclusion

Five system design problems were evaluated using multiple technical and architectural criteria.

The final two problems selected for further development are:

### 1. Online Quiz / Examination Management System

### 2. Food Delivery Ordering System

These two problems will proceed to **Week 11 Literature Survey** and subsequently to **Week 12 High-Level Architecture Design**.

---

## 🔜 Next Step

**Week 11 → Literature Survey for the 2 Selected Problems**
