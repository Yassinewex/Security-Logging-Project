### + Phase 1: Reconnaissance and Scanning

The first step involved scanning the target IP address `192.168.3.188` to identify active services and open ports.

**Command:**
```bash
nmap 192.168.3.188
```
**Results:**
```bash
Port 80/tcp    open  http
Port 443/tcp   open  https
Port 3306/tcp  open  mysql
```
The scan confirms that the web server is running HTTP (port 80) and HTTPS (port 443) services, and a MySQL database (port 3306) is also accessible.
