# Internetstandaarden

Het [Platform Internetstandaarden](/about/) promoot in eerste instantie zes
moderne standaarden voor schaalbaar en veilig internetgebruik:

- [IPv6](#ipv6): een uitgebreide, moderne reeks internetadressen
- [DNSSEC](#dnssec): beveiligingsuitbreidingen voor domeinnamen
- [TLS](#tls): beveiligde verbindingen
- [DKIM, SPF en DMARC](#dkim-spf-en-dmarc): anti-phishing en anti-spoofing

Al deze internetstandaarden zijn volwassen en breed beschikbaar. Het gebruik
ervan levert een belangrijke bijdrage aan de betrouwbaarheid van het
Nederlandse Internet.

[IPv6](/faqs/ipv6/), [DNSSEC](/faqs/dnssec/), [TLS](/faqs/tls/) en
[DKIM](/faqs/mail/#DKIM) staan al jaren op de
[&#39;pas toe of leg uit&#39;-lijst](https://www.forumstandaardisatie.nl/ptolu)
van het [Forum Standaardisatie](/partners/#FS). De standaarden op deze lijst
zijn verplicht gesteld voor Nederlandse overheidsorganisaties.

IPv6 werd tot eind 2014 apart gestimuleerd door de
[IPv6 Task Force](https://ecp.nl/ipv6-task-force), ondergebracht bij
[ECP](/partners/#ECP). De Task Force wordt straks onderdeel van het Platform
Internetstandaarden.

[SIDN](/partners/#SIDN), de beheerder van het .nl-domein, stimuleert het
gebruik van [DNSSEC](http://dnssec.nl/).

## IPv6

Het Internet Protocol (IP) vormt de basis onder al het verkeer op Internet.
Onder de huidige standaard, IP version 4 (IPv4), krijgen alle computers een
adres bestaande uit vier getallen, bijvoorbeeld 192.0.2.26. Op die manier zijn
alle computers die op Internet zijn aangesloten bereikbaar vanaf elke andere
computer.

IPv4 is inmiddels 35 jaar oud en loopt tegen zijn grenzen aan. Het grootste
probleem is dat deze standaard maximaal vier miljard IP-adressen ondersteunt.
Dat lijkt heel veel, maar dat is het niet als je bedenkt dat we inmiddels met
zeven miljard mensen zijn en elk van onze apparaten &mdash; desktops, laptops,
mobiele apparatuur, webcams, thermostaten &mdash; een eigen IP-adres nodig
heeft.

IP versie 6 (IPv6), de opvolger van IPv4, lost het adrestekort op. IPv6 is
inmiddels meer dan vijftien jaar oud maar nog niet op grote schaal ingevoerd.
Probleem is dat de meeste providers en bedrijven op dit moment nog geen IPv6
aanbieden voor hun klanten en gebruikers. Belangrijk doel van deze site is om
hier verandering in te brengen.

Meer informatie over IPv6 staat in de
&quot;[veelgestelde vragen](/faqs/ipv6/)&quot;.

## DNSSEC

DNSSEC is een beveiligingssysteem voor [DNS](/faqs/dnssec/#DNS), het
internet-telefoonboek dat zorgt voor de vertaling van
[domeinnamen](/faqs/dnssec/#domeinnaam) naar
[IP-adressen](/faqs/ipv6/#IPadres). Op zich werkt DNS prima, maar de vertaling
van domeinnaam naar IP-adres is niet beveiligd. Dat is een risico, want een
kwaadwillende kan verkeer van een gebruiker omleiden naar een vals IP-adres.
Op die manier zou hij wachtwoorden of andere gevoelige informatie kunnen
buitmaken.

DNSSEC breidt DNS uit met een extra beveiliging: de vertaling van domeinnaam
naar IP-adres wordt voorzien van een digitale handtekening. Een
internetgebruiker kan die handtekening automatisch laten controleren. Op die
manier voorkomt hij dat hij misleidt wordt naar een vals IP-adres.

Meer informatie over DNSSEC staat in de
&quot;[veelgestelde vragen](/faqs/dnssec/)&quot;.

## TLS

TLS is een standaard voor de cryptografische beveiliging van
internetverbindingen. De meeste gebruikers kennen TLS, en zijn voorloper SSL,
uit hun webbrowser: door het &#39;https&#39;-protocol te specificeren in een
internet-bestemming &mdash; bijvoorbeeld https://www.example.nl/ &mdash; geeft
een internetgebruiker aan een website te willen bezoeken over een beveiligde
verbinding. Het &quot;hangslotje&quot; in de browser laat zien dat dat ook
gelukt is en geeft eventueel meer informatie over de gebruikte beveiliging.

Om TLS veilig te kunnen gebruiken moet deze niet alleen aan staan maar ook
goed ingesteld zijn. Het gebruik van oude versies en verouderde instellingen
kan maken dat een TLS-verbinding toch onveilig is. Het Nationaal Cyber
Security Centrum ([NCSC](/partners/#NCSC)) heeft een richtlijn gepubliceerd om
TLS goed en dus veilig te gebruiken. Deze richtlijn fungeert als leidraad voor
de informatie en de tests op deze site.

Meer informatie over TLS staat in de
&quot;[veelgestelde vragen](/faqs/tls/)&quot;.

## DKIM, SPF en DMARC

DKIM, SPF en DMARC zijn drie internetstandaarden voor het terugdringen van
phishing, spam, virussen en andere narigheid die per [e-mail](/faqs/mail/)
bezorgd wordt. Deze drie standaarden worden meestal gezamenlijk ingezet om te
controleren dat de afzender (een mail-adres) en de verzender (een
computersysteem) van een mail-bericht inderdaad kloppen, en dat de inhoud van
het bericht onderweg niet is veranderd.

Alle drie standaarden gebruiken het [DNS-systeem](/faqs/dnssec/#DNS) om
informatie online te publiceren. Volgens de standaarden is het niet
noodzakelijk om daarbij ook [DNSSEC](/faqs/dnssec/) te gebruiken &mdash; een
beveiligingssysteem voor DNS &mdash; maar dat willen we hier toch van harte
aanraden.

### DKIM

DKIM zorgt voor de beveiliging van mail-berichten. Daarvoor wordt de inhoud en
de &quot;envelope&quot; van elk uitgaand bericht van een digitale handtekening
voorzien. Zo wordt voorkomen dat kwaadwillenden een bericht namens een ander
kunnen verzenden (spoofing) of de inhoud van een bericht onderweg kunnen
veranderen.

### SPF

SPF voorkomt dat &quot;elektronische brievenbussen&quot; mail-berichten
accepteren van ongeauthoriseerde computersystemen. Alleen berichten van
systemen die daadwerkelijk berichten voor een specifiek
[domein](/faqs/dnssec/#domeinnaam) mogen versturen komen er doorheen. Daarvoor
wordt een lijst van geldige verzenders via het
[DNS-systeem](/faqs/dnssec/#DNS) online gepubliceerd. Ontvangende systemen
kunnen deze lijst gebruiken om de verzender te controleren voor zij een
bericht aannemen.

### DMARC

DMARC is een aanvulling op de andere twee beveiligingsstandaarden voor
[e-mail](/faqs/mail/), [DKIM](/faqs/mail/#dkim) en [SPF](/faqs/mail/#spf).
DMARC geeft &quot;elektronische brievenbussen&quot; een aanwijzing hoe om te
gaan met inkomende berichten waarvan de DKIM- of SPF-controle niet in orde
blijkt te zijn. Deze kunnen bijvoorbeeld weggegooid worden of apart worden
gezet.

De aanwijzing wordt via het [DNS-systeem](/faqs/dnssec/#DNS) online
gepubliceerd. Deze kan bovendien een e-mail adres bevatten waarop
brievenbussen afgewezen berichten kunnen rapporteren. Zo krijgt de beheerder
van het betreffende mail-domein inzicht in de aflevering van zowel echte als
vervalste berichten.

Meer informatie over DKIM, SPF en DMARC staat in de
&quot;[veelgestelde vragen](/faqs/mail/)&quot;.
