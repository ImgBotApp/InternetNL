De onderstaande verbeteringen zijn doorgevoerd op Internet.nl.
## Generiek
* De mogelijkheid om voor een andere taal te kiezen via een dropdown-menu. Bezoekers krijgen dan de equivalente pagina in de gekozen taal (als die beschikbaar is).
* De eis dat alle nameservers via IPv6 beschikbaar moeten zijn is komen te vervallen. Het is voldoende als er tenminste evenveel nameservers via IPv6 als via IPv4 beschikbaar zijn. Dit geldt voor de webite- én de mailtest.

## Verbindingtest
* De detectie van een internetprovider is nauwkeuriger en heeft minder vaak time-outs.

## Websitetest
* De test checkt of er een HSTS-policy aanwezig is. Door HSTS 'weet' een webbrowser na het eerste bezoek dat een website alleen via een beveiligde verbinding (HTTPS en niet HTTP) bezocht mag worden. Dit kan zogeheten man-in-the-middle-aanvallen voorkomen, zoals bij het gebruik van publieke WiFi. Bij afwijkingen is de melding niet langer 'oranje' maar 'rood'.
* In de test telt nu mee of de website HTTPS afdwingt door een server redirect (301 of 302) of door alleen HTTPS (en geen HTTP) toe te passen. Bij afwijkingen is de melding niet langer 'oranje' maar 'rood'.
* De TLS-resultaten gaven bij een aantal sites onterecht de melding dat 'client-initiated renegotiation' was toegestaan. Dit is opgelost.
* Bij websites met een redirect van IPv6/IPv4 naar IPv4-only werd de HSTS-policy over IPv6 onterecht niet gedetecteerd. Dit is opgelost.
* De test controleert nu of er daadwerkelijk HTTP-verkeer over poort 443 gaat. Als dat niet het geval is, trekt de test niet langer onterechte HTTPS-gerelateerde conclusies.

## Mailtest
* Als Internet.nl (o.a. door 'rate limiting') geen verbinding kan opzetten met een mailserver, dan krijgen bezoekers nu de suggestie het later nog eens te proberen.
* Dankzij het beter afstellen van timeouts voor het testonderdeel STARTTLS, faalt de test minder snel en kunnen bepaalde mailservers nu ook zonder probleem getest worden.
* Het serieel uitvoeren en minimaliseren van het aantal connecties moet helpen om het risico op 'rate limiting' van mailservers te verminderen. Daardoor kunnen bepaalde mailservers nu ook getest worden waarvoor dat eerder onmogelijk was. 

## Achtergrondinformatie
* [ICT-beveiligingsrichtlijnen voor webapplicaties van NCSC - Verdieping](https://www.ncsc.nl/binaries/content/documents/ncsc-nl/actueel/whitepapers/ict-beveiligingsrichtlijnen-voor-webapplicaties/4/ICT%2BBeveiligingsrichtlijnen%2Bvoor%2BWebapplicaties%2B%2B%2BVerdieping%2B%2B%2BPrintversie.pdf) onder '05 Versleutel communicatie' op p.29;
* [ICT-beveiligingsrichtlijnen voor TLS van NCSC](https://www.ncsc.nl/actueel/whitepapers/ict-beveiligingsrichtlijnen-voor-transport-layer-security-tls.html);
