# Week 09: Problem Use Cases

**Week:** 09
**Topic:** 5 Problem Use Cases – 5 Different System Designs

---

## 🎯 Objective

Identify **5 different real-world system design problems** and define a key use case for each problem.

These 5 problems will be evaluated in **Week 10**, where 2 problems will be shortlisted for further study.

---

# 1. Cloud-Based Expense Tracking & Analytics System

## System Type

Cloud-Based Data Management and Analytics System

## Use Case

**Transaction Logging and Analytics Dashboard**

## Problem Description

Users need an efficient way to record, manage, and analyze their income and expenses. The system stores financial transactions and provides analytics through an interactive dashboard.

## Actors

* User
* Transaction Service
* Analytics Service
* Notification Service

## Main Flow

1. User logs into the system.
2. User adds an income or expense.
3. Transaction Service validates the transaction.
4. Transaction is stored in the database.
5. Analytics Service processes the transaction.
6. Dashboard updates financial statistics.
7. Notification Service generates budget alerts when required.

## Preconditions

* User is registered.
* User is authenticated.

## Postconditions

* Transaction is stored.
* Financial statistics are updated.
* Budget alerts are generated when required.

## Key Features

* Income and expense tracking
* Category management
* Budget management
* Analytics dashboard
* Spending trends
* Budget alerts
* Anomaly detection

## Key Challenges

* Handling large transaction datasets
* Real-time analytics
* Data consistency
* Secure financial data storage
* Scalable cloud infrastructure

---

# 2. Online Quiz / Examination Management System

## System Type

Cloud-Based Examination and Assessment System

## Use Case

**Timed Examination with Automatic Grading**

## Problem Description

Educational institutions require a reliable online examination platform that can support a large number of students simultaneously while securely managing examinations, submissions, and results.

## Actors

* Student
* Teacher
* Administrator
* Examination Service
* Question Service
* Grading Service

## Main Flow

1. Student logs into the system.
2. Student selects the available examination.
3. System verifies examination eligibility.
4. Examination starts and the timer begins.
5. Student answers questions.
6. Answers are automatically saved.
7. Student submits the examination.
8. Grading Service evaluates the answers.
9. Result is generated and stored.
10. Student views the result.

## Preconditions

* Student is registered.
* Student is enrolled.
* Examination is published.

## Postconditions

* Examination attempt is stored.
* Answers are stored.
* Result is generated.

## Key Features

* User authentication
* Examination management
* Question bank
* Timed examinations
* Auto-save
* Automatic grading
* Result generation
* Examination analytics

## Key Challenges

* Handling high concurrent users
* Secure examination environment
* Preventing unauthorized access
* Reliable auto-save
* Automatic grading
* Secure code execution for programming questions

---

# 3. Real-Time Collaborative Whiteboard System

## System Type

Real-Time Distributed Collaboration System

## Use Case

**Multi-User Real-Time Whiteboard Collaboration**

## Problem Description

Remote teams and students need a platform where multiple users can collaborate on a shared digital whiteboard in real time.

## Actors

* User
* Collaboration Service
* WebSocket Server
* Storage Service

## Main Flow

1. User creates or joins a whiteboard room.
2. System establishes a real-time connection.
3. User performs a drawing or editing operation.
4. Operation is sent to the server.
5. Server validates the operation.
6. Server broadcasts the operation to connected users.
7. Other users receive the update.
8. Whiteboard state is synchronized.

## Preconditions

* User has access to a whiteboard room.
* Collaboration session is active.

## Postconditions

* All connected users receive the latest changes.
* Whiteboard state is stored.

## Key Features

* Real-time drawing
* Multiple users
* Room management
* Text and shape tools
* Real-time synchronization
* Whiteboard history
* Persistent storage

## Key Challenges

* Low-latency communication
* WebSocket scalability
* Concurrent editing
* Conflict resolution
* State synchronization
* Handling disconnected users

---

# 4. Food Delivery Ordering System

## System Type

Cloud-Based Distributed E-Commerce System

## Use Case

