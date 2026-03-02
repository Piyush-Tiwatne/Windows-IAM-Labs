#  Lab 1 – Windows Local Users, Groups, and Security Token Validation

##  Objective
To understand Windows local user management, group membership, and role-based access control (RBAC), and to verify effective permissions for **User1**.

---

##  Environment
- OS: Windows 10/11 Pro  
- Tool: lusrmgr.msc  
- Machine Type: Standalone (Non-Domain)  

> **Note:** This lab focuses on local users and groups, not domain accounts.

---

##  Concepts Covered
- Local Users & Groups  
- Security Identifiers (SID)  
- Role-Based Access Control (RBAC)  
- Group Membership  
- Security Tokens  

---

##  Step 1 – Created Users
Created four local users:

- **User1** (Primary user for access verification)  
- User2  
- User3  
- User4  

###  Screenshot: Users
*(Add screenshot from `lusrmgr.msc` here)*

---

##  Step 2 – Created Groups
Created three groups:

- **GroupA** (contains User1 and User2)  
- GroupB (contains User3 and User4)  
- GroupC (simulated nested group; may include GroupA)  

### 📷 Screenshot: Groups
*(Add screenshot from `lusrmgr.msc` here)*

---

##  Step 3 – Assigned Users to Groups
- **GroupA → User1, User2**  
- **GroupB → User3, User4**  
- **GroupC → Simulated nested membership** (e.g., contains GroupA)

###  Screenshot: Group Memberships
*(Add screenshot showing users added to groups here)*

---

## 🧪 Step 4 – Verification of Effective Access (User1)
**Purpose:** Step 4 verifies **what groups User1 effectively belongs to** and therefore **what permissions they have**. This includes **direct membership** (GroupA) and **indirect/nested membership** (GroupC).  

**Command used:**

```cmd
whoami /groups
### Screenshot:
