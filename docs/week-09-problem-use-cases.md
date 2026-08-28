# Week 9: 5 Problem Use Cases (5 Different System Designs)

**Week:** 9  

## Objective

Identify 5 distinct system design problems and define one key use case for each. These will form the basis for shortlisting 2 final projects in Week 10.

---

## 1. Cloud-Based Expense Tracking & Analytics System

**Type:** High System Design (Cloud-Deployable)

### Use Case: Transaction Logging & Analytics Dashboard

**Description:**  
A user logs daily income and expenses with categories (e.g., food, travel, salary). The system aggregates this data and displays an interactive dashboard with:

- Monthly spending trends  
- Category-wise breakdown  
- Budget alerts and anomaly detection  

**Actors:** User, Transaction Service, Analytics Service  
**Pre-conditions:** User is registered and logged in  
**Post-conditions:** Transactions are stored; dashboard reflects updated data  

**Key Challenges:**  
- Efficient aggregation of large transaction datasets  
- Real-time dashboard updates  
- Integration of ML for predictions and anomaly detection  

---

## 2. Online Quiz / Exam Management System

**Type:** High System Design (Cloud-Deployable)

### Use Case: Timed Exam Attempt with Auto-Grading

**Description:**  
A student starts a timed exam, answers MCQs and coding questions, and submits. The system:

- Enforces time limits  
- Auto-saves answers periodically  
- Auto-grades MCQs and code submissions immediately after submission  

**Actors:** Student, Attempt Service, Grading Service  
**Pre-conditions:** Exam is published; student is enrolled  
**Post-conditions:** Attempt is recorded; grades are computed and stored  

**Key Challenges:**  
- Handling high concurrency during peak exam times  
- Secure code execution in isolated sandboxes  
- Preventing cheating (tab-switch detection, randomized questions)  

---

## 3. Real-Time Collaborative Whiteboard

**Type:** High System Design (Cloud-Deployable)

### Use Case: Multi-User Real-Time Drawing

**Description:**  
Multiple users join a shared whiteboard room and draw/annotate simultaneously. Changes are synced in real time so all users see the same canvas.

**Actors:** User, WebSocket Server, Whiteboard Service  
**Pre-conditions:** User has a shareable room link  
**Post-conditions:** All users see synchronized canvas updates  

**Key Challenges:**  
- Low-latency real-time sync via WebSockets  
- Conflict resolution when multiple users edit simultaneously  
- Scaling to many concurrent rooms and users  

---

## 4. Food Delivery Ordering System

**Type:** Low System Design (Domain Modeling & Patterns)

### Use Case: Order Placement & Lifecycle Management

**Description:**  
A customer places an order from a restaurant. The system manages the order lifecycle:

- Order Placed → Preparing → Picked Up → Delivered  
- Assigns a delivery agent based on proximity and availability  

**Actors:** Customer, Restaurant, Delivery Agent, Order Service  
**Pre-conditions:** Restaurant is active; delivery agents are available  
**Post-conditions:** Order is created and assigned; status is tracked  

**Key Challenges:**  
- State machine for order status transitions  
- Design patterns (Strategy for pricing, Observer for status updates)  
- Clean domain modeling without distributed complexity  

---

## 5. Splitwise-Style Expense Splitting System

**Type:** Low System Design (Domain Modeling & Algorithms)

### Use Case: Group Expense Splitting & Debt Simplification

**Description:**  
A group of users adds shared expenses (e.g., rent, food). The system:

- Splits expenses equally, unequally, or by percentage  
- Calculates net balances for each user  
- Suggests minimal transactions to settle all debts  

**Actors:** User, Group, Expense, Split, Settlement  
**Pre-conditions:** Group is created; users are added  
**Post-conditions:** Balances are calculated; settlement suggestions are generated  

**Key Challenges:**  
- Multiple split strategies (equal, unequal, percentage)  
- Efficient balance ledger (avoid tracking every individual transaction)  
- Debt simplification algorithm (minimize number of transactions)  

---

## Next Steps (Week 10)

- Review all 5 use cases.  
- Shortlist 2 problems (one per final project) based on:  
  - Complexity and learning potential  
  - Availability of IEEE/research papers  
  - Alignment with cloud-deployable high system design goals  

**Deliverable:** [`week-10-2-problems-shortlist.md`](week-10-2-problems-shortlist.md)
