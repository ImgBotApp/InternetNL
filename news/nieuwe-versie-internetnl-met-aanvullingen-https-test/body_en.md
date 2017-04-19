Below we describe the major changes.

* The previous version of Internet.nl did test the **security of the HTTPS configuration over either IPv6 or IPv4**. Through manual testing we regularly see websites that have unintended different HTTPS configurations over IPv6 and IPv4. Therefore in the new release the HTTPS configuration is tested over both IPv6 and IPv4. **From now on** the result of this test item  is part of the overall score in the website test.
* The website tests checks whether a **HSTS policy** is published. Through HSTS a web browser gets informed after the first usage that a website only may be visited over HTTPS. This can prevent so-called man-in-the-middle attacks (for example when a public Wi-Fi hotspot is used). The result of this test item is displayed as an orange warning in case the HSTS policy is absent. As of **July 2016** the result will be part of the score in the website test.
* The website test does test whether **HTTPS is enforced** for a website. There are two ways to enforce HTTPS that are described below.The result of this test item is displayed as an orange warning in case the HSTS policy is absent. As of **July 2016** the result will be part of the score in the website test.
   1. By redirecting HTTPS to HTTPS. This can be done by redirecting `https://example.nl` to `https://example.nl`.  It is important that both domain names are identical because a web browser does only accept a HSTS policy for a certain domain when a HTTPS connection is used. If `http://example.nl` redirects to `https://www.example.nl` then a HSTS policy normally will not be used by the browser, unless a user explicitly enters `https://example.nl` or clicks on a hyperlink with this URL.
   2. By only supporting HTTPS and no HTTP. Because a browser normally uses a HTTP-connection after a user enters a domain name, users should enter `https://example.nl` to reach the website or click on a hyperlink with this URL.
* The website test does check whether **HTTP compression** is used. Enabling HTTP compression does make many websites  vulnerable for BREACH when no other mitigating measures are in place. Switching off HTTP compression could negatively impact performance. In case HTTP compression is detected an **orange warning** is displayed.
* The website test of the previous version of Internet.nl already checked whether the **content of a website was similar over IPv6 and IPv4**. The test took into account legitimate differences for example caused by different add banners. The result of this test item **from now on** is part of the overall score in the website test. 
* If a user does enter a **non-existing domain name** a red error message is displayed. 


***
**More information:**

* [ICT-Beveiligingsrichtlijnen voor Webapplicaties van NCSC](https://www.ncsc.nl/actueel/whitepapers/ict-beveiligingsrichtlijnen-voor-webapplicaties.html) [Dutch]
* [ICT-beveiligingsrichtlijnen voor Transport Layer Security (TLS)](https://www.ncsc.nl/actueel/whitepapers/ict-beveiligingsrichtlijnen-voor-transport-layer-security-tls.html) [Dutch]
* [RFC 6797: HTTP Strict Transport Security (HSTS)](https://tools.ietf.org/html/rfc6797)
* [Breach Attack](http://breachattack.com/)
