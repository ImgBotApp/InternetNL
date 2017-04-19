De meest in het oog springende verbeteringen staan hieronder. 

1. De vorige versie van Internet.nl testte de veiligheid van de HTTPS-configuratie over IPv6 óf over IPv4. Omdat we via handmatig testen regelmatig websites tegen zijn gekomen die onbedoeld verschillende HTTPS-configuraties over IPv6 en IPv4 hanteren, wordt vanaf nu de **HTTPS-configuratie zowel over IPV6 als over IPv4** getest.  Het resultaat van dit uitgebreide testonderdeel weegt **vanaf nu** mee in de score van de websitetest.
2. Voor websites wordt nu ook getest of er een **HSTS-policy** aanwezig is. HSTS zorgt ervoor dat een webbrowser na het eerste bezoek weet dat een website alleen over HTTPS bezocht mag worden. Hiermee kunnen zogeheten man-in-the-middle-aanvallen (bijvoorbeeld als gebruik wordt gemaakt van een publieke wifi-hotspot) worden voorkomen. Het resultaat van dit nieuwe testonderdeel komt nu bij afwijking terug als oranje waarschuwing en telt nog niet mee in de score van de websitetest. **Vanaf juli 2016** weegt het resultaat wel mee in de score.
3. De website-test controleert nu ook of door websites **HTTPS afgedwongen** wordt. Het afdwingen kan op de twee onderstaande manieren. Het resultaat van dit nieuwe testonderdeel komt bij afwijking terug als oranje waarschuwing en telt nog niet mee in de score van de websitetest. **Vanaf juli 2016** weegt het resultaat wel mee in de score.
    1. Door HTTP naar HTTPS te 'redirecten'. Dat kan door `http://example.nl` naar `https://example.nl` te laten verwijzen. Het is belangrijk dat het identieke domeinen zijn omdat een webbrowser alleen een HSTS-policy voor een bepaalde domeinnaam accepteert over een HTTPS-verbinding. Als `http://example.nl` doorverwijst naar `https://www.example.nl` dan zal de HSTS-policy bij normaal gebruik niet voor `example.nl` in de browser worden opgeslagen, tenzij een gebruiker bewust `https://example.nl` intoetst of hierop als link klikt.
    2. Door alleen HTTPS en geen HTTP te ondersteunen. Doordat een browser normaal gesproken bij het intoetsen van een domeinnaam een HTTP-verbinding opzet moeten gebruikers bewust `https://example.nl` intoetsen om de website te bereiken of daarop als link klikken.
4. De websitetest controleert in de nieuwe versie of er sprake is van **HTTP-compressie**. Het inschakelen van HTTP-compressie maakt veel websites kwetsbaar voor de BREACH-aanvalstechniek als geen andere mitigerende maatregelen zijn genomen. Het uitschakelen van HTTP-compressie kan een negatieve invloed hebben op de prestaties van het systeem. Indien HTTP-compressie wordt gedetecteerd dan wordt dat vermeld als **oranje waarschuwing** .
5. De websitetest van de vorige versie van Internet.nl controleerde al of de **content van een website gelijk is over IPv6 en IPv4**. Dit testonderdeel hield ook al rekening met kleine terechte verschillen zoals bijvoorbeeld vanwege verschillende advertenties. Het resultaat van dit testonderdeel weegt **vanaf nu** mee in de score van de websitetest.
6. Als een gebruiker een **niet-bestaande domeinnaam** intoetst dan wordt een rode foutmelding gegeven.


***

**Meer informatie:**

* [ICT-Beveiligingsrichtlijnen voor Webapplicaties van NCSC](https://www.ncsc.nl/actueel/whitepapers/ict-beveiligingsrichtlijnen-voor-webapplicaties.html)
* [ICT-beveiligingsrichtlijnen voor Transport Layer Security (TLS)](https://www.ncsc.nl/actueel/whitepapers/ict-beveiligingsrichtlijnen-voor-transport-layer-security-tls.html)
* [RFC 6797: HTTP Strict Transport Security (HSTS)](https://tools.ietf.org/html/rfc6797)
* [Breach Attack](http://breachattack.com/)
