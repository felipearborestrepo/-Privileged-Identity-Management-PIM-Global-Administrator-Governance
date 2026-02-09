# 🔐 Privileged Identity Management (PIM) — Global Administrator Governance

<img width="1536" height="1024" alt="ChatGPT Image Feb 8, 2026 at 10_59_33 PM" src="https://github.com/user-attachments/assets/113f32a4-941a-4fc5-b3b3-d58b6b581f29" />

## 📘 Project Overview

This project documents the implementation and validation of **Privileged Identity Management (PIM)** for highly privileged roles in **Microsoft Entra ID**.

The objective was to demonstrate how **standing administrative access** can be identified, reviewed, and removed to align with **least privilege** and **Zero Trust** principles.

The project focuses on governing **Global Administrator** access by validating role assignment activity and ensuring privileged access does not persist without justification.

---

## 🎯 Objectives

- Validate how Global Administrator roles are assigned and removed
- Demonstrate visibility into privileged role changes
- Enforce least privilege by removing standing admin access
- Capture audit evidence for privileged role activity
- Align with enterprise IAM and PAM best practices

---

## 🏗️ Environment

- Microsoft Entra ID tenant
- Privileged Identity Management (PIM)
- Test user:
  - `Felipe-PIM`
- Privileged role:
  - Global Administrator

---

## 🧩 Privileged Access Scenario

A dedicated test identity (`Felipe-PIM`) was created to simulate an administrative user receiving elevated privileges.

This allowed for controlled testing of:
- Privileged role assignment
- Privileged role removal
- Audit logging of sensitive role changes

This approach mirrors how IAM teams validate and monitor administrative access in production environments.

![Image 2-8-26 at 22 31](https://github.com/user-attachments/assets/faeb86d3-2500-4f55-991b-aea67c58d118)

---

## 🔍 Privileged Role Assignment

The `Felipe-PIM` user was assigned the **Global Administrator** role to simulate elevated access.

This step represents a scenario where administrative privileges are granted, either temporarily or permanently, and must be governed to prevent excessive access.
![Image 2-8-26 at 22 33](https://github.com/user-attachments/assets/e5ec7f33-d199-4b9e-846c-cdd6f8245a7b)

![Image 2-8-26 at 22 34](https://github.com/user-attachments/assets/bd59a99a-52be-40f5-a037-c93afb225a73)

![Image 2-8-26 at 22 35](https://github.com/user-attachments/assets/a6ef784b-78f4-403f-9af2-1b740f912339)

![Image 2-8-26 at 22 35](https://github.com/user-attachments/assets/1a45a9c8-1781-4628-842e-b2b2545d11ed)

![Image 2-8-26 at 22 37](https://github.com/user-attachments/assets/7223f996-2eb9-4b3a-81ed-bbf755a0ab8f)

![Image 2-8-26 at 22 38](https://github.com/user-attachments/assets/e0278da7-edb4-4d24-ba1f-131cc908df6a)

![Image 2-8-26 at 22 40](https://github.com/user-attachments/assets/ff5fe71a-3084-437f-b237-5218f9deccd4)

![Image 2-8-26 at 22 41](https://github.com/user-attachments/assets/ca96f330-6f80-4b18-911b-7e3b39d14b19)

---
## ⚙️ Privileged Role Configuration (PIM Role Settings)

The **Global Administrator role settings** were reviewed and updated to enforce stronger controls during privileged access usage.

### 🔐 Activation Controls
The following activation requirements were configured:
- **Maximum activation duration:** 1 hour
- **Multi-Factor Authentication (MFA) required on activation**
- **Justification required on activation**
- Approval requirement disabled for streamlined but auditable elevation

These controls ensure that privileged access is:
- Time-bound
- Authenticated with MFA
- Explicitly justified at activation time

![Image 2-8-26 at 22 43](https://github.com/user-attachments/assets/ce3f5976-7326-4d88-8451-d24d51aa2f87)

---

### 🧾 Assignment Controls
The following assignment rules were enforced:
- Eligible assignments allowed with expiration
- Active assignments configured with expiration limits
- **MFA required for active assignments**
- **Justification required for active role assignments**

These settings prevent unmanaged standing admin access and enforce accountability for role usage.

![Image 2-8-26 at 22 43](https://github.com/user-attachments/assets/417b15ce-8e63-4235-81dd-375c26b87bd4)

---
## 🛑 Privileged Role Removal (Least Privilege Enforcement)

After validation, the Global Administrator role assignment was **removed** from the `Felipe-PIM` user.

This demonstrates:
- Identification of unnecessary standing admin access
- Enforcement of least privilege
- Reduction of attack surface associated with persistent administrative roles

Removing standing access is a foundational principle of Privileged Identity Management.

![Image 2-8-26 at 22 46](https://github.com/user-attachments/assets/2e3f83c1-e51c-49e2-9459-56ade0959cc1)

---

## 📊 Audit & Governance Evidence

Audit logs were reviewed to validate the full lifecycle of the privileged role change.

Captured evidence includes:
- Global Administrator role assignment event
- Global Administrator role removal event
- Timestamped audit records associated with the `Felipe-PIM` user

This confirms that privileged role activity is:
- Fully logged
- Traceable
- Reviewable for compliance and security investigations

![Image 2-8-26 at 23 04](https://github.com/user-attachments/assets/c4ef16af-c6ca-470f-b4d1-28a0d2e78ec5)

---

## 🧠 Key Takeaways

- Standing Global Administrator access represents significant risk
- Privileged role assignments must be reviewed and governed
- Audit logs provide critical visibility into admin role changes
- Removing unnecessary admin access directly supports Zero Trust
- PIM is essential for reducing identity-based attack paths

---

## 🏁 Conclusion

This project demonstrates a foundational **Privileged Identity Management** workflow by validating and removing highly privileged access.

By reviewing and eliminating standing Global Administrator roles, organizations can significantly reduce risk while maintaining full audit visibility.

This lab reflects real-world IAM practices used to secure administrative access in enterprise environments.
