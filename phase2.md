### Phase 2: Vulnerability Analysis

An application vulnerability assessment was conducted on the `/cgi-bin/badstore.cgi` script using Wapiti to identify security weaknesses.

**Command:**
```bash
wapiti -u [http://192.168.3.188/](http://192.168.3.188/)
```
***Vulnerability:*** SQL Injection (DBMS: MySQL)
***Parameter:*** searchquery
***Impact:*** Potential manipulation of the backend database.

The analysis revealed an SQL Injection vulnerability within the ⁠searchquery⁠ parameter.
