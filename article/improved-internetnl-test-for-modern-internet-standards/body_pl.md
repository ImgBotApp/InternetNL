*"Since its first launch in april 2015 over 300.000 tests were executed on Internet.nl. More than 50% of the retested websites show improvements. We hope the improved Internet.nl will be even more helpful for people to test, require and get modern, secure Internet Standards."*, says Gerben Klein Baltink, chair of the Dutch Internet Standards Platform.

Internet.nl helps users to check whether their internet is up to date. Do your website, email and internet connection use modern and reliable internet standards? And if they don’t, what can you do about it?

Internet.nl is an initiative of the Dutch Internet Standards Platform that pushes the adoption of modern Internet Standards like IPv6, DNSSEC, HTTPS, DMARC, STARTTLS and DANE. In this platform the following partners from the internet community and the Dutch government collaborate: [DHPA](https://dhpa.nl/), [ECP](https://ecp.nl/), [Forum Standaardisatie](https://forumstandaardisatie.nl/), [Internet Society internationaal](https://internetsociety.org/), [Internet Society Nederland](https://isoc.nl/), [ISPConnect](https://ispconnect.nl/), [Ministerie van Economische Zaken](https://www.rijksoverheid.nl/ministeries/ministerie-van-economische-zaken), [NCSC](https://ncsc.nl/), [NLnet](https://nlnet.nl/), [NLnet Labs](https://nlnetlabs.nl/), [RIPE NCC](https://ripe.net/), [SIDN](https://sidn.nl/) and [SURFnet](https://surfnet.nl/).

[Open Netlabs](https://www.opennetlabs.com/) / NLnet Labs is responsible for the technical implementation of the Internet.nl website. The new layout is designed by [WBVB](https://wbvb.nl/) and [200OK](https://www.200ok.nl/).

---
## Release notes

- Web redesing features:
  - Site is more easily accessible by users with disabilities;
  - Site is designed to be accessed by mobile devices;
  - Tests' details reworked:
     - Grouped under sections;
     - Test explanation for every test;
     - Compact technical details for all servers in a test.
  - Link to rerun the same test from the results' page;
  - Aside boxes in the results' page:
     - Immediately run suggested tests or start new tests;
     - Follow links to suggested test websites for further testing.
- New: We require at least 2 IPv6-enabled nameservers for full score on the IPv6 test.
- Bugfixes:
  - Partial IPv6 connectivity was falsely reported as good result (only visually, the score was correct);
  - Multiple SPF records were not resulting in error.
