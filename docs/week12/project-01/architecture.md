# Project 01 — High-Level Architecture

## Online Quiz / Examination Management System

---

# 1. System Overview

The Online Quiz / Examination Management System is a cloud-based platform for conducting secure and scalable online examinations.

The architecture separates major functions into independent services so that each service can be scaled and maintained independently.

---

# 2. Architecture Goals

The architecture is designed to provide:

* Scalability
* High availability
* Security
* Reliability
* Performance
* Fault tolerance
* Maintainability
* Secure examination processing

---

# 3. High-Level Architecture

```text
                         ┌─────────────────────┐
                         │       STUDENT       │
                         │    Web / Mobile     │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │    Load Balancer    │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │     API Gateway     │
                         └──────────┬──────────┘
                                    │
              ┌─────────────────────┼─────────────────────┐
              │                     │                     │
              ▼                     ▼                     ▼
     ┌────────────────┐   ┌────────────────┐   ┌────────────────┐
     │ Authentication │   │ Examination    │   │ Question       │
     │    Service     │   │    Service     │   │    Service     │
     └───────┬────────┘   └───────┬────────┘   └───────┬────────┘
             │                    │                    │
             └────────────────────┼────────────────────┘
                                  │
                                  ▼
                       ┌─────────────────────┐
                       │  Submission Service │
                       └──────────┬──────────┘
                                  │
                                  ▼
                       ┌─────────────────────┐
                       │    Message Queue    │
                       │   Kafka / RabbitMQ  │
                       └──────────┬──────────┘
                                  │
                                  ▼
                       ┌─────────────────────┐
                       │   Grading Service   │
                       └──────────┬──────────┘
                                  │
                         ┌────────┴────────┐
                         ▼                 ▼
                ┌────────────────┐ ┌────────────────┐
                │ Result Service │ │   Monitoring   │
                │                │ │    Service     │
                └───────┬────────┘ └────────────────┘
                        │
                        ▼
               ┌────────────────────┐
               │     PostgreSQL     │
               │      Database      │
               └─────────┬──────────┘
                         │
                         ▼
                  ┌──────────────┐
                  │ Redis Cache  │
                  └──────────────┘
```

---

# 4. Component Responsibilities

## 4.1 Load Balancer

Distributes incoming requests across multiple application instances.

### Responsibilities

* Traffic distribution
* Health checks
* Failover
* High availability

---

## 4.2 API Gateway

Acts as the main entry point for client requests.

### Responsibilities

* Request routing
* Authentication forwarding
* Rate limiting
* API monitoring
* Request validation

---

## 4.3 Authentication Service

Handles user authentication and authorization.

### Responsibilities

* Login
* Registration
* Token generation
* Role management
* Session validation

### Roles

* Student
* Teacher
* Administrator

---

## 4.4 Examination Service

Manages examination lifecycle.

### Responsibilities

* Create examination
* Publish examination
* Schedule examination
* Start examination
* End examination
* Manage examination attempts

---

## 4.5 Question Service

Manages examination questions.

### Responsibilities

* Question creation
* Question retrieval
* Question categorization
* Question randomization
* Question bank management

---

## 4.6 Submission Service

Handles student answer submissions.

### Responsibilities

* Receive answers
* Validate submissions
* Auto-save answers
* Store submission events
* Prevent duplicate submissions

---

## 4.7 Message Queue

Kafka or RabbitMQ can be used for asynchronous processing.

### Responsibilities

* Decouple services
* Handle high traffic
* Buffer examination submissions
* Provide reliable event processing

Example:

```text
Student Submission
       ↓
Submission Service
       ↓
Message Queue
       ↓
Grading Service
```

---

## 4.8 Grading Service

Processes submitted answers.

### Responsibilities

* MCQ grading
* Programming-question evaluation
* Score calculation
* Result generation

For programming questions, submitted code should execute inside an isolated sandbox.

---

## 4.9 Result Service

Manages examination results.

### Responsibilities

* Calculate final score
* Store result
* Generate result summary
* Provide result to student
* Generate examination analytics

---

## 4.10 Monitoring Service

Monitors system health and examination activity.

### Responsibilities

* Service health monitoring
* Error monitoring
* Performance monitoring
* Suspicious activity logging
* Infrastructure monitoring

---

# 5. Data Flow

```text
1. Student Login
       ↓
2. Authentication Service
       ↓
3. Examination Selection
       ↓
4. Examination Service
       ↓
5. Question Service
       ↓
6. Questions Delivered
       ↓
7. Student Answers
       ↓
8. Submission Service
       ↓
9. Message Queue
       ↓
10. Grading Service
       ↓
11. Result Service
       ↓
12. Database
       ↓
13. Result Returned to Student
```

---

# 6. Database Design

## Main Entities

### User

```text
User
-----
user_id
name
email
password_hash
role
created_at
```

### Examination

```text
Examination
-----------
exam_id
title
description
start_time
end_time
duration
status
created_by
```

### Question

```text
Question
--------
question_id
exam_id
question_text
question_type
marks
difficulty
```

