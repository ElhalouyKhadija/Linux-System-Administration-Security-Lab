# Phase 2 — Network Configuration & Connectivity

# Check network interfaces
ip addr

# Check routing table
ip route

# Check default gateway
ip route | grep default

# Check DNS configuration
cat /etc/resolv.conf

# Test connectivity to Google DNS
ping -c 4 8.8.8.8

# Test connectivity to Cloudflare DNS
ping -c 4 1.1.1.1

# Test HTTP/HTTPS connectivity
curl -I https://google.com