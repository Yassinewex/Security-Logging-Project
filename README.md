# Project: Web Application Security and Reverse Proxy Setup with ModSecurity

## 📌 Overview
This project documents the practical process of scanning a target environment, identifying security vulnerabilities, and implementing defensive mechanisms using a reverse proxy and a Web Application Firewall (WAF).

## 🎯 Objectives
- **Conduct** network reconnaissance to identify open ports and running services.
- **Analyze** application request flows to detect potential injection vulnerabilities.
- **Deploy** an Apache Reverse Proxy to isolate the backend infrastructure.
- **Implement** ModSecurity to filter malicious traffic and protect against common web attacks.
- **Deploy** Suricata to monitor network traffic and provide real-time intrusion detection and alerting capabilities.

## 🛠️ Tools Used
- **Nmap**: For network scanning and port discovery.
- **Wapiti**: For web application vulnerability scanning.
- **Apache2**: Web server and reverse proxy implementation.
- **ModSecurity**: Open-source Web Application Firewall (WAF).
- **Suricata** : For real-time network traffic analysis and intrusion detection.

## 🚀 Implementation Steps

### Phase 1: Reconnaissance and Scanning
The first step involved scanning the target IP address `192.168.3.188` to identify active services and open ports. The scan results revealed the following open ports:

```text
Port 80/tcp    open  http
Port 443/tcp   open  https
Port 3306/tcp  open  mysql
```
### Phase 2: Vulnerability Analysis
An application vulnerability assessment was conducted on the ⁠/cgi-bin/badstore.cgi⁠ script using Wapiti to identify security weaknesses. The analysis revealed an SQL Injection vulnerability within the ⁠searchquery⁠ parameter, allowing for potential manipulation of the backend database.

### Phase 3: Infrastructure Hardening (Reverse Proxy Configuration)
To secure the backend server, an Apache Reverse Proxy was configured. This acts as an intermediary, forwarding client requests to the backend while hiding the internal server structure. The ⁠reverse-proxy.conf⁠ file was set up with ⁠ProxyPass⁠ and ⁠ProxyPassReverse⁠ directives pointing to the internal server.

### Phase 4: Implementing the Web Application Firewall (WAF)
To mitigate threats such as SQL Injection, ModSecurity was installed and integrated into the Apache environment. The ⁠security2⁠ module was enabled, and the configuration was tested to ensure syntax integrity before restarting the Apache service.

### Phase 5: Intrusion Detection System Deployment
 * Deploy and configure Suricata as an Intrusion Detection System (IDS) to monitor network traffic in real time.  
 * Implement rule-based detection to identify malicious activities, unauthorized access, and potential security threats.  
 * Analyze Suricata alerts and logs to validate security configurations and confirm the effectiveness of the detection mechanisms.  

## 🛡️ Conclusion

The successful implementation of the Reverse Proxy and ModSecurity provides a robust defensive layer, effectively intercepting and neutralizing malicious requests targeting the application. Complementing this, the deployment of Suricata completes the defensive pipeline by offering real-time network traffic analysis and threat detection, ensuring comprehensive security monitoring and alerting against diverse vulnerabilities and attacks.

