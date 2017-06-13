We testen of je webserver HTTPS afdwingt door een verwijzing (d.w.z. 301/302 redirect) van HTTP naar HTTPS op dezelfde domeinnaam, of door ondersteuning van alleen HTTPS. Ingeval van verwijzing is moet een domein eerst zelf 'upgraden' via een redirect naar HTTPS voordat het  eventueel doorverwijst naar een andere domeinnaam. Dit zorgt er ook voor dat een webbrowser de HSTS kan accepteren. Voorbeelden van correcte redirect-volgorde:

* http://example.nl --> https://example.nl --> https://www.example.nl 
* http://www.example.nl --> https://www.example.nl

Zie [Webapplicatie-richtlijnen van NCSC, Verdieping](https://www.ncsc.nl/actueel/whitepapers/ict-beveiligingsrichtlijnen-voor-webapplicaties.html), richtlijn U/WA.05.
