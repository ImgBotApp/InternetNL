## I. Algemeen

### Wat doet HTTPS?
Als een bezoeker een onbeveiligde HTTP-verbinding heeft met een website, dan kan een kwaadwillende eenvoudig gegevens onderweg afluisteren of aanpassen, of zelfs het contact volledig overnemen. Bij HTTPS is TLS (opvolger van SSL) toegevoegd aan HTTP om de verbinding te beveiligen. HTTPS werkt tussen de webclient (vaak een browser) van de bezoeker en de webserver van de aanbieder van de website of webservice.

Mits veilig geconfigureerd, zorgt HTTPS voor de volgende drie beveiligingsaspecten.

* **Vertrouwelijkheid**: De verbinding tussen de bezoeker en de website is versleuteld waardoor het onmogelijk is voor kwaadwillenden om de webcontent, URL's, cookies en andere gevoelige (meta)data onderweg af te luisteren.
* **Authenticiteit**: De bezoeker kan controleren of hij/zij direct met de website die hoort bij de gebruikte domeinnaam contact heeft, en niet met een vervalste website of via een kwaadwillende tussenpersoon ('man-in-the-middle').
* **Integriteit**: Een kwaadwillende kan de gegevens tussen de bezoeker en de website onderweg niet aanpassen of zaken (bijv. malware) toevoegen.

