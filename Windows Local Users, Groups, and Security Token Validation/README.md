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
![Step 1 – Users](users_created.png)


---

##  Step 2 – Created Groups
Created three groups:

- **GroupA** (contains User1 and User2)  
- GroupB (contains User3 and User4)  
- GroupC (simulated nested group; may include GroupA)  

### 📷 Screenshot: Groups
![Step 2 – Groups](groups_created.png)



---

##  Step 3 – Assigned Users to Groups
- **GroupA → User1, User2**  
- **GroupB → User3, User4**  
- **GroupC → Simulated nested membership** (e.g., contains GroupA)

###  Screenshot: Group Memberships
![Groups](GroupA_memmbers.png)
![Groups ](GroupB_members.png)
![Groups ](GroupC_members.png)



---

##  Step 4 – Verification of Effective Access (User1)
**Purpose:** Step 4 verifies **what groups User1 effectively belongs to** and therefore **what permissions they have**. This includes **direct membership** (GroupA) and **indirect/nested membership** (GroupC).  

**Command used:**
whoami /groups

### Screenshot: Whoami
![Whoami ](whoami_groups.png)



##  IAM Relevance
- Permissions are assigned to **groups, not individual users**, which improves scalability.  
- **RBAC (Role-Based Access Control)** ensures that changing group permissions automatically affects all members.  
- **Nested groups** allow **indirect permission inheritance** (e.g., User1 inherits GroupC permissions via GroupA).  
- Security tokens determine the **actual privileges** a user has at login.  
- Step 4 demonstrates how **effective permissions** are calculated based on group membership.

---

##  Key Learnings
- Groups simplify access management and reduce **manual permission errors**.  
- RBAC improves **security management** by centralizing permission control.  
- Group membership, including **nested groups**, impacts a user’s effective privileges.  
- Verifying effective access for User1 helps understand **how permissions propagate** in Windows.  
- Step 4 is essential to confirm that **users have the expected access** based on group assignments.





