#  Identity and Access Management (IAM) Lab – BlackTECH Academy

This repository documents hands-on IAM tasks completed as part of the BlackTECH Cybersecurity Academy.  
Tasks include Microsoft Entra PIM, MFA enforcement, SAML integration, and IAM auditing.

---

##  Lab Objective

To strengthen identity and access controls through:
- Just-in-Time (JIT) privilege elevation
- Role-based access control (RBAC)
- Secure authentication practices
- Auditing and monitoring access

---

##  Tasks

- [x] Task 1: Enable Privileged Identity Management (PIM)
- [ ] Task 2: Configure PIM Role Activation & Approval Flow
- [ ] Task 3: Integrate Enterprise App with Entra ID via SAML
- [ ] Task 4: Automate Access Reviews in PIM
- [ ] Task 5: Audit and Monitor IAM Activities in Entra ID
- [ ] Task 6: Setup Bitwarden Password Collection
- [ ] Task 7: Enforce MFA for Bitwarden Access

---

##  Task 1: Enable Privileged Identity Management (PIM)

###  Objective
Enable Just-in-Time (JIT) elevation using Microsoft Entra Privileged Identity Management (PIM) for:
- Exchange Administrator
- Teams Administrator
- Security Administrator

This minimizes standing admin privileges and reduces risk of privilege abuse.

###  Steps Taken
1. Logged in to [Microsoft Entra Admin Center](https://entra.microsoft.com)
2. Navigated to **Privileged Identity Management > Microsoft Entra roles**
3. Enabled PIM for selected roles
4. Assigned user as **Eligible** (not Active) with **Permanent** assignment

###  Key Concepts
- **JIT Access** – Grant roles only when needed
- **Eligible** – Requires user to request access
- **PIM** – Provides access control, auditability, and time limits

###  Screenshot  
![PIM Role Enabled] <img width="1366" height="711" alt="2025-07-24 (3)" src="https://github.com/user-attachments/assets/4348ea2a-d6aa-4db5-9eb9-e4443a8f7683" />

---

Stay tuned as I complete and document the rest of the tasks! 
