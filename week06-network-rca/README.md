README.md — Week 6 Network RCA

Scenario

Emily Park, a remote ACME employee, reported that she could not reach the ACME intranet or shared drives. Some external websites loaded, but all ACME resources were unreachable. Her laptop worked normally the previous day. My task was to simulate a similar fault, run diagnostics, identify the fault layer, document the root cause, and write user‑safe instructions she could follow if the issue happens again.



Fault Simulated

I simulated an incorrect IP configuration by manually setting the network adapter to a static IP address outside the valid subnet:



IP Address: 10.99.99.99



Subnet Mask: 255.255.255.0



Default Gateway: (blank)



This configuration prevents the device from routing any traffic off the local machine.



Tools Used

ipconfig /all



ping 8.8.8.8



nslookup acme.internal



Test-NetConnection -ComputerName 8.8.8.8 -Port 80



Windows Network Adapter Settings



Windows Network Troubleshooter



Root Cause

The network adapter was manually configured with an incorrect static IP address (10.99.99.99) and no default gateway. Because the device was placed outside the valid subnet, it could not route traffic to ACME resources or any external host. Evidence in connectivity-evidence.txt shows that ping to 8.8.8.8 failed, nslookup returned “Server: Unknown,” and Test-NetConnection showed no reachable path. Restoring the adapter to automatic IP/DNS assignment resolved the issue.



Evidence Collected

Screenshot of incorrect static IP configuration



connectivity-evidence.txt containing:



ipconfig /all output



ping results



nslookup failure



Test-NetConnection failure



Terminal screenshot showing diagnostic commands running



evidence-report.txt showing all required files FOUND



Troubleshooting Narrative

Fault simulated and symptom:  

I set the adapter to an incorrect static IP (10.99.99.99) with no gateway. This caused complete loss of access to ACME resources and external sites.



First clear signal:  

ipconfig /all showed a static IP outside the valid subnet and a missing default gateway, indicating an IP/gateway fault layer.



First fix attempt:  

I restored the adapter to “Obtain an IP address automatically” so it could receive a valid DHCP lease.



Confirmation of fix:  

After resetting the adapter, ping to 8.8.8.8 succeeded and nslookup returned a valid DNS server instead of “Unknown.”



Verification:  

I re-ran all diagnostic commands and confirmed that IP, gateway, DNS, and port reachability were functioning normally.



Business impact if unresolved:  

Emily would remain unable to reach ACME intranet and shared drives, preventing her from completing any work tasks and causing a high-impact outage.



Escalation Note

Tier‑1 Actions

Resetting the network adapter (disable/enable)



Returning the adapter to automatic IP/DNS (DHCP)



Running Windows network troubleshooter



Verifying IP, gateway, and DNS using diagnostic commands



Escalation Required

VPN Server or ACME Gateway Configuration Issues



Escalate to: ACME Network Infrastructure Team



Provide: hostname (ACME-EMILY-REMOTE), connectivity-evidence.txt, screenshots, and Test-NetConnection results.



Firewall or Routing Policy Problems



Escalate to: ACME Security Operations Team



Provide: evidence of blocked ports, failed gateway ping, and troubleshooting narrative.



Portfolio Card

I isolated a Windows connectivity failure caused by an incorrect static IP, captured diagnostic evidence, and translated the fix into clear instructions a remote user could follow.



AI Use Statement

I used AI to help draft my root-cause explanation and user instructions. I verified all diagnostic output directly on my VM. I revised the AI’s suggestions to match my actual evidence and the Week 6 help guide.

