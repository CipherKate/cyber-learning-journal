# Certified in Cybersecurity – Domain 3: Access Control Concepts (ADHD-Friendly Guide)

---

### How to use this ADHD-friendly mini-course

* **Micro-lessons:** One screen per concept—no overwhelm.  
* **Layered learning:** Skim **Level 1** (keywords) first, then dive into **Level 2** (details + analogies).  
* **Active recall:** After each section, cover up the answers and quiz yourself out loud.  
* **Pomodoro breaks:** 25 min study, 5 min break—stand, stretch, or fidget.  
* **Spaced repetition:** Review after 1 day, 2 days, and 1 week to cement memory.  

---

## Module 1 – Core Access Control Concepts (the “who, what, when”)

| Level 1 keyword            | Level 2 explanation                                                             |
|----------------------------|----------------------------------------------------------------------------------|
| **Subject (Who)**          | The user, process, or device requesting access                                   |
| **Object (What)**          | The resource being accessed (file, database, application)                        |
| **Rule (How & When)**      | The policy or conditions that govern whether access is granted                   |
| **Defense in Depth**       | Layered security—multiple barriers across people, tech, and processes             |
| **Least Privilege**        | Grant only the permissions strictly needed                                       |
| **Privileged Access Mgmt** | Temporary elevation of admin rights when needed, then automatic revoke           |
| **Provisioning**           | Create → Modify → Disable → Delete accounts as roles and staffing change         |

**Analogy:**  
Access control is like a VIP club—guests (subjects) get wristbands (rules) for specific rooms (objects), with bouncers (defense layers) enforcing “no extra privileges.”

**Quick quiz:**
1. Who or what is a “subject” in access control?  
2. What’s the main goal of “least privilege”?

<details><summary>Answer key</summary>
1. The user, process, or device requesting access.  
2. To reduce risk by giving users only the rights they absolutely need.
</details>

---

## Module 2 – Physical Access Controls (the “barriers”)

| Control category       | Examples                                           |
|------------------------|----------------------------------------------------|
| **Deterrents**         | Fences, lighting, signage                          |
| **Locks & Barriers**   | Mechanical locks, electronic door locks, turnstiles|
| **Detection**          | CCTV cameras, motion sensors, alarms               |
| **Guards & Dogs**      | Security personnel, guard dogs                     |
| **Authentication**     | Badges, PIN pads, biometric scanners, mantraps     |
| **Environmental Design**| CPTED layouts (clear sightlines, natural surveillance) |
| **Audit & Monitoring** | Log books, access logs, regular inspections        |

**Analogy:**  
Think of a data center as a medieval castle—moat (deterrents), drawbridge (locks), watchtowers (cameras), guards (security staff), and secret sally ports (mantraps).

**Quick quiz:**
1. What’s the purpose of a mantrap?  
2. Name one CPTED tactic for physical security.

<details><summary>Answer key</summary>
1. To enforce two-stage entry: you must pass one door before the other unlocks, preventing tailgating.  
2. Designing landscaping so that bushes don’t block sightlines, allowing natural surveillance.
</details>

---

## Module 3 – Logical Access Controls (the “permissions”)

| Access model            | Description                                                  |
|-------------------------|--------------------------------------------------------------|
| **DAC (Discretionary)** | Owner sets permissions (file ACLs)                           |
| **MAC (Mandatory)**     | System enforces policies based on labels/classifications     |
| **RBAC (Role-Based)**   | Permissions tied to job roles, users inherit by role         |
| **ABAC (Attribute-Based)** | Decisions based on user, resource, environment attributes |
| **IAM Systems**         | Software (e.g., directory services) enforcing authn/authz    |
| **Config vs Hardware**  | GUI settings vs. hardware switches/jumpers                   |

**Mnemonic:** **D M R A** (Discretionary • Mandatory • Role • Attribute)

**Quick quiz:**
1. What differentiates MAC from DAC?  
2. Give one example of ABAC.

<details><summary>Answer key</summary>
1. MAC is centrally enforced by the system (no owner override), while DAC lets resource owners set permissions.  
2. An ABAC rule might allow “Engineering” staff access only between 8 am–6 pm on “Engineering” servers.
</details>

---

## Rapid-fire memory hooks

* **SOR** → Subject • Object • Rule  
* **D M R A** → Discretionary • Mandatory • Role-Based • Attribute-Based  
* **PAM** → Privileged Access Management (temporary admin rights)  
* **CPTED** → Environmental design to discourage intruders  
* **Provisioning cycle** → Create → Modify → Disable → Delete  

---

## Make it stick

1. **Flashcards:** Level 1 keywords on one side, Level 2 on the back.  
2. **Teach-back:** Explain each module to a peer or your favorite plush toy.  
3. **Scenario drills:** Sketch controls for a vault vs. a SaaS app.  
4. **Mind-maps:** Draw flows: Subject → Rule → Object.  
5. **Pomodoro:** 25 min focus, 5 min break—walk or fidget.  
6. **Spaced review:** Redo quizzes after 1, 2, and 7 days.  
7. **Rewards:** Treat yourself after each module (snack, short walk).
