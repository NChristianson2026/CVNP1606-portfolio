ACME Kiosk \& Seasonal Staff Access Control Memo

Ticket: CVNP1606‑W03‑003

Prepared by: Nakota Christianson

System: ACME‑W11‑BASELINE

Date: 11 September 2026



1\. Purpose

Document account creation, group membership auditing, and least‑privilege decisions for the ACME kiosk system.



2\. Work Completed

Created seasonal staff accounts (standard users)



Created kiosk account and configured Assigned Access



Verified UAC behavior for non‑admin accounts



Audited Administrators and Users groups



Exported evidence (evidence-report.txt)



3\. Account Configuration

Seasonal Staff

Created as Local Standard Users.

They only need access to kiosk‑approved applications, not system configuration.



Reasoning:  

Standard rights prevent accidental system changes, software installation, or bypassing kiosk restrictions.



Kiosk Account

Created as a Local Standard User and locked into Assigned Access.



Reasoning:  

Kiosk Mode requires a restricted environment. Admin rights would break isolation and expose the system to misuse.



4\. Group Audit

Commands used:



Code

Get-LocalGroupMember -Group "Administrators"

Get-LocalGroupMember -Group "Users"

Findings:



Administrators group contained only authorized ACME technicians



Users group contained seasonal staff and kiosk accounts



No unauthorized admin accounts found



5\. UAC Verification

Standard users were correctly blocked from elevation.

Admin credentials were required for privileged actions.

Kiosk account remained restricted under Assigned Access.



6\. Evidence

Stored in the repository:



evidence-report.txt



Group membership screenshots



PowerShell output



Kiosk configuration evidence



7\. Summary

The system now follows ACME least‑privilege standards:



Seasonal staff = standard users



Kiosk account = standard user in Assigned Access



Admin rights limited to technicians



UAC blocks elevation attempts



No unauthorized admin access detected



8\. Completion

All tasks for CVNP1606‑W03‑003 are complete.

The kiosk is secure, restricted, and ready for seasonal deployment.

