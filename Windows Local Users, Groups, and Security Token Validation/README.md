Lab 1: Identity Provisioning and Group-Based Access Control (GBAC)
# Executive Summary
In this project, I performed the foundational tasks of an IAM Administrator by provisioning local identities and organizing them into a scalable group hierarchy. The lab concludes with a technical verification of a user's Security Access Token to ensure that group memberships are correctly inherited and recognized by the OS.

# Step-by-Step Implementation
Phase 1: Identity Provisioning
I created four unique local user accounts. In an enterprise setting, this represents the "Joiner" process where new identities are added to the system's identity store (SAM database).

Action: Created User1, User2, User3, and User4 via lusrmgr.msc.

Technical Note: Each account is assigned a unique Security Identifier (SID).

Evidence: 


Phase 2: Logical Grouping (Resource Management)
To manage permissions efficiently, I created three administrative groups. Managing access via groups (RBAC) is an industry best practice as it prevents "Permission Creep" and simplifies audits.

Groups Created: GroupA, GroupB, GroupC.

Assignment: Added User1 & User2 to GroupA; added User3 & User4 to GroupB.

Evidence: 


Phase 3: Simulated Nested Grouping
To demonstrate the concept of Transitive Membership, I simulated a nested group structure. I added the members of the departmental groups into GroupC (The "Parent" or "Master" group).

Logic: If GroupC is granted access to a folder, all members of GroupA and GroupB should theoretically inherit those rights.

Evidence: 

Phase 4: Security Token Audit (Technical Verification)
The final and most critical step was verifying the Access Token. I logged in as User1 to trigger a new authentication session and used the CLI to inspect the active security context.

Command: whoami /groups

Result: The system successfully listed GroupA and GroupC as active SIDs in User1’s token.

Evidence: 

 Key IAM Takeaways
Token Refresh: I observed that group membership changes require a fresh login session to update the user's security token.

Scalability: Assigning permissions to groups rather than individuals is the only way to manage large-scale corporate environments.

Auditability: Using whoami provides a clear audit trail of what a user's "Effective Permissions" actually are.
