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

## Questions I Still Have
- What if I want to add 100s of users at the same time and add them to the group as well? Do I have to do it manually?
```
