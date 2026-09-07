Escalation Note — Week 6 Networking RCA

Tier‑1 Actions (within scope)

These are actions a Tier‑1 technician is allowed to perform:



Resetting the network adapter (disable/enable)



Returning the adapter to automatic IP/DNS (DHCP)



Running the Windows network troubleshooter



Using ipconfig, ping, nslookup, and Test-NetConnection to identify the fault layer



Guiding the user through basic network checks such as opening a known‑good website



These steps were performed during the diagnostic process.



Escalation Required (outside Tier‑1 scope)

1\. VPN Server or ACME Gateway Configuration Issues

If the device receives a correct IP but still cannot reach ACME internal resources, the issue may be with ACME’s VPN gateway or routing infrastructure.



Escalate to: ACME Network Infrastructure Team



Include:



Hostname: ACME-EMILY-REMOTE



connectivity-evidence.txt



Screenshots of adapter settings



Results from Test-NetConnection



Description of steps already attempted



2\. Firewall or Security Policy Problems

If specific ports or services are blocked, or if Test-NetConnection shows port failures while basic connectivity works, this indicates a firewall or security policy issue.



Escalate to: ACME Security Operations Team



Include:



Evidence of blocked ports



Failed gateway or service reachability tests



Troubleshooting narrative



Any relevant timestamps or error messages



Escalation Boundary Summary

Tier‑1 handles local device configuration.

Tier‑2/Infrastructure handles network-wide systems such as VPN servers, firewalls, and routing policies.

