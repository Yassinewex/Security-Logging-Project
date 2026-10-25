### Phase 2: Vulnerability Analysis

An application vulnerability assessment was conducted on the `/cgi-bin/badstore.cgi` script using Wapiti to identify security weaknesses.

**Command:**
```bash
wapiti [http://192.168.3.188/cgi-bin/badstore.cgi](http://192.168.3.188/cgi-bin/badstore.cgi) -o vulnerability_report
```
Vulnerability: SQL Injection (DBMS: MySQL)
Parameter: searchquery
Impact: Potential manipulation of the backend database.

The analysis revealed an SQL Injection vulnerability within the ⁠searchquery⁠ parameter.
