# Identity & Access — Week 1 Notes

## What I Learned
- Entra ID is Microsoft's cloud-based identity and access management service
- It handles authentication (who are you?) and authorisation (what can you do?)
- Entra ID is NOT the same as on-premise Active Directory


## What I Built
- Created a fictional company: Meridian Tech
- Created 3 users: Alex Turner (IT), Priya Patel (IT), Jamie Brooks (HR)
- Created 2 Security groups: IT-Team, HR-Team
- I wasn't sure about UPN vs Display Name at first but figured it out during creation. 
  I also noticed Azure auto-generates a temporary password for new users — 
  in a real environment you'd share this securely with the new starter.


## Key Terms
| Term | What it means |
|---|---|
| Tenant | Your organisation's dedicated instance of Entra ID |
| UPN | The username used to sign in — follows email format |
| Display Name | The name people see in the directory |
| Security Group | Used to control access to resources |

#### Questions I Still Have
- What if I want to add 100s of users at the same time and add them to the group as well? Do I have to do it manually?

## RBAC — Role Based Access Control

### What I Learned
- RBAC controls who can do what in Azure
- Three key concepts: Role (what's allowed), Scope (where it applies), 
  Security Principal (who gets it)
- Always assign roles to groups not individuals — easier to manage
- Least privilege = give users only the access they need for their job

### What I Built
- Assigned Contributor role to IT-Team at subscription scope
- Assigned Reader role to HR-Team at subscription scope
- IT-Team (Alex, Priya) can now create and manage resources
- HR-Team (Jamie) can view resources but not change anything

### Key Roles to Remember
| Role | What it can do |
|---|---|
| Owner | Full access + manage permissions |
| Contributor | Create and manage resources, no permission control |
| Reader | View only, change nothing |

### Real World Scenario
- If a user moves departments, just move them between groups
- Permissions update automatically — no need to touch role assignments
- Which means we control the groups instead of individual users, i.e Create group based on Job Title or Department

## Key Lesson — Group Types

| Group Type | Purpose |
|---|---|
| Security | Controlling access to Azure resources via RBAC |
| Microsoft 365 | Collaboration — email, Teams, SharePoint |

- You cannot assign Azure RBAC roles to a Microsoft 365 group
- In real organisations both group types often exist side by side
- Naming convention matters — use clear names like 
  Finance-Team (M365) and Finance-Team-Access (Security)

## MFA & Conditional Access

### Security Defaults (what we enabled)
- Microsoft enables Security Defaults automatically on new tenants
- Enforces MFA registration for all users
- Blocks legacy authentication protocols
- Free — no licence required

### Conditional Access (conceptual — requires Entra ID P1/P2)
- Controls the CONDITIONS under which a user can sign in
- Different from RBAC — RBAC controls what you can access, 
  Conditional Access controls whether you can sign in at all
- Think of it as a bouncer at the door — RBAC is the list of 
  rooms you're allowed into once inside

### Example Conditional Access Rules
- Block sign-ins from outside the UK
- Require MFA when signing in from an unrecognised device
- Allow access only from a specific office network/IP range

### Key Distinction
| | What it controls |
|---|---|
| RBAC | What resources you can access and what you can do |
| Conditional Access | Whether you're allowed to sign in at all |
