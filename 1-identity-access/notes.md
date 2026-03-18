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
