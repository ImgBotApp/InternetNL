## I. Algemeen

### Wat is DNS?
Domain Name System (DNS) is het registratiesysteem van namen en bijbehorende nummers op het internet. Het is vergelijkbaar met een telefoonboek. Dit systeem kan worden bevraagd om namen naar nummers te vertalen en omgekeerd.

### Waarom DNS?
Ieder apparaat dat met het internet is verbonden, heeft een uniek numeriek adres namelijk het IP-adres. Voorbeelden daarvan zijn `94.198.159.35` (IPv4) en `2a00:d78:0:712:94:198:159:35` (IPv6). Omdat IP-adressen moeilijk te onthouden zijn én bovendien nog wel eens kunnen wijzigen, zijn domeinnamen in het leven geroepen. Een voorbeeld is `example.nl`. Een domeinnaam zie je onder andere in de balk bovenin je webbrowser als je een website bezoekt. Maar je gebruikt ook een domeinnaam als je e-mail adresseert, bijvoorbeeld aan `iemand@example.nl`. DNS knoopt domeinnamen en IP-adressen aan elkaar.

### Is DNS beveiligd?
Nee, de vertaling van domeinnaam naar IP-adres is niet beveiligd. Daardoor kan een kwaadwillende de vertaling vervalsen en een gebruiker omleiden naar een kwaadaardig IP-adres. Gelukkig bestaat er een oplossing, namelijk DNSSEC.

### Wordt de onveiligheid van DNS misbruikt?
Ja, hieronder volgt een aantal incidenten die publiekelijk bekend zijn. Lang niet altijd wordt een aanval gedetecteerd of, als dat wel het geval is, openbaar gemaakt.

