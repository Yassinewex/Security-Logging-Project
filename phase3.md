### Phase 3: Infrastructure Hardening (Reverse Proxy Configuration)

To secure the backend server and isolate infrastructure, an Apache Reverse Proxy was configured. This acts as an intermediary, forwarding client requests to the backend server while hiding its internal structure.

**Configuration Details:**
* `ProxyRequests off`: Disables forward proxy functionality for security.
* `ProxyPass`: Forwards incoming requests to the backend IP.
* `ProxyPassReverse`: Adjusts the URL in HTTP headers for redirects.
* `Substitute`: Modifies response content to rewrite URLs.

**Configuration File (`reverse-proxy.conf`):**
```text
ProxyRequests off
<Proxy *>
  Order deny,allow
  Allow from all
</Gallery>
ProxyPass / [http://192.168.3.188/](http://192.168.3.188/)
ProxyPassReverse / [http://192.168.3.188/](http://192.168.3.188/)
Substitute "s#https?://192.168.3.188([A-Za-z0-9/\-\.]*)#[http://192.168.3.188](http://192.168.3.188)"
