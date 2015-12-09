**Deze pagina is nog onder constructie; deze informatie komt binnenkort
beschikbaar.**

Onderaan deze pagina vind je wel al links naar meer informatie over TLS.

## Algemeen

### Wat is TLS?

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

## TLS-test voor websites
Zie met name de NCSC "[Factsheet HTTPS kan een stuk veiliger](https://www.ncsc.nl/dienstverlening/expertise-advies/kennisdeling/factsheets/factsheet-https-kan-een-stuk-veiliger.html)" 

## TLS-test voor mail

### Hoe werkt TLS voor mailservers (STARTTLS)?

Als je een e-mail verzendt, dan verstuurt de mailserver van jouw mailprovider deze naar de mailserver van de ontvanger. De verbinding tussen de mailservers kan met TLS worden beveiligd. Het gebruikte protocol heet dan STARTTLS. STARTTLS is een manier om een onversleutelde (plain-text) verbinding te upgraden naar een versleutelde TLS-verbinding (i.p.v. een TLS-verbinding over een eigen poort).

Beide mailservers moeten STARTTLS ondersteunen om de versleuteling te laten werken. Afleveringszekerheid is bij e-mail van groot belang. Daarom is het gebruikelijk dat mailservers terugvallen naar een onversleutelde verbinding (ook wel &quot;plain text&quot;) als het opzetten van de versleuteling faalt. Dit mechanisme wordt &quot;opportunistische &quot; versleuteling genoemd.

###Waartegen beschermt STARTTLS?

Versleuteling met STARTTLS beschermt goed tegen afluisteren door een passieve
aanvaller die afluistert zonder het berichtenverkeer te manipuleren.

Een actieve aanvaller die het berichtenverkeer manipuleert, kan
STARTTLS blokkeren (STRIPTLS-aanval) of de versleutelingsterkte verlagen (downgrade-aanval) om de verbinding af te luisteren en e-mails te lezen.


###Hoe zit het met veilige TLS-instellingen bij STARTTLS?
Veel mailproviders ondersteunen naast sterke encryptie ook zwakkere encryptie. Onder anderen Bettercrypto.org en de makers van de veelgebruikte mailserver Postfix hanteren deze lijn. 

Het zorgt er voor dat mailservers minder snel terug vallen naar een onversleutelde verbinding en er tenminste nog iets van versleuteling is. Daarbij geldt wel dat een actieve aanvaller bij STARTTLS de versleuteling sowieso geheel kan blokkeren. 


###Hoe zit het met het valideren van certificaten bij STARTTLS?

Voor STARTTLS moet op de ontvangende mailserver een certificaat worden
geinstalleerd. De ontvangende mailserver voor een domeinnaam is meestal bereikbaar onder een andere domeinnaam. De mail voor @domeinnaam1-adressen wordt dan dus ontvangen op de mailserver met domeinnaam2. De koppeling tussen domeinnaam1 en domeinnaam2 is vastgelegd in de DNS. Een verzendende mailserver weet dus nooit zeker welke domeinnaam hij in het certificaat moet valideren, tenzij de koppeling tussen beide domeinnamen is beveiligd met DNSSEC. Het valideren van een certificaat, zonder DNSSEC, is dus van beperkte waarde. Bovendien rijst de vraag wat de verzendende mailserver moet doen als het certificaat niet valideert (niet versturen, wel versturen over TLS of versturen over 'plain text'?). 

Overigens wordt hetzelfde certificaat op een mailserver vaak ook gebruikt voor de verbinding met e-mailclients. Omdat een e-mailclient het certificaat in de regel zal valideren, zijn de certificaat-kenmerken (zoals of het is uitgegeven door een certificaatautoriteit) in dit geval direct van waarde.

###Wat telt mee in de score op TLS in de mailtest?

In de mail-test checkt Internet.nl of de ontvangende mailserver van een domeinnaam STARTTLS ondersteunt. Als dat het geval is dan krijgt de geteste domeinnaam op dit onderdeel alle punten.

Voor beveiliging van mailtransport is het ook van belang dat een verzendende mailserver STARTTLS ondersteunt. Bovendien is het belangrijk dat de verbinding tussen de e-mailclients van de verzender en ontvanger met hun mailservers is beveiligd met TLS. De mail-test op Internet.nl test deze punten nu niet.


###Tellen TLS-instellingen mee in de score van de mail-test?
Nee, de TLS-instellingen tellen nu niet mee in de score, omdat er voor mail nog geen eenduidige beveiligingsrichtlijn bestaan. 

De mail-test checkt wel of de ontvangende mailserver een aantal TLS-instellingen (namelijk TLS-versies en ciphers) ondersteunt die conform de TLS-richtlijn van NCSC &quot;voldoende&quot; zijn. Als dat het geval is, dan wordt dat vermeld zonder dat dit meetelt in de score. De test checkt niet of een mailserver TLS-instellingen toepast die conform de NCSC-richtlijn &quot;onvoldoende&quot; zijn. 


###Tellen de certificaat-kenmerken mee in de mail-test?
Nee, de certificaat-kenmerken (zoals of het certificaat is uitgegeven door een vertrouwde certificaatautoriteit) tellen nu niet mee in de score, omdat er voor mail nog geen eenduidige beveiligingsrichtlijn bestaan. 

De mail-test geeft wel de resultaten weer van de checks op certificaat-kenmerken. Deze tellen in tegenstelling tot de web-test echter niet mee in de score. De reden daarvoor is dat het valideren van een certificaat bij mail anders werkt dan bij een website.


###Wat is de betekenis van DNSSEC en DANE voor mail?
In de mailtest wordt ook getest op DNSSEC en DANE. Beide kunnen de STARTTLS-beveiliging van mailverbindingen tussen mailservers sterker maken. DNSSEC telt als losse test wel mee in de score. DANE telt niet mee in de score maar het resultaat wordt wel getoond.

Als een verzendende mailserver DNSSEC-validatie toepast, dan kan deze betrouwbaar een met DNSSEC ondertekende domeinnaam van de ontvangende mailserver opvragen. Dit zorgt ervoor dat het valideren van het certificaat van de ontvangende mailserver door de verzendende mailserver daadwerkelijk waarde heeft.

DANE is een techniek die voortbouwt op DNSSEC. Als beide zijden van de verbinding DANE toepassen, is een STRIPTLS-aanval niet meer mogelijk. Het kan daarmee de actieve aanvaller buiten spel zetten. Bovendien kan DANE worden gebruikt als 'trust anchor' voor het gebruikte certificaat. Dit kan naast of in plaats van het 'trust anchor' via een vertrouwde certificaatautoriteit die certificaten uitgeeft binnen een PKI-stelsel.



## Meer informatie

- NCSC publicatie "[ICT-beveiligingsrichtlijnen voor Transport Layer Security (TLS)](https://www.ncsc.nl/dienstverlening/expertise-advies/kennisdeling/whitepapers/ict-beveiligingsrichtlijnen-voor-transport-layer-security-tls.html)"
- NCSC publicatie "[Factsheet HTTPS kan een stuk veiliger](https://www.ncsc.nl/dienstverlening/expertise-advies/kennisdeling/factsheets/factsheet-https-kan-een-stuk-veiliger.html)"
- [TLS bij het ISOC Deploy360 Programma](http://www.internetsociety.org/deploy360/tls/)
- [TLS op 'pas toe of leg uit'-lijst van Forum Standaardisatie](https://lijsten.forumstandaardisatie.nl/open-standaard/tls-0)
