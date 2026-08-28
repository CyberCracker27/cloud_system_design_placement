# Cloud System Design 

**Author:** Gopikrishnan S  
**Course:** B.E CSE(Cybersecurity)  
**Institution:** Dr.N.G.P Intitute of Technology  

## Overview

This repository documents my 12-week journey of designing and planning two **high system design, cloud-deployable projects**:

1. **Cloud-Based Expense Tracking & Analytics System**  
2. **Online Quiz / Exam Management System**

Each week, I will update this repository with progress, documents, and artifacts (problem statements, literature survey, architecture diagrams, etc.).

---

## Project Timeline & Weekly Goals

### Week 9: Problem Identification & Use Cases

**Goal:** Define 5 problem use cases across both projects.

- [ ] Expense Tracker – Use Case 1: User registration & authentication  
- [ ] Expense Tracker – Use Case 2: Add income/expense transaction  
- [ ] Expense Tracker – Use Case 3: View dashboard & analytics  
- [ ] Exam System – Use Case 1: Instructor creates exam with question bank  
- [ ] Exam System – Use Case 2: Student attempts timed exam  

**Deliverable:** [`docs/week-09-problem-use-cases.md`](docs/week-09-problem-use-cases.md)

---

### Week 10: Problem Shortlisting (2 Final Problems)

**Goal:** From the 5 use cases, finalize 2 core problems (one per project) to focus on.

- [ ] Select primary use case for Expense Tracker  
- [ ] Select primary use case for Exam System  
- [ ] Document rationale for selection  

**Deliverable:** [`docs/week-10-problem-shortlist.md`](docs/week-10-problem-shortlist.md)

---

### Week 11: Literature Survey

**Goal:** Conduct literature survey for the 2 selected problems using IEEE papers and other research.

- [ ] Expense Tracker – Literature survey (IEEE base paper + 2–3 additional references)  
- [ ] Exam System – Literature survey (IEEE base paper + 2–3 additional references)  
- [ ] Summarize key findings, gaps, and how my solution extends existing work  

**Deliverable:** [`docs/week-11-literature-survey.md`](docs/week-11-literature-survey.md)

---

### Week 12: High-Level Architecture (HLD)

**Goal:** Design high-level architecture for both projects.

- [ ] Expense Tracker – HLD diagram + component descriptions  
- [ ] Exam System – HLD diagram + component descriptions  
- [ ] Document cloud services, data flow, and scalability considerations  

**Deliverable:** [`docs/week-12-hld-architecture.md`](docs/week-12-hld-architecture.md)

---

## Project Details

### Project 1: Cloud-Based Expense Tracking & Analytics System

**IEEE Base Paper:**  
- "Expense Management System" – IEEE Conference Publication  
- Link: https://ieeexplore.ieee.org/abstract/document/10353348

**Objective:**  
Build a cloud-native expense tracking system with dashboards, analytics, and AI-driven predictions.

**Key Features (Planned):**
- User authentication & authorization  
- Transaction CRUD (income/expense)  
- Categorization & receipt uploads  
- Dashboard with trends, budgets, and anomaly detection  
- ML-based monthly predictions  

**Status:** 🟡 In Progress

---

### Project 2: Online Quiz / Exam Management System

**IEEE Base Paper:**  
- "Online Examination System with Measures for Prevention of Cheating along with Rapid Assessment and Automatic Grading" – IEEE Conference  
- Link: https://ieeexplore.ieee.org/document/10039552

**Objective:**  
Build a secure, scalable online exam platform with auto-grading and analytics.

**Key Features (Planned):**
- Instructor exam creation & question bank  
- Student exam attempts with timer & auto-save  
- Auto-grading (MCQs, code, descriptive via NLP)  
- Analytics dashboards for performance tracking  
- Anti-cheating measures (tab-switch detection, randomized questions)  

**Status:** 🟡 In Progress

---

## Weekly Progress Log

| Week | Focus Area | Status | Deliverable |
|------|------------|--------|-------------|
| 9 | Problem Identification & Use Cases | 🟡 In Progress | [`docs/week-09-problem-use-cases.md`](docs/week-09-problem-use-cases.md) |
| 10 | Problem Shortlisting (2 Final Problems) | ⚪ Not Started | [`docs/week-10-problem-shortlist.md`](docs/week-10-problem-shortlist.md) |
| 11 | Literature Survey | ⚪ Not Started | [`docs/week-11-literature-survey.md`](docs/week-11-literature-survey.md) |
| 12 | High-Level Architecture (HLD) | ⚪ Not Started | [`docs/week-12-hld-architecture.md`](docs/week-12-hld-architecture.md) |

🟢 Completed | 🟡 In Progress | ⚪ Not Started

---

## How to Use This Repository

1. **Clone the repo:**
   ```bash
   git clone https://github.com/[your-username]/cloud-system-design-portfolio.git
   cd cloud-system-design-portfolio
   ```

2. **Check weekly progress:**  
   Navigate to the `docs/` folder and open the relevant week's document.

3. **Contribute / Feedback:**  
   Feel free to open issues or pull requests for suggestions, improvements, or collaborations.

---

## Tools & Technologies (Planned)

- **Frontend:** React.js / Next.js  
- **Backend:** Node.js / Python (FastAPI) / Java (Spring Boot)  
- **Cloud:** AWS / Azure / GCP  
- **Database:** PostgreSQL / MongoDB  
- **DevOps:** Docker, Kubernetes, GitHub Actions, Terraform  
- **Diagrams:** Draw.io, Excalidraw, Lucidchart  

---

## References

1. IEEE, "Expense Management System," IEEE Conference Publication. [Online]. Available: https://ieeexplore.ieee.org/abstract/document/10353348  
2. IEEE, "Online Examination System with Measures for Prevention of Cheating along with Rapid Assessment and Automatic Grading," IEEE Conference. [Online]. Available: https://ieeexplore.ieee.org/document/10039552  

---

**Last Updated:** [Date]
