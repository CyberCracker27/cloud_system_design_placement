# Project 02 — High-Level Architecture

## Food Delivery Ordering System

---

# 1. System Overview

The Food Delivery Ordering System is a cloud-based distributed platform that connects customers with restaurants and delivery agents.

The system supports the complete food delivery lifecycle:

```text
Restaurant Discovery
        ↓
Menu Selection
        ↓
Cart
        ↓
Order
        ↓
Payment
        ↓
Restaurant Preparation
        ↓
Delivery Assignment
        ↓
Real-Time Tracking
        ↓
Delivery
```

---

# 2. Architecture Goals

The architecture is designed to provide:

* High scalability
* High availability
* Low-latency responses
* Real-time tracking
* Secure payments
* Reliable order processing
* Fault tolerance
* Independent service scaling
* Cloud-native deployment

---

# 3. High-Level Architecture

```text
                              ┌──────────────────────┐
                              │      CUSTOMER        │
                              │    Web / Mobile      │
                              └──────────┬───────────┘
                                         │
                                         ▼
                              ┌──────────────────────┐
                              │    Load Balancer     │
                              └──────────┬───────────┘
                                         │
                                         ▼
                              ┌──────────────────────┐
                              │     API Gateway      │
                              └──────────┬───────────┘
                                         │
              ┌──────────────────────────┼──────────────────────────┐
              │                          │                          │
              ▼                          ▼                          ▼
     ┌────────────────┐        ┌────────────────┐        ┌────────────────┐
     │ Authentication │        │  Restaurant    │        │     Order      │
     │    Service     │        │    Service     │        │    Service     │
     └────────────────┘        └───────┬────────┘        └───────┬────────┘
                                       │                          │
                                       │                          ▼
                                       │                 ┌────────────────┐
                                       │                 │ Payment Service│
                                       │                 └───────┬────────┘
                                       │                          │
                                       └──────────────┬───────────┘
                                                      ▼
                                           ┌────────────────────┐
                                           │    Message Queue    │
                                           │   Kafka / RabbitMQ  │
                                           └──────────┬─────────┘
                                                      │
                          ┌───────────────────────────┼─────────────────────┐
                          │                           │                     │
                          ▼                           ▼                     ▼
                 ┌────────────────┐         ┌────────────────┐    ┌────────────────┐
                 │   Restaurant   │         │    Delivery    │    │ Notification   │
                 │    Service     │         │    Service     │    │    Service     │
                 └────────────────┘         └───────┬────────┘    └────────────────┘
                                                    │
                                                    ▼
                                           ┌──────────────────┐
                                           │ Tracking Service  │
                                           └────────┬─────────┘
                                                    │
                                                    ▼
                                           ┌──────────────────┐
                                           │    PostgreSQL     │
                                           │     Database      │
                                           └────────┬─────────┘
                                                    │
                                                    ▼
                                              ┌──────────┐
                                              │  Redis   │
                                              │  Cache   │
                                              └──────────┘
```

---

# 4. Component Responsibilities

## 4.1 Load Balancer

Distributes incoming traffic across multiple application instances.

### Responsibilities

* Traffic distribution
* Health checks
* Failover
* High availability

---

# 4.2 API Gateway

The API Gateway acts as the entry point for all client requests.

### Responsibilities

* Request routing
* Authentication forwarding
* Rate limiting
* API monitoring
* Request validation

---

# 4.3 Authentication Service

Manages user authentication and authorization.

### Supported Roles

* Customer
* Restaurant
* Delivery Agent
* Administrator

### Responsibilities

* Registration
* Login
* Token generation
* Role management
* Session validation

---

# 4.4 Restaurant Service

Manages restaurants and their menus.

### Responsibilities

* Restaurant registration
* Restaurant availability
* Menu management
* Food item management
* Restaurant status

---

# 4.5 Order Service

Manages the complete order lifecycle.

### Order States

```text
Order Placed
     ↓
Payment Confirmed
     ↓
Restaurant Accepted
     ↓
Preparing
     ↓
Ready for Pickup
     ↓
Picked Up
     ↓
Out for Delivery
     ↓
Delivered
```

### Responsibilities

* Create order
* Update order
* Track order status
* Cancel order
* Maintain order history

---

# 4.6 Payment Service

Handles payment processing.

