Remediation Change Note – Week 7 CVNP 1606

1. Before State
VMware SVGA 3D:

Driver version (before change): Same version as originally installed prior to rollback

Driver date (before change): Same date as originally installed prior to rollback

Status: Device was manually disabled during the lab exercise.

Microphone (Audio Input Device):

Status: Device was manually disabled during the lab exercise.

2. Action Taken
VMware SVGA 3D:

Performed a driver rollback to revert the device to its previous driver version.

Then performed a driver update to restore the correct, up‑to‑date VMware SVGA 3D driver.

Re‑enabled the device.

Microphone:

Simply re‑enabled the device in Device Manager.

3. Why This Action Was Chosen
VMware SVGA 3D:

Rolling back and then updating ensured the device returned to a known-good, stable driver state.

This avoided potential display issues or VM graphics instability that could occur if the device remained disabled or if an outdated driver stayed in place.

Alternative options (leaving it disabled, uninstalling the driver, or forcing a manual driver install) were rejected because they could introduce instability or break VMware display functionality.

Microphone:

The microphone had no driver corruption or version issues—only a manual disable.

Re-enabling was the least disruptive and correct remediation action.

No rollback or update was necessary because the device was functioning normally once re-enabled.

4. Expected After State
VMware SVGA 3D:

Device is enabled, using the correct updated driver, and functioning normally.

Device Manager should show no warnings, no errors, and the proper driver version/date restored.

Microphone:

Device is enabled and functioning normally.

Device Manager should show the microphone as active with no warnings.