**Order Placement and Delivery Lifecycle Management**

## Problem Description

Customers need a platform to discover restaurants, order food, make payments, and track deliveries in real time.

## Actors

* Customer
* Restaurant
* Delivery Agent
* Order Service
* Payment Service
* Tracking Service

## Main Flow

1. Customer logs into the application.
2. Customer searches for restaurants.
3. Customer selects food items.
4. Customer adds items to the cart.
5. Customer places the order.
6. Payment Service processes the payment.
7. Restaurant receives the order.
8. Restaurant prepares the food.
9. Delivery Agent is assigned.
10. Delivery Agent picks up the order.
11. Customer tracks the delivery.
12. Order is delivered.

## Preconditions

* Customer is authenticated.
* Restaurant is active.
* Food items are available.
* Delivery service is available.

## Postconditions

* Order is completed.
* Payment is recorded.
* Delivery status is updated.

## Key Features

* Restaurant discovery
* Menu management
* Shopping cart
* Order management
* Online payment
* Delivery assignment
* Real-time tracking
* Notifications
* Order history

## Key Challenges

* Order state management
* Payment reliability
* Delivery assignment
* Real-time tracking
* Location services
* High traffic during peak hours
* Distributed service communication

---

# 5. Splitwise-Style Expense Splitting System

## System Type

Collaborative Financial Management System

## Use Case

**Group Expense Splitting and Debt Settlement**

## Problem Description

Groups of users frequently share expenses such as food, rent, travel, and events. Manually calculating individual balances can be complex and error-prone.

The system automatically calculates how much each member owes and generates settlement recommendations.

## Actors

* User
* Group Service
* Expense Service
* Settlement Service

## Main Flow

1. User creates a group.
2. Members join the group.
3. User records a shared expense.
4. Members involved in the expense are selected.
5. User selects the split method.
6. System calculates individual shares.
7. Member balances are updated.
8. Settlement Service calculates optimized payments.
9. Users settle their outstanding balances.

## Preconditions

* Group exists.
* Users are members of the group.

## Postconditions

* Expense is recorded.
* Individual balances are updated.
* Settlement recommendations are generated.

## Key Features

* Group management
* Expense tracking
* Equal splitting
* Unequal splitting
* Percentage-based splitting
* Balance calculation
* Debt simplification
* Settlement tracking

## Key Challenges

* Multiple split strategies
* Accurate balance calculation
* Debt simplification
* Transaction consistency
* Concurrent updates

---

# 📊 Comparison of 5 Problems

| # | Problem                      | Complexity | Scalability | Cloud Potential | Research Potential |
| - | ---------------------------- | ---------- | ----------- | --------------- | ------------------ |
| 1 | Expense Tracking & Analytics | High       | High        | High            | High               |
| 2 | Online Examination System    | High       | High        | High            | High               |
| 3 | Collaborative Whiteboard     | High       | Very High   | Very High       | High               |
| 4 | Food Delivery System         | High       | High        | High            | High               |
| 5 | Expense Splitting System     | Medium     | Medium      | Medium          | Medium             |

---

# 🔍 Evaluation Criteria for Week 10

The five problems will be evaluated using:

1. **System Complexity**
2. **Scalability**
3. **Cloud Deployment Potential**
4. **Real-World Relevance**
5. **Research Availability**
6. **Innovation Potential**
7. **Implementation Feasibility**
8. **Security Requirements**
9. **Performance Requirements**
10. **Future Expansion Potential**

---

# 📌 Week 9 Conclusion

Five different system design problems have been identified:

1. **Cloud-Based Expense Tracking & Analytics System**
2. **Online Quiz / Examination Management System**
3. **Real-Time Collaborative Whiteboard System**
4. **Food Delivery Ordering System**
5. **Splitwise-Style Expense Splitting System**

The five problems will be evaluated in **Week 10**, and the best **2 problems out of 5** will be shortlisted for literature survey and high-level architecture design.

---

## 🔄 Next Step

**Week 10 → Shortlist 2 Problems out of 5**
