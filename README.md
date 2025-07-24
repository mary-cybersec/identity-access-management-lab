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
- [x] Task 2: Configure PIM Role Activation & Approval Flow
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
---

##  Task 2: Configure PIM Role Activation & Approval Flow

###  Objective

Strengthen access control by requiring **approval**, **MFA**, and **justification** before activating privileged roles (JIT model).

---

###  Steps Taken

1. Navigated to each role in:

   * `Microsoft Entra Admin Center > Privileged Identity Management > Microsoft Entra roles`

2. Selected roles:

   * Exchange Administrator
   * Teams Administrator
   * Security Administrator

3. Opened **Role Settings** and applied the following configuration:

   *  **MFA required to activate**
   *  **Justification required**
   *  **Approval required**

     * Chose a test user/admin as approver
   *  **Activation duration set to 1 hour**

4. Saved the settings for each role

---

###  Key Concepts

* **Approval workflow** ensures that elevated access isn't automatic.
* **MFA & justification** add layered verification and traceability.
* **Time-bound access** limits security exposure during elevation.

---

###  Screenshot 
![Role Activation Settings]
<img width="1366" height="711" alt="2025-07-24 (16)" src="https://github.com/user-attachments/assets/04fc8433-9766-4984-8ee5-e0592612dabf" />


---
##  Task 3: Integrate Salesforce App with Entra ID via SAML

###  Objective
Enable Single Sign-On (SSO) for **Salesforce** using the **SAML 2.0** protocol with Microsoft Entra ID as the Identity Provider (IdP).

---

###  Steps Taken

1. Navigated to:
   `Microsoft Entra Admin Center > Enterprise Applications`

2. Clicked **“+ New Application”**, then searched and selected:
   -  **Salesforce**

3. After app creation, selected:
   - **Single sign-on > SAML**

4. On the SAML configuration page:
   - Reviewed & confirmed the following:
     - **Identifier (Entity ID):**  
       `https://saml.salesforce.com`
     - **Reply URL (ACS):**  
       `https://<your-domain>.my.salesforce.com`

5. Downloaded the **Federation Metadata XML**
6. Assigned a test user under **Users and Groups**
7. (Optional) Sent metadata to Salesforce admin for import on their end

---

### Key Concepts

- **SAML 2.0** provides federated login between Entra ID and Salesforce.
- Microsoft Entra ID acts as the **Identity Provider (IdP)**.
- Salesforce is the **Service Provider (SP)**.
- **SSO** improves both security and user experience.

---

### Screenshot
![Salesforce SAML Setup]
<img width="1366" height="711" alt="2025-07-24 (23)" src="https://github.com/user-attachments/assets/2a89951c-0ec1-4dad-8fc8-2a43412f15ee" />

---

 Salesforce is now integrated with Microsoft Entra for SAML SSO. Further testing and claim customization can be done as needed.



Stay tuned as I complete and document the rest of the tasks! 
