### Phase 5: Intrusion Detection System (Suricata IDS) Implementation

To monitor network traffic and detect malicious activities or rule violations in real-time, Suricata was deployed as an Intrusion Detection System (IDS).

#### 1. Installation & Repository Setup
Add the official Suricata PPA repository, update package indices, and install Suricata along with its rule management utility:  

```bash
sudo add-apt-repository ppa:oisf/suricata-stable -y
sudo apt-get update
sudo apt-get install suricata suricata-update -y
```
#### 2. Service Management & Verification
Verify service status and ensure Suricata starts automatically on system boot:  
```bash
sudo systemctl enable suricata
sudo systemctl status suricata
```
#### 3. Rule Management & Threat Intelligence Updates
Update the threat signature ruleset to ensure coverage against current vulnerabilities and attack vectors:  
```bash
sudo suricata-update
sudo systemctl reload suricata
```
#### 4. Configuration & Interface Binding
Configure Suricata by editing ⁠/etc/suricata/suricata.yaml⁠ to specify the monitored network interfaces, home network variables (⁠HOME_NET⁠), and active rule path sets:
```bash
sudo nano /etc/suricata/suricata.yaml
```
* Key Configuration Parameters:
   + ⁠HOME_NET⁠: Define protected internal IP ranges (e.g., ⁠[192.168.3.0/24]⁠).
   + ⁠af-packet⁠: Assign specific network interface cards (NICs) to inspect incoming/outgoing traffic.  
   + default-rule path⁠: Verify path is set to ⁠/var/lib/suricata/rules⁠.

* Test configuration syntax validity prior to restarting:
```bash
sudo suricata -T -c /etc/suricata/suricata.yaml
sudo systemctl restart suricata
```
#### 5. Log Management & Analysis

+ Suricata outputs standard operation logs and threat detection alerts to ⁠/var/log/suricata/⁠:
      * Log Files:
 ⁠        - fast.log⁠: Line-based concise log containing individual alert triggers, signatures, classification, and IP/port tuples.
 ⁠        -suricata.log⁠: System operational, startup, engine initialization, and module error logs.
+ Commands for Real-time Monitoring & Troubleshooting:
  
####  Monitor real-time intrusion alerts:
```bash
sudo tail -f /var/log/suricata/fast.log
```
####  Inspect system operational and error logs:
```bash
sudo tail -f /var/log/suricata/suricata.log
```
