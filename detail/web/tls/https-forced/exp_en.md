We check if your web server enfroces HTTPS by a 301/302 redirect from HTTP to HTTPS on the same domain, or by supoorting only HTTPS. In case of redirecting a domain should firstly upgrade itself by redirecting to HTTPS before it may redirect to another domain. This makes also sure that the HSTS-policy will be accepted by the web browser. Examples of correct redirect orders:

*  http://example.nl > https://example.nl > https://www.example.nl 
* http://www.example.nl > https://www.example.nl

See Web application guidelines from NCSC-NL, guideline U/WA.05 (in Dutch).
