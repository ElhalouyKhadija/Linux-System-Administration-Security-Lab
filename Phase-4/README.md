Phase 4 — Firewall & Security Rules

Objective

The objective of this phase was to inspect the firewall configuration on Kali Linux and understand the current network filtering policies.

The firewall configuration was reviewed using iptables.

1. Firewall Inspection

The current firewall configuration was inspected with:

sudo iptables -L -n -v

Command Options
	•	-L — Lists the firewall rules.
	•	-n — Displays IP addresses and ports numerically.
	•	-v — Displays detailed information, including packet and byte counters.

2. Firewall Chains

The command displays three main firewall chains:

INPUT

Controls network traffic entering the Kali Linux system.

FORWARD

Controls packets that are routed through the system.

OUTPUT

Controls network traffic leaving the system.

3. Observed Configuration

The inspection showed the following default policies:

Chain	Policy
INPUT	ACCEPT
FORWARD	ACCEPT
OUTPUT	ACCEPT

No visible filtering rules were configured at the time of the test.

The packet and byte counters were also 0.

4. Security Observation

The firewall configuration was inspected as part of the security assessment.

The system was using ACCEPT as the default policy for the main chains, and no visible iptables filtering rules were present during the inspection.

No firewall rules were added, removed, or modified during this phase.

5. What I Learned
	•	How to inspect Linux firewall configuration
	•	How iptables chains work
	•	Difference between INPUT, FORWARD, and OUTPUT
	•	How firewall policies are displayed
	•	How to read packet and byte counters
	•	How to perform a basic firewall security check

Evidence

The practical work was performed on Kali Linux and verified using the terminal command and screenshot.

Practical Status

Applied / Partially Applied

The firewall configuration was successfully inspected and documented. No firewall configuration changes were performed during this phase.