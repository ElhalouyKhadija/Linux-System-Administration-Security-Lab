Phase 4 — Firewall & Security Rules

Objective

The objective of this phase was to inspect the firewall configuration on Kali Linux.

Firewall Inspection

The firewall was inspected using:

sudo iptables -L -n -v

Result
	•	INPUT policy: ACCEPT
	•	FORWARD policy: ACCEPT
	•	OUTPUT policy: ACCEPT
	•	No visible firewall rules were configured.
	•	Packet counters were 0.

What I Learned
	•	Basic iptables inspection
	•	Firewall chains and policies
	•	Network traffic filtering

Practical Status

Applied / Partially Applied

The firewall configuration was inspected and verified on Kali Linux