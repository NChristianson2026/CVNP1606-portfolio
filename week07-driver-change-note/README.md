Week 07 – Driver Change Note

README.md

Overview

This week’s task required identifying a driver‑related issue, selecting an appropriate remediation action, executing the fix, and documenting both the change and the rollback plan. Two devices were involved in this lab: VMware SVGA 3D and the Microphone input device. Both had been manually disabled during earlier exercises and needed to be restored to a correct operational state.



Summary of Changes

VMware SVGA 3D

The device had been manually disabled.



I performed a driver rollback to return it to the previous known-good version.



Then I performed a driver update to restore the correct, up‑to‑date VMware SVGA 3D driver.



The device was re‑enabled and verified in Device Manager.



Microphone

The device had been manually disabled.



I simply re‑enabled it because no driver corruption or version issues were present.



Why These Actions Were Chosen

VMware SVGA 3D: Rolling back and then updating ensured the graphics adapter returned to a stable, supported driver version. This avoided potential VM display issues and ensured the device was restored cleanly rather than left in a disabled or outdated state.



Microphone: The simplest correct fix was re-enabling the device. No rollback or update was necessary because the driver was already functioning normally.



Expected After State

VMware SVGA 3D is enabled, using the correct updated driver, and shows no warnings or errors.



Microphone is enabled and functioning normally.



Device Manager reflects both devices in a healthy, operational state.



Included Evidence

This folder contains the required documentation:



change-note.md



Covers before state, action taken, reasoning, and expected after state.



rollback-plan.md



Provides exact step-by-step instructions for restoring the system if the fix causes new issues.



Includes responsibility, notification requirements, verification steps, and escalation path.



Device Manager Screenshot



Shows VMware SVGA 3D and the Microphone in their updated, enabled states.