### Responsibilities

* Payment initiation
* Payment confirmation
* Payment failure handling
* Refund processing
* Transaction records

The system should avoid storing sensitive payment credentials directly and should use a trusted payment provider.

---

# 4.7 Message Queue

Kafka or RabbitMQ can be used for asynchronous communication.

### Example Events

```text
OrderCreated
     ↓
PaymentCompleted
     ↓
RestaurantAccepted
     ↓
FoodPrepared
     ↓
DeliveryAssigned
     ↓
OrderDelivered
```

### Benefits

* Service decoupling
* Reliable event processing
* Traffic buffering
* Asynchronous communication
* Improved scalability

---

# 4.8 Delivery Service

Manages delivery agents and assignment.

### Responsibilities

* Rider registration
* Rider availability
* Delivery assignment
* Pickup confirmation
* Delivery completion

---

# 4.9 Tracking Service

Provides real-time delivery tracking.

### Responsibilities

* Receive rider location
* Update delivery location
* Track delivery status
* Send location updates to customers

Example:

```text
Delivery Agent
      │
      ▼
GPS / Mobile App
      │
      ▼
Tracking Service
      │
      ▼
Redis / Real-Time Store
      │
      ▼
Customer Application
```

---

# 4.10 Notification Service

Sends notifications to customers, restaurants, and delivery agents.

### Notification Types

* Order confirmation
* Payment confirmation
* Restaurant accepted
* Food preparation started
* Delivery assigned
* Rider nearby
* Order delivered
* Payment failure

---

# 5. Complete Order Data Flow

```text
Customer
   │
   ▼
Restaurant Search
   │
   ▼
Menu Service
   │
   ▼
Cart
   │
   ▼
Order Service
   │
   ▼
Payment Service
   │
   ▼
Payment Gateway
   │
   ▼
Message Queue
   │
   ▼
Restaurant
   │
   ▼
Food Preparation
   │
   ▼
Delivery Service
   │
   ▼
Delivery Agent
   │
   ▼
Tracking Service
   │
   ▼
Customer
```

---

# 6. Database Design

## User

```text
User
-----
user_id
name
email
password_hash
role
phone
created_at
```

## Restaurant

```text
Restaurant
----------
restaurant_id
name
address
location
status
rating
created_at
```

## Menu Item

```text
MenuItem
--------
item_id
restaurant_id
name
description
price
availability
category
```

## Order

```text
Order
-----
order_id
customer_id
restaurant_id
delivery_agent_id
total_amount
payment_status
order_status
created_at
```

## Order Item

```text
OrderItem
---------
order_item_id
order_id
item_id
quantity
price
```

## Payment

```text
Payment
-------
payment_id
order_id
amount
payment_method
payment_status
transaction_reference
created_at
```

## Delivery

```text
Delivery
--------
delivery_id
order_id
agent_id
pickup_location
delivery_location
status
assigned_at
completed_at
```

---

# 7. Scalability Strategy

Food delivery platforms experience significant traffic variation.

For example:

```text
Normal Traffic
      │
      ▼
     Peak
      │
      ▼
Dinner / Weekend Traffic
```

The architecture should support automatic scaling.

## Horizontal Scaling

```text
                 Load Balancer
                      │
          ┌───────────┼───────────┐
          ▼           ▼           ▼
      Order Pod   Order Pod   Order Pod
```

## Caching

Redis can cache:

* Restaurant listings
* Menus
* Restaurant availability
* Popular food items
* Delivery locations

## Database Scaling

Use:

* Database indexing
* Read replicas
* Connection pooling
* Partitioning where required

---

# 8. Delivery Assignment

The Delivery Service can select an available delivery agent using factors such as:

* Distance
* Availability
* Current workload
* Estimated delivery time
* Restaurant location
* Customer location

Example:

```text
                 New Order
                     │
                     ▼
             Find Available Riders
                     │
                     ▼
              Calculate Distance
                     │
                     ▼
             Estimate Delivery Time
                     │
                     ▼
              Select Best Rider
                     │
                     ▼
              Assign Delivery
```

---

# 9. Route Optimization

The system can use an optimization engine to improve delivery routes.

Possible inputs:

* Rider location
* Restaurant location
* Customer location
* Current orders
* Estimated preparation time
* Delivery time window
* Traffic information

