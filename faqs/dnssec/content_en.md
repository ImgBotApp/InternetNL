## Why
Below you will find some links to descriptions of some known incidents that DNSSEC probably could have prevented. 

* ["Cache-poisoning attack snares top Brazilian bank"](https://www.theregister.co.uk/2009/04/22/bandesco_cache_poisoning_attack/)
* ["Eircom reveals ‘cache poisoning’ attack by hacker led to outages"](https://www.siliconrepublic.com/enterprise/eircom-reveals-cache-poisoning-attack-by-hacker-led-to-outages)
* ["DNS cache poisonings foist malware attacks on Brazilians"](https://www.theregister.co.uk/2011/11/07/brazilian_dns_cache_poisoing_attacks/)
* ["Probable Cache Poisoning of Mail Handling Domains"](http://www.cert.org/blogs/certcc/post.cfm?EntryID=206)
* ["Neither Snow Nor Rain Nor MITM... An Empirical Analysis of Email Delivery Security"](http://dl.acm.org/citation.cfm?id=2815695)

Below follows a quotation from the last mentioned research publication:

> Mail security, like that of many other protocols, is intrinsically tangled with the security of DNS resolution. Rather than target the SMTP protocol, an active network attacker can spoof the DNS records of a destination mail server to redirect SMTP connections to a server under the attacker’s control. [...] We find evidence that 178,439 out of 8,860,639(2.01%) publicly accessible DNS servers provided invalid IPs or MX records for one or more of these domains.

## Adoption statistics
* [.nl stats and data](http://stats.sidnlabs.nl/#/dnssec) by SIDN Labs
* [DNSSEC Validation Measurement](https://stats.labs.apnic.net/dnssec) by APNIC
* [DNSSEC Deployment Report](http://dnssec-deployment.icann.org/dctld/)

## Further information
* [ISOC's Deploy360 on DNSSEC](http://www.internetsociety.org/deploy360/dnssec/)
* [SIDN about DNSSEC](https://www.sidn.nl/a/internet-security/dnssec?language_id=2)
* [Wikipedia on DNSSEC](https://en.wikipedia.org/wiki/Domain_Name_System_Security_Extensions)
* [DNSSEC.net](http://www.dnssec.net/)

## Specifications
* [RFC 4033: DNS Security Introduction and Requirements](https://datatracker.ietf.org/doc/rfc4033)
* [RFC 4034: Resource Records for the DNS Security Extensions](https://datatracker.ietf.org/doc/rfc4034)
* [RFC 4035: Protocol Modifications for the DNS Security Extensions](https://datatracker.ietf.org/doc/rfc4035)
