The following improvements have been made on [Internet.nl](/).
## Generic
* The ability to choose a different language from a dropdown menu. Visitors will get the equivalent page in the selected language (if available).
* The requirement that all name servers must be available over IPv6 has been cancelled. It is sufficient if at least as many name servers are available over IPv6 as there are over IPv4. This applies to both the webite test and the mail test.

## Connection test
* The detection of the internet provider is more precise and timeouts occur less frequent. 

## Website test
* The test checks whether a HSTS-policy is available. Through HSTS a web browser will 'know' after the first visit that a website can only be accessed through a secure connection (HTTPS, not HTTP). This can prevent so-called man-in-the-middle attacks, e.g. when using public Wi-Fi. In case of deviations, the message is no longer 'orange' but 'red'.
* The test now checks whether the website enforces HTTPS by using a server redirect (301 or 302) or by applying only HTTPS (and no HTTP). In case of deviations, the message is no longer 'orange' but 'red'.
* In the case of some websites, the TLS results incorrectly showed that 'client-initiated renegotiation' was allowed. This has been solved.
* In the test results of websites with a redirect from IPv6/IPv4 to IPv4-only, the HSTS-policy over IPv6 remained incorrectly undetected. This has been solved.
* The test now checks whether actual HTTP traffic is sent over port 443. If that is not the case, the test will no longer draw incorrect conclusions which are HTTPS-related .

## Mail test
* If Internet.nl cannot establish a connection to a mail server (e.g. by 'rate limiting'), visitors will now be asked to try again later.
* Thanks to the improved adjustment of timeouts, failure of the test part 'STARTTLS' is less likely. Therefore certain mail servers can now be tested without problems.
* Running connections serially and minimizing the number of connections should help to reduce the risk of 'rate limiting' of mail servers. Therefore certain mail servers can now be tested which was not possible before.

## Background information
* [ICT-beveiligingsrichtlijnen voor webapplicaties van NCSC - Verdieping](https://www.ncsc.nl/binaries/content/documents/ncsc-nl/actueel/whitepapers/ict-beveiligingsrichtlijnen-voor-webapplicaties/4/ICT%2BBeveiligingsrichtlijnen%2Bvoor%2BWebapplicaties%2B%2B%2BVerdieping%2B%2B%2BPrintversie.pdf) onder '05 Versleutel communicatie' op p.29 [Dutch];
* [ICT-beveiligingsrichtlijnen voor TLS van NCSC](https://www.ncsc.nl/actueel/whitepapers/ict-beveiligingsrichtlijnen-voor-transport-layer-security-tls.html) [Dutch];
* [TLS - veelgestelde vragen ](/faqs/tls/) onder 'TLS-test voor mail' [Dutch].