* ["Cache-poisoning attack snares top Brazilian bank"](https://www.theregister.co.uk/2009/04/22/bandesco_cache_poisoning_attack/)
* ["Eircom reveals ‘cache poisoning’ attack by hacker led to outages"](https://www.siliconrepublic.com/enterprise/eircom-reveals-cache-poisoning-attack-by-hacker-led-to-outages)
* ["DNS cache poisonings foist malware attacks on Brazilians"](https://www.theregister.co.uk/2011/11/07/brazilian_dns_cache_poisoing_attacks/)
* ["Probable Cache Poisoning of Mail Handling Domains"](http://www.cert.org/blogs/certcc/post.cfm?EntryID=206)
* ["Neither Snow Nor Rain Nor MITM... An Empirical Analysis of Email Delivery Security"](http://dl.acm.org/citation.cfm?id=2815695)

Uit de laatste onderzoekspublicatie komt het onderstaand citaat:
> Mail security, like that of many other protocols, is intrinsically tangled with the security of DNS resolution. Rather than target the SMTP protocol, an active network attacker can spoof the DNS records of a destination mail server to redirect SMTP connections to a server under the attacker’s control. [...] We find evidence that 178,439 out of 8,860,639
(2.01%) publicly accessible DNS servers provided invalid IPs or MX records for one or more of these domains.

### Wat is DNSSEC?
DNSSEC, een afkorting van Domain Name System Security Extensions, breidt DNS uit met een extra beveiligingslaag. Het zorgt ervoor dat de vertaling van domeinnaam naar IP-adres is voorzien van een digitale handtekening. Een internetgebruiker kan die handtekening automatisch laten controleren.

### Waarom DNSSEC?
Door de domeinnaam-handtekening te controleren kan een kwaadwillende de vertaling niet langer ongemerkt vervalsen. Dit voorkomt dat de gebruiker kan worden misleid naar een kwaadaardig IP-adres.

### Wat beveiligt DNSSEC precies?
DNSSEC zorgt ervoor dat authenticiteit en integriteit van DNS-vertalingen kan worden gecontroleerd. De vertrouwelijkheid beschermt DNSSEC echter niet. DNS-vertalingen kunnen dus wel nog worden afgeluisterd, maar ze zijn niet meer te manipuleren.

### Biedt DNSSEC nog andere voordelen?
Andere beveiligingsstandaarden kunnen voortbouwen op DNSSEC als onderliggende beveiligingslaag. Behalve IP-adressen kan namelijk ook andere domeindata in de DNS worden geregistreerd. Standaarden als SPF, DKIM, DMARC (anti-phishing) en DANE (beveiligde verbindingen) maken daar gebruik van. Deze profiteren van de betrouwbaarheid die DNSSEC biedt.

## II. Voor domeinnaamhouders

### Hoe weet ik of mijn domeinnnaam is ondertekend met DNSSEC?
Doe de websitetest of de e-mailtest op Internet.nl. Eén van de testonderdelen controleert DNSSEC. Let op: Het komt regelmatig voor dat een mailserver een andere domeinnaam heeft dan uw eigen domeinnaam. Bijvoorbeeld omdat uw eigen domein (bijv. `@example.nl`; het mailto-domein) gebruik maakt van de mailserver van een derde partij (bijv. `mailserver.example.com`; het mailserver-domein). In de mailtest worden beide domeinnamen gecontroleerd op DNSSEC.

### Hoe onderteken ik mijn domeinnaam met DNSSEC?
Als jouw domeinnaam nog niet beveiligd is met DNSSEC:

1. Vraag jouw registrar om DNSSEC op korte termijn te ondersteunen;
2. Als hij dat niet kan, kies dan voor een registrar die wel DNSSEC ondersteunt. Voor .nl-domeinnamen zie het [registraroverzicht](https://www.sidn.nl/registrars/?name=&country=&dnssec=true) van SIDN;
3. Verhuis je domeinnaam naar een registrar naar keuze. Voor verhuizing van .nl-domeinnamen zie [domeinnaam verhuizen](https://www.sidn.nl/a/nl-domeinnaam/domeinnaam-verhuizen) van SIDN.

De registrar is de partij die voor jou de domeinnaam heeft geregistreerd. Voor DNSSEC is ook de medewerking nodig van de beheerder van de domeinnaam-servers (oftewel nameservers). Vaak is dat de registrar, maar dat kan ook een andere partij zijn. De registrar en de domeinnamen van de nameservers voor .nl-domeinen zijn in te zien via de [whois](https://www.sidn.nl/whois/) van SIDN.

### Hoeveel andere partijen hebben hun domeinnaam ondertekend met DNSSEC?
Op de website van SIDN Labs wordt [bijgehouden](https://stats.sidnlabs.nl/#/dnssec) hoeveel .nl domeinnamen inmiddels zijn beveiligd met DNSSEC. Als je wilt weten of een specifieke domeinnaam beveiligd is met DNSSEC, doe dan de website- of e-mailtest op Internet.nl.

## III. Voor internetgebruikers

### Hoe weet ik of domeinnaam-handtekeningen worden gecontroleerd?
Dit kun je controleren door de verbindingentest op Internet.nl uit te voeren. Deze test controleert of de internetverbinding die je op dat moment gebruikt over een modern adres (IPv6) beschikt, en of domein-handtekeningen worden gecontroleerd (DNSSEC validatie). 

### Hoe kan ik ervoor zorgen dat domeinnaam-handtekeningen worden gecontroleerd?
Vraag aan je internetprovider op welke termijn deze van plan is om DNSSEC validatie toe te gaan passen. Als er geen plannen zijn om dit op korte termijn te gaan doen, stap dan over naar een internetprovider die dit wel doet, of maak gebruik van een aparte DNS provider die DNSSEC validatie ondersteunt. 

### Hoeveel andere partijen controleren domeinnaam-handtekeningen?
Het gebruik van DNSSEC neemt nog steeds toe, maar de groei lijkt af te vlakken. Van mei 2015 tot mei 2017 groeide het gebruik van DNSSEC op .nl met slechts 3%, terwijl de groei van mei 2014 tot mei 2015 ongeveer 12% bedroeg. Dit is eigenlijk verbazingwekkend aangezien het DNS protocol een van de meest cruciale protocollen op het internet is, en geeft aan dat het belangrijk blijft om de adpoptie van veilige en betrouwbare internetstandaarden te blijven stimuleren. 

Statistieken van DNSSEC-adoptie:
* [.nl stats and data](http://stats.sidnlabs.nl/#/dnssec) door SIDN Labs
* [DNSSEC Validation Measurement](https://stats.labs.apnic.net/dnssec) door APNIC
* [DNSSEC Deployment Report](http://dnssec-deployment.icann.org/dctld/)

## Meer informatie
* [DNSSEC.nl](https://dnssec.nl)
* [SIDN over DNSSEC](https://www.sidn.nl/a/veilig-internet/dnssec)
* Facstsheet "DNSSEC: Voorkom domeinnaamfraude" ([uitgebreid](https://www.ibdgemeenten.nl/downloads/?id=3614) / [kort](https://www.ibdgemeenten.nl/downloads/?id=3616)) door Informatiebeveiligingsdienst voor gemeenten
