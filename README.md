# homelab-networking-fundamentals

## Overview

This portfolio demonstrates my ability to diagnose and resolve common network issues using essential IT support tools. These skills are critical for helpdesk and entry-level IT roles.
## 📋 Key Commands Mastered

The following command we run

### IP Configuration Command

| Command | Purpose | When to Use |
|---------|---------|-------------|
| `ipconfig /all` | View network configuration | Initial troubleshooting - check if computer has valid IP address |
| `ping` | Test connectivity | Check if device is reachable on the network |
| `tracert` | Trace network path | Find where connection breaks along the route |
| `nslookup` | Test DNS resolution | Diagnose name resolution issues |
| `Test-NetConnection` | Test ports/services | Verify specific services are running and accessible |

### 🖥️ Command Demonstrations

#### 1. ipconfig /all - Network Configuration Check
Why I ran it: First step in any network issue - check if the computer has a valid IP address.

Command:

cmd
ipconfig /all
Output:
https://screenshots/ipconfig-all.png

##### What I Learned:

- The first thing to check when troubleshooting
- Shows if computer has an IP, subnet, gateway, and DNS
- Confirms DHCP is working (or if using static IP)
- Identifies which DNS servers are being used

#### 2. ping - Connectivity Testing
Why I ran it: To verify connectivity at different levels - local, network, internet, and DNS.

##### Test 1: Local Connectivity
cmd
ping 127.0.0.1
Output:
https://screenshots/ipconfig-all.png

##### What I Learned:

- Verifies TCP/IP stack is working
- If this fails, there's a serious OS-level issue
- This is the first test before checking anything else
- Identifies which DNS servers are being used

##### Test 2: Network Connectivity
cmd
ping 172.16.0.10
Output:
https://screenshots/ipconfig-all.png

##### What I Learned:

- Tests if I can reach specific devices on my network
- DC01 responds - internal network is working
- Use ping [hostname] to test DNS + connectivity

##### Test 3: Internet Connectivity
cmd
ping 8.8.8.8
Output:
https://screenshots/ipconfig-all.png

##### What I Learned:

- Tests internet connectivity without DNS dependency
- Good response time (12ms) indicates healthy internet
- If this fails but internal ping works, gateway is the issue

##### Test 4: DNS Resolution
cmd
ping google.com
Output:
https://screenshots/ipconfig-all.png

##### What I Learned:

- Tests internet connectivity without DNS dependency
- Good response time (12ms) indicates healthy internet
- If this fails but internal ping works, gateway is the issue

##### Key takeaway
use a layered approach with ping: first loopback (127.0.0.1), then my own IP, then the gateway, then an external IP like 8.8.8.8, and finally a domain name like google.com. This tells me exactly where the connectivity problem is - whether it's local, network, or DNS-related.
Use a layered approach with ping: first loopback (127.0.0.1), then my own IP, then the gateway, then an external IP like 8.8.8.8, and finally a domain name like google.com. This tells me exactly where the connectivity problem is - whether it's local, network, or DNS-related.
