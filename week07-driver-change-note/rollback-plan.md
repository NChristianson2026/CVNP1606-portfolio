Rollback Plan – Week 7 CVNP 1606

Purpose

This rollback plan describes the exact steps a technician must follow if the remediation actions applied to VMware SVGA 3D or the Microphone device cause new or worse problems. The goal is to safely restore the system to the previous known-good state.



1\. Rollback Steps – VMware SVGA 3D

A. Restore Previous Driver Version

Open Device Manager.



Expand Display adapters.



Right‑click VMware SVGA 3D → select Properties.



Go to the Driver tab.



Click Roll Back Driver.



Choose the option to revert to the previously installed driver.



Click OK and allow Windows to complete the rollback.



Restart the machine.



B. Re-disable the Device (if required to match original lab state)

Open Device Manager.



Right‑click VMware SVGA 3D.



Select Disable device.



Confirm the action.



C. Confirmation

Device Manager should show the previous driver version and date.



No warnings or errors should appear.



Display output should behave normally inside the VM.



2\. Rollback Steps – Microphone (Audio Input Device)

A. Return Device to Previous State

Open Device Manager.



Expand Audio inputs and outputs.



Right‑click the Microphone device.



Select Disable device.



Confirm the action.



B. Confirmation

Device Manager should show the microphone as disabled.



No warnings or errors should appear.



Applications should no longer detect an active microphone input.



3\. Responsibility

Primary Technician: The next CVNP student or assigned support technician working the ticket.



Notification Requirement:



Notify the instructor or lab supervisor immediately after performing the rollback.



Document the rollback in the portfolio folder and update the ticket or assignment notes.



4\. Verification Checklist

The technician must confirm all of the following:



VMware SVGA 3D is using the previous driver version.



The device state (enabled/disabled) matches the original pre‑change condition.



Microphone is returned to its previous disabled state.



No new warnings, errors, or degraded functionality appear after rollback.



System behavior matches the before state documented in change-note.md.



5\. Escalation Path

If the rollback does not resolve the issue:



Collect screenshots of Device Manager and any error messages.



Document the symptoms clearly.



Escalate to:



Instructor or lab supervisor for CVNP coursework issues.



VMware documentation or support if the display adapter continues to malfunction.



Do not attempt additional driver installs or registry edits without approval.

