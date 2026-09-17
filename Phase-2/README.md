Phase 2 — Network Configuration & Connectivity

Objective

This phase focused on checking the network configuration and connectivity on Kali Linux.

Network Configuration
	•	Interface: eth0
	•	IP address: 192.168.0.117/24
	•	Default gateway: 192.168.0.1
	•	DNS server: 192.168.0.1

Connectivity Tests
	•	ping -c 4 8.8.8.8 → 4 received, 0% packet loss
	•	ping -c 4 1.1.1.1 → 4 received, 0% packet loss
	•	curl -I https://google.com → HTTP/2 301

What I Learned
	•	Linux network interfaces
	•	Routing and default gateway
	•	DNS configuration
	•	Network connectivity testing

Practical Status

Applied / Completed

Practically performed on Kali Linux.