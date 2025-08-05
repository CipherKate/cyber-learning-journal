# Certified in Cybersecurity – Domain 3: Access Control Concepts (ADHD-Friendly Guide)

---

### How to use this ADHD-friendly mini-course

* **Micro-lessons:** Each module fits on one screen—no scrolling marathon.  
* **Layered learning:** Read **Level 1** first (bold keywords only), then come back for **Level 2** (details & analogies).  
* **Active recall:** After each module, cover up the answers and quiz yourself out loud.  
* **Pomodoro breaks:** Work 25 minutes, break 5 minutes—stand, stretch, or squeeze a stress ball.  
* **Spaced repetition:** Review after 1 day, 2 days, and 1 week to lock in memory.  

---

## Module 1 – Core Access Control Concepts (the “who, what, when”)

| Level 1 keyword            | Level 2 explanation                                                                                     | Quick-quiz                                  |
|----------------------------|---------------------------------------------------------------------------------------------------------|---------------------------------------------|
| **Subject (Who)**          | The user, process, or device requesting access                                                           | What’s an example of a “subject”?           |
| **Object (What)**          | The resource being accessed (file, database, application)                                                | Give an example of an “object.”             |
| **Rule (How & When)**      | The policy or conditions that govern whether access is granted or denied                                 | What does a rule define?                   |
| **Defense in Depth**       | Layered security—multiple barriers (people, tech, processes) protect the same asset                      | Why is defense in depth stronger than one layer? |
| **Least Privilege**        | Grant only the permissions strictly needed—nothing extra                                                 | How does least privilege reduce risk?       |
| **Privileged Access Mgmt** | Temporary elevation of admin rights when needed, then revoke                                            | Why use privileged access management?       |
| **User Provisioning**      | Lifecycle: create, modify, disable, delete accounts as roles and staffing change                         | What step comes after “create”?             |

**Analogy:**  
Access control is like a VIP club—guests (subjects) get wristbands (rules) for specific areas (objects); bouncers and checkpoints (defense layers) enforce who goes where, and no one gets more privileges than necessary.

---

## Module 2 – Physical Access Controls (the “barriers”)

| Control category      | What it is                                                                            | Quick-quiz                                |
|-----------------------|---------------------------------------------------------------------------------------|-------------------------------------------|
| **Deterrents**        | Fences, lighting, signage, sealed windows to discourage intruders                     | Name one deterrent you’d use around a data center. |
| **Locks & Barriers**  | Mechanical locks, electronic door locks, cable locks, turnstiles                      | What’s the purpose of a turnstile?        |
| **Detection**         | CCTV cameras, motion sensors, glass-break alarms                                      | How does a motion detector alert you?     |
| **Guards & Dogs**     | Security personnel, guard dogs to patrol and respond                                 | What’s a key benefit of guard dogs?       |
| **Authentication**    | Badges, PIN pads, biometric scanners, mantraps                                        | Explain how a mantrap works.              |
| **Environmental Design** | Crime Prevention Through Environmental Design (CPTED)—architectural layout reduces opportunities | Give one CPTED tactic.                |
| **Audit & Monitoring**| Record gate logs, review access records, spot anomalies                              | Why is auditing physical access important?|

**Analogy:**  
Securing a building is like protecting a medieval fortress—moat (deterrents), drawbridge (locks), watchtowers (cameras), guards (security staff), secret sally ports (mantraps).

---

## Module 3 – Logical Access Controls (the “permissions”)

| Access model           | How it works                                                                                    | Quick-quiz                               |
|------------------------|------------------------------------------------------------------------------------------------|------------------------------------------|
| **DAC (Discretionary)**| Resource owner sets permissions (file ACLs, share rights)                                      | Who controls DAC permissions?            |
| **MAC (Mandatory)**    | System enforces policies based on labels (classification + clearance)                          | How does MAC differ from DAC?            |
| **RBAC (Role-Based)**  | Permissions tied to job roles; users inherit rights by role                                    | Give an example of a role in RBAC.       |
| **Logical Access Systems** | Software systems (IAM, directory services) that enforce user authentication & authorization | What’s one component of a logical ACS?   |
| **Config vs Hardware** | GUI settings vs. hardware jumpers or console commands                                           | Name one hardware-based control.         |
| **User Provisioning**  | Automated workflows for onboarding, changes, and offboarding                                   | What’s the last step in provisioning?    |

**Mnemonic:**  
**D M R** – Discretionary • Mandatory • Role-based

**Analogy:**  
Permissions are like backstage passes—DAC is a pass you give personally; MAC is a centrally issued secured credential; RBAC is a pass based on your job title.

---

## Rapid-fire memory hooks

* **SOR** → Subject • Object • Rule  
* **D M R** → Discretionary • Mandatory • Role-based  
* **PAM** → Privileged Access Management  
* **CPTED** → Design spaces to discourage crime  
* **Provisioning life-cycle** → Create → Modify → Disable → Delete  

---

## “Make it stick” study strategies

1. **Flashcards:** Write Level 1 keywords on one side, Level 2 on the back.  
2. **Teach-back:** Explain each module to a friend or even a rubber duck.  
3. **Scenario drills:** Sketch out controls for a bank vault vs. a SaaS platform.  
4. **Mind-maps:** Draw Subject → Rule → Object flows.  
5. **Pomodoro:** 25 min focus, 5 min break—use that time to walk or fidget.  
6. **Spaced review:** Revisit quizzes after 1, 2, and 7 days.  
7. **Positive reinforcements:** Reward yourself for completing modules (snack break, quick walk).

---
