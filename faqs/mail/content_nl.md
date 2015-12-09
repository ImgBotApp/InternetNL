**Deze pagina is nog onder constructie; deze informatie komt binnenkort
beschikbaar.**

Onderaan deze pagina vind je wel al links naar meer informatie over
standaarden voor e-mail-authenticatie.

## Algemeen

### Wat doen DKIM, SPF en DMARC?

DKIM, SPF en DMARC zijn drie internetstandaarden voor het terugdringen van
phishing, spam, virussen en andere narigheid die per e-mail bezorgd wordt.
Deze drie standaarden worden meestal gezamenlijk ingezet om te controleren dat
de afzender (een mail-adres) en de verzender (een computersysteem) van een
mail-bericht inderdaad kloppen, en dat de inhoud van het bericht onderweg niet
is veranderd.

Alle drie standaarden gebruiken het [DNS-systeem](/faqs/dnssec/#DNS) om
informatie online te publiceren. Volgens de standaarden is het niet
noodzakelijk om daarbij ook [DNSSEC](/faqs/dnssec/) te gebruiken &mdash; een
beveiligingssysteem voor DNS &mdash; maar dat willen we hier toch van harte
aanraden.

### Wat is DKIM?

DKIM zorgt voor de beveiliging van mail-berichten. Daarvoor wordt de inhoud en
de &quot;envelope&quot; van elk uitgaand bericht van een digitale handtekening
voorzien. Zo wordt voorkomen dat kwaadwillenden een bericht namens een ander
kunnen verzenden (spoofing) of de inhoud van een bericht onderweg kunnen
veranderen.

### Wat is SPF?

SPF voorkomt dat &quot;elektronische brievenbussen&quot; mail-berichten
accepteren van ongeauthoriseerde computersystemen. Alleen berichten van
systemen die daadwerkelijk berichten voor een specifiek
[domein](/faqs/dnssec/#domeinnaam) mogen versturen komen er doorheen. Daarvoor
wordt een lijst van geldige verzenders via het
[DNS-systeem](/faqs/dnssec/#DNS) online gepubliceerd. Ontvangende systemen
kunnen deze lijst gebruiken om de verzender te controleren voor zij een
bericht aannemen.

### Wat is DMARC?

DMARC is een aanvulling op de andere twee beveiligingsstandaarden voor e-mail,
[DKIM](/faqs/mail/#dkim) en [SPF](/faqs/mail/#spf).
DMARC geeft &quot;elektronische brievenbussen&quot; een aanwijzing hoe om te
gaan met inkomende berichten waarvan de DKIM- of SPF-controle niet in orde
blijkt te zijn. Deze kunnen bijvoorbeeld weggegooid worden of apart worden
gezet.

De aanwijzing wordt via het [DNS-systeem](/faqs/dnssec/#DNS) online
gepubliceerd. Deze kan bovendien een e-mail adres bevatten waarop
brievenbussen afgewezen berichten kunnen rapporteren. Zo krijgt de beheerder
van het betreffende mail-domein inzicht in de aflevering van zowel echte als
vervalste berichten.

TODO

## Voor eigenaren van een mail-domein

TODO

## Voor internetgebruikers

TODO

## Meer informatie

- CIP white paper "[E-mailauthenticatie](http://www.cip-overheid.nl/wp-content/uploads/2014/06/20140528_Emailauthenticatie_def.pdf)"
- M3AAWG publicatie "[Trust in Email Begins with Authentication](https://www.m3aawg.org/sites/maawg/files/news/M3AAWG_Email_Authentication_Update-2015.pdf)"
- M3AAWG publicatie "[Protecting Parked Domains Best Common Practices](https://www.m3aawg.org/sites/maawg/files/news/M3AAWG_Parked_Domains_BP-2015-02.pdf)"
- [Mailman and DMARC](http://wiki.list.org/DEV/DMARC)
- Virus Bulletin: [Using DMARC to improve your email reputation](https://www.virusbtn.com/virusbulletin/archive/2014/11/vb201411-DMARC)
- [DKIM](http://www.dkim.org/), [SPF](http://www.openspf.org/) en
  [DMARC](http://dmarc.org/)
- [DKIM op 'pas toe of leg uit'-lijst van Forum Standaardisatie](https://lijsten.forumstandaardisatie.nl/open-standaard/dkim)
