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
- [x] Task 3: Integrate Enterprise App with Entra ID via SAML
- [x] Task 4: Automate Access Reviews in PIM
- [x] Task 5: Audit and Monitor IAM Activities in Entra ID
- [x] Task 6: Setup Bitwarden Password Collection
- [x] Task 7: Enforce MFA for Bitwarden Access

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

 ---
 ## Task 4: Automate Access Reviews in PIM

### Objective
Create recurring access reviews in Microsoft Entra PIM for privileged roles to enforce the principle of least privilege and maintain compliance.

---

### Steps Taken

1. Navigated to:
   `Microsoft Entra Admin Center > Identity Governance > Access Reviews`

2. Clicked **“+ New access review”**

3. Configured the following:
   - **Review name:**  
     `PIM Access Review – Exchange & Teams Admin`
   - **Start date:** Today  
   - **Recurrence:** Monthly
   - **Scope:**  
     - Directory roles → Exchange Administrator  
     - Directory roles → Teams Administrator
   - **Reviewers:** Self-review (admin)
   - **Auto apply results:** ✅ Yes
   - **Action for users not reviewed:** Remove access
   - **Notifications:** ✅ Enabled

4. Saved and launched the review cycle

---

### Key Concepts

- **Access Reviews** automate revalidation of role assignments
- Enforces **just-in-time access** and **least privilege**
- Helps meet security & compliance standards by reducing dormant or stale assignments

---

### Screenshot
![Access Review Setup]
<img width="1366" height="706" alt="2025-07-24 (24)" src="https://github.com/user-attachments/assets/c3854d07-3e09-4892-9013-1c529a20f8e5" />


---


Monthly access reviews are now live and enforcing privileged access hygiene.

---
### 🔎 Task 5: Audit and Monitor IAM Activities in Entra ID

**Objective**  
To monitor and audit Identity and Access Management (IAM) activities in Microsoft Entra ID by tracking sign-ins, role changes, and other critical user actions. This strengthens visibility and supports proactive threat detection.

**Steps Performed**  
1. **Accessed Microsoft Entra Admin Center**  
   - Logged into [https://entra.microsoft.com](https://entra.microsoft.com) with administrator credentials.

2. **Monitored Key IAM Logs**  
   - Navigated to **Monitoring > Audit Logs** to track admin actions like role assignments and group changes.  
   - Reviewed **Sign-in Logs** for authentication events including successful and failed login attempts.

3. **Applied Filters to Identify Key Events**  
   - Filtered logs by time range, user, and activity types (e.g., MFA updates, role changes, login failures).  
   - Focused on activities related to privileged accounts and sign-ins from unfamiliar locations.

4. **Exported and Analyzed Logs**  
   - Exported logs to CSV format for external review.  
   - Used spreadsheet filters to detect anomalies and prepare audit summaries.

5. **Documented Findings**  
   - Noted any unusual access patterns or critical configuration changes.  
   - Screenshots and findings were saved as part of the project documentation.

**Outcome**  
Successfully established a clear audit trail for IAM events in Entra ID. This task provided critical visibility into access patterns and administrative changes, supporting ongoing compliance and incident response readiness.

---

###  Task 6: Set Up Bitwarden Password Collection

**Objective**  
To establish a secure and centralized password management system for the SOC lab team using Bitwarden. This ensures shared credentials are protected, easily accessible, and properly managed.

**Steps Performed**  
1. **Signed into Bitwarden Web Vault**  
   - Logged in via [https://vault.bitwarden.com](https://vault.bitwarden.com) using admin credentials.

2. **Created a New Organization**  
   - Navigated to the **Organizations** tab.  
   - Created a new organization named `SOC Lab Vault`.  
   - Selected the appropriate plan (Free plan used for lab purposes).

3. **Created a Password Collection**  
   - Inside the organization, accessed the **Collections** section.  
   - Created a new collection named `SOC Shared Credentials`.  
   - Assigned user access and permissions to the collection.

4. **Added Login Items to the Collection**  
   - Created a new login item for a service (e.g., Azure Admin Portal).  
   - Entered service name, username, password, and URL.  
   - Linked the item to the newly created collection.  
   - Saved the item securely within the vault.

5. **Enabled Bitwarden Browser Extension**  
   - Installed the Bitwarden extension in the browser.  
   - Logged in and tested **Auto-fill** functionality for saved logins.

6. **Invited Team Member (Optional)**  
   - Sent an invitation to another SOC lab participant to join the organization.  
   - Granted them access to specific collections for shared use.

**Outcome**  
Secure password sharing was successfully implemented through Bitwarden. This setup enables the SOC team to manage credentials collaboratively without compromising on security or accessibility.

---
###  Task 7: Enforce MFA for Bitwarden Access

**Objective**  
To enforce two-factor authentication (2FA) for all users accessing Bitwarden, ensuring enhanced protection of shared credentials.

**Steps Performed**  
1. **Navigated to Bitwarden Web Vault**  
   - Logged in to [https://vault.bitwarden.com](https://vault.bitwarden.com)

2. **Enabled Two-Step Login (2FA)**  
   - Went to **Settings > Security > Two-step Login**  
   - Selected **Authenticator App** and scanned the QR code using Google Authenticator.  
   - Entered the 6-digit code to verify and enable 2FA.

3. **Verified Admin Enforcement**  
   - Tested login with 2FA enabled to confirm enforcement.  
   - Ensured Bitwarden requires MFA for access going forward.

**Outcome**  
Bitwarden access is now protected with MFA, ensuring that even if credentials are compromised, unauthorized access is prevented.

<img width="1366" height="711" alt="2025-07-24 (33)" src="https://github.com/user-attachments/assets/d093b905-fe6f-489a-8da2-0761e4073b73" />