### Submission

```text
Submission
----------
submission_id
exam_id
user_id
submitted_at
status
```

### Answer

```text
Answer
------
answer_id
submission_id
question_id
answer_data
marks
```

### Result

```text
Result
------
result_id
exam_id
user_id
score
percentage
status
generated_at
```

---

# 7. Scalability Strategy

The system must support a large number of students starting examinations simultaneously.

### Horizontal Scaling

Multiple instances of services can run simultaneously.

```text
              Load Balancer
                    │
        ┌───────────┼───────────┐
        ▼           ▼           ▼
     Server 1    Server 2    Server 3
```

### Caching

Redis can cache:

* Examination metadata
* Question sets
* User sessions
* Frequently accessed data

### Asynchronous Processing

The message queue prevents grading operations from blocking answer submission.

### Database Scaling

Use:

* Indexing
* Read replicas
* Connection pooling
* Partitioning where necessary

---

# 8. Security Architecture

```text
Client
  ↓
HTTPS / TLS
  ↓
API Gateway
  ↓
Authentication
  ↓
Authorization
  ↓
Application Services
  ↓
Encrypted Database
```

## Security Controls

* HTTPS/TLS
* JWT/OAuth authentication
* Role-Based Access Control
* Password hashing
* Input validation
* Rate limiting
* Secure cookies/tokens
* Database encryption
* Audit logs

---

# 9. Examination Integrity

Potential mechanisms include:

* Randomized questions
* Randomized answer choices
* Time limits
* Session monitoring
* Tab-switch detection
* Suspicious behaviour logging
* Question-set variation
* Audit trails

AI-based proctoring can be added as an independent service in future versions.

---

# 10. Fault Tolerance

The system should continue operating even if an individual component fails.

```text
Service Failure
      │
      ▼
Health Check
      │
      ▼
Remove Failed Instance
      │
      ▼
Traffic Redirected
      │
      ▼
Healthy Instance
```

The message queue also provides buffering when downstream services temporarily become unavailable.

---

# 11. Cloud Deployment

A possible cloud deployment is:

```text
                         Internet
                            │
                            ▼
                     Cloud Load Balancer
                            │
                            ▼
                       API Gateway
                            │
              ┌─────────────┼─────────────┐
              ▼             ▼             ▼
          Auth Pods     Exam Pods     Question Pods
              │             │             │
              └─────────────┼─────────────┘
                            ▼
                       Message Queue
                            │
                            ▼
                       Grading Pods
                            │
                            ▼
                     PostgreSQL
                            │
                            ▼
                         Backup
```

---

# 12. Technology Stack

| Layer          | Technology            |
| -------------- | --------------------- |
| Client         | React                 |
| Backend        | Node.js / Spring Boot |
| API Gateway    | NGINX                 |
| Load Balancer  | Cloud Load Balancer   |
| Database       | PostgreSQL            |
| Cache          | Redis                 |
| Message Queue  | Apache Kafka          |
| Authentication | JWT / OAuth 2.0       |
| Container      | Docker                |
| Orchestration  | Kubernetes            |
| Cloud          | AWS / Azure / GCP     |
| Monitoring     | Prometheus + Grafana  |

---

# 13. Non-Functional Requirements

## Performance

The system should provide low-latency responses during normal examination operations.

## Scalability

The system should support horizontal scaling during examination peaks.

## Availability

Critical services should be deployed redundantly.

## Security

Student information, examination content, and results must be protected.

## Reliability

Submitted answers should not be lost because of temporary service failures.

## Maintainability

Services should be independently deployable and maintainable.

---

# 14. Future Enhancements

Possible future extensions include:

* AI-based proctoring
* Face verification
* Behaviour analysis
* AI-assisted question generation
* NLP-based answer evaluation
* Advanced examination analytics
* Personalized assessments
* Multi-region deployment

---

# 15. Final Architecture Summary

```text
                    ONLINE EXAMINATION SYSTEM

                           Student
                              │
                              ▼
                     Web / Mobile Client
                              │
                              ▼
                       Load Balancer
                              │
                              ▼
                         API Gateway
                              │
            ┌─────────────────┼─────────────────┐
            ▼                 ▼                 ▼
         Auth             Examination        Question
        Service             Service           Service
            │                 │                 │
            └─────────────────┼─────────────────┘
                              ▼
                     Submission Service
                              │
                              ▼
                        Message Queue
                              │
                              ▼
                       Grading Service
                              │
                     ┌────────┴────────┐
                     ▼                 ▼
               Result Service      Monitoring
                     │              Service
                     ▼
                 PostgreSQL
                     │
                     ▼
                  Redis Cache
```

---

# 16. Conclusion

The proposed architecture provides a scalable, secure, and reliable foundation for an online examination platform.

The service-based architecture separates authentication, examination management, question delivery, submission, grading, and result processing.

Cloud infrastructure, caching, asynchronous messaging, horizontal scaling, and fault tolerance enable the system to support large-scale online examinations.