## Biedt HTTPS nog andere voordelen?
* Het gebruik van HTTPS biedt ook SEO-voordelen. SEO staat voor Search Engine Optimization en is een verzamelnaam voor verschillende methoden en technieken die een website optimaal vindbaar binnen zoekmachines. Een betere vindbaarheid betekent immers meer (relevante) bezoekers. Bij Google is het bijvoorbeeld zo dat websites die worden aangeboden op basis van HTTPS, hoger in de ranglijst staan dan soortgelijke HTTP varianten.
* Eventuele discussies over het feit dat HTTPS websites (te) traag maakt, behoren met HTTP/2 definitief tot het verleden. HTTP/2 biedt vele voordelen ten opzicht van het huidige HTTP/1.1, waaronder een zeer snelle laadtijd en een verbeterde beveiliging. De snelheid van het inladen van een webpagina over HTTP/2 met TLS is, afhankelijk van de inhoud, vele malen sneller dan over HTTP/1.1 zonder TLS (zie [hier](https://www.httpvshttps.com/) en [hier](https://http2.akamai.com/demo)). Daarnaast valt op dat hoewel het vanuit de specificatie van HTTP/2 niet verplicht is, browserfabrikanten er massaal voor kiezen om HTTP/2 alleen te ondersteunen in combinatie met TLS. Dit is goed nieuws voor het gebruik van HTTPS dat op deze manier hopelijk de nieuwe standaard wordt.

### Moet je HTTPS doen voor alle websites?
Op voorhand is vaak niet te voorspellen hoe informatie wordt gebruikt en welke waarde de informatie voor de afnemer heeft. Daarom is het gebruik van HTTPS in alle gevallen verstandig. Bij inlog- en medische gegevens is dat evident, maar er zijn ook situaties waarin bijvoorbeeld openbare informatie van cruciaal belang is. Denk bijvoorbeeld aan de agrarische sector waar besluiten worden genomen op basis van weersverwachtingen, of aan transportbedrijven die afhankelijk zijn van actuele verkeersinformatie. Ook bij het gebruik van publieke (en vaak open) Wi-Fi netwerken biedt HTTPS noodzakelijke bescherming om misbruik te voorkomen.

### Hoe werkt HTTPS?
Voor het tot stand brengen van een beveiligde verbinding maakt de webclient gebruik van een certificaat dat wordt aangeboden door de webserver, en is uitgegeven door een vertrouwde certificaatinstantie. Dit certificaat bevat een zogenaamde publieke sleutel en wordt samen met de bijhorende privésleutel op de webserver, gebruikt voor het veilig uitwisselen van een sessiesleutel. Deze sessiesleutel wordt vervolgens gebruikt voor de daadwerkelijke versleuteling van de verbinding tussen de webclient en de webserver.

### Waarom is het belangrijk om HTTPS veilig in te stellen?
Onder de oppervlakte kan voor het toepassen van een versleutelde HTTPS verbinding, gebruik worden gemaakt van verschillende versies van het TLS- of SSL-protocol en verschillende onderliggende versleutelingsstandaarden (ciphers). Aangezien niet alle versies en combinaties als voldoende veilig worden beschouwd, is het belangrijk om hierin de juiste keuze te maken en ook regelmatig te controleren of de gebruikte instellingen nog veilig zijn. Een foutieve toepassing van HTTPS kan immers net zo onveilig zijn als het gebruik van HTTP zonder TLS.

## II. Voor eigenaren/beheerder van websites

### Maakt HTTPS mijn website trager?
De toevoeging van TLS aan HTTP zorgt ervoor dat er meer data wordt verzonden tussen de client en de server. Ook kan de belasting van zowel de server als de client als gevolg van HTTPS toenemen vanwege de cryptografische berekeningen. Aan de serverkant is dit bij kleinere websites en IT omgevingen te verwaarlozen, maar in het geval van grote en complexe IT omgevingen kan deze impact aanzienlijk zijn. Ondanks het feit dat servers steeds krachtiger worden, komt het nog steeds voor dat er specialistische apparatuur wordt gebruikt om de serverbelasting van TLS te verplaatsen (ook wel 'offloaden' en/of 'onloaden' genoemd) van een (web)server naar een hiervoor geoptimaliseerd apparaat. 

Zoals eerder beschreven op deze pagina, biedt het gebruik van HTTP/2 verschillende voordelen voor de snelheid waarmee websites over HTTPS worden geladen in browsers (client zijde). 

### Hoe kan ik HTTPS implementeren?
Voor het toepassen van HTTPS in de praktijk, kunnen (afhankelijk van de context) de volgende stappen worden gezet:

1. Inventariseer alle domeinen en stel vast (op basis van een classificatie van de verwerkte gegevens) voor welke domeinen HTTPS strikt noodzakelijk is. Overweeg daarnaast om alle domeinen van een HTTPS verbinding te voorzien.
2. Schaf een certificaat aan bij een certificaat autoriteit en installeer dit certificaat op het onderliggende systeem. Houd hierbij rekening met:
a. Het type certificaat. Extended Validation (EV) certificaten bieden de meeste zekerheid over de identiteit van de eigenaar van het domein, maar zijn wel duurder dan andere certificaten die minder zekerheid bieden: Organisation Validation (OV) en Domain Validation (DV) certificaten.
b. Eventueel te specificeren Subject Alternate Names.
c. Gebruik minimaal het SHA-256 hash algoritme voor de vingerafdruk van het certificaat. Oudere hash algoritmes (MD5 en SHA-1) bevatten kwetsbaarheden waardoor vingerafdrukken op basis van deze algoritmes niet betrouwbaar zijn.
d. Veilig beheer van certificaten om de kans op incidenten te verkleinen (bijvoorbeeld gestolen of vervalste certificaten), en de schade te beperken in het geval van een incident.
3. Gebruik een recente versie van de software die TLS implementeert, bijv. OpenSSL of LibreSSL.
4. Configureer veilige TLS instellingen waaronder
a. een recente versie van het TLS protocol (bijvoorbeeld TLS 1.2)
b. betrouwbare versleutelingsalgorimen
5. Gebruik aanvullende standaarden om op HTTPS gerichte aanvallen te kunnen weerstaan. Bijvoorbeeld HSTS, DANE en HPKP.
6. Testen of HTTPS conform bovenstaande eisen is geïnstalleerd (onder andere met Internet.nl)
7. Pas, indien nodig, de inhoud van de website aan zodat er geen content van andere websites wordt geladen over een onbeveiligde HTTP verbinding. Dit voorkomt mixed content foutmeldingen.
8. Pas na zorgvuldige testprocedure toe in productie.
9. Controleer regelmatig of er nog steeds gebruik wordt gemaakt van geadviseerde beveiligingsstandaarden.

### Aandachtspunten implementatie
* Let bij gebruik van HSTS goed op de redirect volgorde. Wanneer er gebruik wordt gemaakt van redirects om het gebruik van HTTPS te forceren én bezoekers door te verwijzen naar een ander (sub)domein, hanteer dan deze volgorde: redirect eerst naar HTTPS, en pas daarna naar een ander (sub)domein. Dus http://example.nl -> https://example.nl -> https://www.example.nl.
* Vergeet niet om de DANE TLSA records in je DNS-zone voorafgaand aan het ingebruik nemen van een nieuwe certificaat aan te passen.
* Wees voorzichtig met de implementatie van aanvullende standaarden die voor een goede werking afhankelijk zijn van caching aan de zijde van de client (HSTS, HPKP). Test dit eerst zorgvuldig, want fouten zijn mogelijk niet (makkelijk) te herstellen.
* Kijk uit met het gebruik van certificaten op meerdere plaatsen. Voorkom dat certificaten in meerdere type omgevingen (OTAP) worden gebruikt. Dit verkleint de impact op het vervangen van een certificaat.

## III. Voor bezoekers van websites

### Hoe kan ik zien of een website HTTPS doet?
Het gebruik van HTTPS is doorgaans te herkennen aan het slotje in de browser. Voer de website test op Internet.nl uit om het zeker te weten.

### Aandachtspunten gebruik
* Aanvullende standaarden die afhankelijk zijn van caching bij de webclient (HSTS, HPKP) verliezen hun werking wanneer de webbrowser is ingesteld in de privémodus, of wanneer de browser geschiedenis wordt gewist. Dit geldt ook voor organisaties die medewerkers iedere dag van een “schone” installatie van hun werkplek voorzien.

## Meer informatie
* [ICT-beveiligingsrichtlijnen voor Webapplicaties (NCSC)](https://www.ncsc.nl/actueel/whitepapers/ict-beveiligingsrichtlijnen-voor-webapplicaties.html)
* [ICT-beveiligingsrichtlijnen voor TLS (NCSC)](https://www.ncsc.nl/actueel/whitepapers/ict-beveiligingsrichtlijnen-voor-transport-layer-security-tls.html)
* [Factsheet Veilig beheer van digitale certificaten (NCSC)](https://www.ncsc.nl/actueel/factsheets/factsheet-veilig-beheer-van-digitale-certificaten.html)
* [Factsheet TLS (IBD Gemeenten)](https://www.ibdgemeenten.nl/3619-2/)
* [Still think you don't need HTTPS? (Scott Helme)](https://scotthelme.co.uk/still-think-you-dont-need-https/)
