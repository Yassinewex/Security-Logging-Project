### Phase 4: Implementing the Web Application Firewall (WAF)

To mitigate threats such as SQL Injection, ModSecurity was installed and integrated into the Apache environment as a Web Application Firewall (WAF).

* **Installation Command:**
```bash
sudo apt-get install libapache2-mod-security2
```
```bash
sudo a2enmod security2
```
```bash 
sudo apachectl configtest
```
```bash
sudo systemctl restart apache2
```