Future implementations can use:

* Vehicle Routing Problem algorithms
* Heuristics
* Reinforcement Learning
* Graph Neural Networks

The optimization engine should operate independently from the core order-processing service.

---

# 10. Security Architecture

```text
Customer
   │
   ▼
HTTPS / TLS
   │
   ▼
API Gateway
   │
   ▼
Authentication
   │
   ▼
Authorization
   │
   ▼
Microservices
   │
   ▼
Encrypted Database
```

## Security Controls

* HTTPS/TLS
* JWT/OAuth authentication
* Role-Based Access Control
* API rate limiting
* Input validation
* Secure payment integration
* Password hashing
* Encryption of sensitive information
* Audit logging

---

# 11. Fault Tolerance

The system should continue functioning when individual services fail.

```text
                Service Failure
                      │
                      ▼
                Health Check
                      │
                      ▼
              Failed Instance Removed
                      │
                      ▼
              Traffic Redirected
                      │
                      ▼
                Healthy Instance
```

The message queue provides additional resilience by buffering events until downstream services become available.

---

# 12. Real-Time Tracking Architecture

```text
Delivery Agent
      │
      ▼
Mobile GPS
      │
      ▼
Tracking API
      │
      ▼
Tracking Service
      │
      ├──────────────► Redis
      │
      ▼
WebSocket / Real-Time Gateway
      │
      ▼
Customer Application
```

This allows customers to receive near real-time delivery updates.

---

# 13. Cloud Deployment

```text
                         INTERNET
                            │
                            ▼
                  ┌──────────────────┐
                  │  Cloud Load       │
                  │    Balancer      │
                  └────────┬─────────┘
                           │
                           ▼
                    ┌──────────────┐
                    │ API Gateway  │
                    └──────┬───────┘
                           │
             ┌─────────────┼─────────────┐
             ▼             ▼             ▼
        Auth Pods     Order Pods    Restaurant Pods
             │             │             │
             └─────────────┼─────────────┘
                           ▼
                    Message Queue
                           │
             ┌─────────────┼─────────────┐
             ▼             ▼             ▼
        Delivery       Tracking      Notification
          Pods           Pods           Pods
             │             │
             └──────┬──────┘
                    ▼
               PostgreSQL
                    │
                    ▼
                  Redis
                    │
                    ▼
                 Backups
```

---

# 14. Non-Functional Requirements

## Scalability

The system should automatically scale services based on workload.

## Availability

Critical services should use multiple instances and health checks.

## Performance

Restaurant search, menu retrieval, and order operations should have low response times.

## Reliability

Orders and payment events should not be lost.

## Security

Customer, payment, restaurant, and delivery information must be protected.

## Maintainability

Services should be independently developed and deployed.

---

# 15. Future Enhancements

* AI-based restaurant recommendations
* Dynamic pricing
* Demand prediction
* Intelligent rider assignment
* Reinforcement-learning-based route optimization
* Smart food packaging sensors
* IoT-based food temperature monitoring
* Multi-region deployment
* Advanced fraud detection
* Predictive delivery-time estimation

---

# 16. Final Architecture Summary

```text
                    FOOD DELIVERY SYSTEM

                         Customer
                            │
                            ▼
                     Web / Mobile App
                            │
                            ▼
                      Load Balancer
                            │
                            ▼
                       API Gateway
                            │
        ┌───────────────────┼───────────────────┐
        ▼                   ▼                   ▼
      Auth              Restaurant             Order
     Service              Service             Service
                                                │
                                                ▼
                                          Payment Service
                                                │
                                                ▼
                                           Message Queue
                                                │
                              ┌─────────────────┼─────────────────┐
                              ▼                 ▼                 ▼
                         Restaurant         Delivery         Notification
                           Service           Service            Service
                                               │
                                               ▼
                                          Tracking
                                           Service
                                               │
                                               ▼
                                           PostgreSQL
                                               │
                                               ▼
                                             Redis
```

---

# 17. Conclusion

The proposed Food Delivery Ordering System uses a cloud-native, microservices-based, event-driven architecture.

The separation of order processing, payment, restaurant management, delivery, tracking, and notification services allows individual components to scale independently.

The architecture also provides a foundation for future optimization techniques such as AI-based demand prediction, intelligent rider assignment, and dynamic route optimization.
