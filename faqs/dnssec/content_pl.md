## Dlaczego DNSSEC
Poniżej znajdziecie linki do opisów niektórych znanych incydentów, których DNSSEC prawdopodobnie mógł zapobiec.

* ["Cache-poisoning attack snares top Brazilian bank"](https://www.theregister.co.uk/2009/04/22/bandesco_cache_poisoning_attack/)
* ["Eircom reveals ‘cache poisoning’ attack by hacker led to outages"](https://www.siliconrepublic.com/enterprise/eircom-reveals-cache-poisoning-attack-by-hacker-led-to-outages)
* ["DNS cache poisonings foist malware attacks on Brazilians"](https://www.theregister.co.uk/2011/11/07/brazilian_dns_cache_poisoing_attacks/)
* ["Probable Cache Poisoning of Mail Handling Domains"](http://www.cert.org/blogs/certcc/post.cfm?EntryID=206)
* ["Neither Snow Nor Rain Nor MITM... An Empirical Analysis of Email Delivery Security"](http://dl.acm.org/citation.cfm?id=2815695)

Poniżej znajduje się cytat z ostatniej publikacji

> Bezpieczeństwo poczty elektronicznej, podobnie jak wiele innych protokołów jest nierozerwalnie związana z bezpieczenstem rozpoznawania nazw DNS. Zamiast adresować protokół SMTP, aktywny napastnik sieciowy może spoofować rekordy DNS docelowego serwera pocztowego, aby przekierować połączenia SMTP z serwerem pod kontrolą osoby atakującej. [...] Dowiadujemy się, że 178439 z 8 860,639 (2,01%) publicznie dostępnych serwerów DNS dostarczało nieprawidłowe adresy IP lub rekordy MX dla jednej lub więcej z tych domen.

## Statystyki przyjęcia
* [.nl stats and data](http://stats.sidnlabs.nl/#/dnssec) by SIDN Labs
* [DNSSEC Validation Measurement](https://stats.labs.apnic.net/dnssec) by APNIC
* [DNSSEC Deployment Report](http://dnssec-deployment.icann.org/dctld/)

## Dalsze informacje
* [ISOC's Deploy360 on DNSSEC](http://www.internetsociety.org/deploy360/dnssec/)
* [SIDN about DNSSEC](https://www.sidn.nl/a/internet-security/dnssec?language_id=2)
* [DNSSEC.net](http://www.dnssec.net/)
* [DNSSEC/TLSA Validator](https://www.dnssec-validator.cz/)
* [Wikipedia on DNSSEC](https://en.wikipedia.org/wiki/Domain_Name_System_Security_Extensions)

## Specyfikacje
* [RFC 4033: DNS Security Introduction and Requirements](https://datatracker.ietf.org/doc/rfc4033)
* [RFC 4034: Resource Records for the DNS Security Extensions](https://datatracker.ietf.org/doc/rfc4034)
* [RFC 4035: Protocol Modifications for the DNS Security Extensions](https://datatracker.ietf.org/doc/rfc4035)
