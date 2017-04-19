## Aanvullende eisen voor IPv6
Vergeleken met mail die via IPv4 binnenkomt, stellen verschillende (grote) mailproviders extra eisen aan mail die ze over IPv6 ontvangen. Deze aanvullende eisen zorgen ervoor dat de mailproviders kunnen filteren op basis van domeinnaamreputatie in plaats van of naast IP-adresreputatie. Daardoor kunnen ze over IPv6 verstuurde spam en phishing mail beter tegengaan. Bij Gmail staat IPv6-ontvangst overigens standaard aan. Bij Office365 kan Microsoft het nu op verzoek van de klant aanzetten.

### Meer IP-adressen dan ooit
Dankzij IPv6 is er een bijna onuitputtelijke voorraad IP-adressen bijgekomen. Dat betekent ook dat er veel meer IP-adressen zijn waarvandaan internetcriminelen spam en phishing mails kunnen versturen. Daardoor heeft het werken met zwarte lijsten ('black lists') – zoals we gewend zijn met IPv4 – bij IPv6-adressen minder zin. We illustreren dit met het volgende voorbeeld.

### Voorbeeld: blacklisting werkt minder goed
Stel dat er spam vanaf jouw thuis-aansluiting komt (omdat je besmet bent met een spam botnet zoals Cutwail), dan kan een mailprovider je IPv4-adres snel op een blacklist zetten. Mocht het je nog lukken om een ander IPv4-adres te krijgen, dan wordt dat ook geblacklist. Maar heb je thuis IPv6, dan heb je meestal een subnet met heel veel IPv6-adressen. De spambot kan dan vrijwel eindeloos van adres wisselen en dat jaren volhouden, want in een IPv6-subnet van /64 zitten 18.446.744.073.709.551.616 adressen. Hoewel het mogelijk is om een subnet op een blacklist te zetten, is het niet altijd duidelijk hoe groot een individueel subnet is. De blokkade van een subnet kan al snel als negatief bijeffect hebben dat anderen onbedoeld ook gehinderd worden.

### Koppeling e-mail en domeinaam
Wat is de oplossing? Mailproviders, zoals [Gmail](https://support.google.com/mail/answer/81126?hl=nl#authentication) en [MS Office365](https://technet.microsoft.com/en-us/library/dn720852(v=exchg.150).aspx), willen een via IPv6 ontvangen e-mail ook aan een domeinnaam kunnen koppelen – en niet alleen aan een IPv6-adres. Zo nodig kunnen ze dan e-mails vanaf een bepaalde domeinnaam filteren. De mailproviders stellen de volgende twee eisen die zijn gebaseerd op de best practice ['Policy Issues for Receiving Email in a World with IPv6 Hosts'](https://www.m3aawg.org/sites/default/files/document/M3AAWG_Inbound_IPv6_Policy_Issues-2014-09.pdf) van M³AAWG :

**1. E-mailauthenticatie**
De verzonden mail moet óf de SPF-controle (“mag dit IP-adres mailen voor dit afzenderdomein?”) óf de DKIM-controle (“is deze mail ondertekend met de geldige digitale handtekening van dit afzenderdomein?”) succesvol doorstaan.

**2. Reverse DNS**
Het IPv6-adres van de verzendende mailserver moet een via reverse DNS opvraagbare PTR-record (d.w.z. domeinnaam) hebben. Gmail vereist aanvullend dat dit IPv6-adres overeenkomt met het IPv6-adres dat kan worden verkregen via normale (voorwaartse) DNS-omzetting van de domeinnaam uit de PTR-record (d.w.z. Forward-confirmed reverse DNS).

## Wat kan je doen?

### Mail via provider
Bent je klant bij een e-mailprovider die IPv6 ondersteunt, dan kun je te maken hebben met deze ‘best practice’. Wanneer een verzendende partij die IPv6 gebruikt zijn SPF-, DKIM-, rDNS-instellingen niet op orde heeft, dan kan het gebeuren dat je geen e-mails meer van deze partij ontvangt. De kans daarop is echter niet heel groot. Verzenders die via IPv6 versturen, zijn doorgaans op de hoogte van de ‘best practice’ en passen deze toe. Gaat het toch mis met bepaalde inkomende mails over IPv6? Wijs de verzendende partij dan op de beschreven 'best practice'.

### Mail via eigen mailserver
Als je IPv6 aanzet voor mail en zelf je mailservers draait, dan is er weinig aan de hand qua inkomende mail. Het is uiteraard ook dan verstandig om controles op e-mailauthenticatie en eventueel aanvullend reverse DNS uit te voeren om spam en phishing  te voorkomen. Omdat je zelf aan de knoppen zit, kun je meteen zien wanneer een mail die je via IPv6 ontvangt niet door de controles komt. Voor uitgaande mail is het aan te raden om je mailservers conform bovengenoemde ‘best practice’  in te richten. Anders loop je het risico dat jouw mails over IPv6 niet aankomen.

### Gebruik je alleen IPv4 en nog geen IPv6?
Ook in het geval van IPv4 is het van belang om in ieder geval e-mailauthenticatie (SPF, DKIM en aanvullend DMARC) op orde te hebben. Deze standaarden helpen ook bij IPv4 om spam en phishing te voorkomen en de afleveringszekerheid van je mail te vergroten.
Bovendien toont [Gmail](https://support.google.com/mail/answer/180707?hl=nl) sinds enige tijd aan de gebruiker een vraagteken naast de naam van de afzender als zowel de SPF- als DKIM-check hebben gefaald, ook bij mail over IPv4. En zo'n vraagteken bij je afzendernaam dat wil toch niemand?
Zorg er daarnaast voor dat je snel ook via een modern IPv6-adres mailt.

### Test via Internet.nl
In de mailtest op [Internet.nl](/) kan je eenvoudig testen of je mail via IPv6 kan ontvangen en of je voor uitgaande mail SPF-, DKIM-, en DMARC-records hebt gepubliceerd.
