# Active Directory Lab: Restricting Registry Editor with GPO

## Objective
Create an Organizational Unit (OU) and apply a Group Policy Object (GPO) to restrict access to Registry Editor (regedit) for a test user.

## Steps Completed

### 1. Created an Organizational Unit
- Opened **Active Directory Users and Computers**
- Created a new **Homelab OU** for testing purposes
- This OU is used to organize objects and apply Group Policy

### 2. Moved user into the OU
- Took the test User1 from the default **Users** container
- Moved the user into the newly created OU
- Confirmed that the user is now located inside the OU

### 3. Created a new Group Policy Object
- Opened **Group Policy Management**
- Created a new GPO named **Regedit Restriction**

### 4. Linked the GPO to the OU
- Linked the **Regedit Restriction** GPO to the created **Homelab OU**
- This ensures the policy applies to all users inside that OU

### 5. Configured the policy
- Edited the **Regedit Restriction** GPO
- Navigated to:

  `User Configuration > Policies > Administrative Templates > System`

- Enabled the setting:

  **Prevent access to registry editing tools**

### 6. Applied and tested the policy

- Logged in as the test user and attempted to open `regedit`

## Notes
- Learned that **GPOs are applied through OU**, not directly through groups
- The default **Users** container is not suitable for GPOs targeting
- Creating фт OU is required to ptoperly link and manage GPOs
- Moving users into an OU is required for proper GPOs management

## Result
Successfully created an OU, linked a GPO, and configured a policy intended to restrict access to Registry Editor for users within that OU.
