# I. Algemeen

## Wat is IP?
Het Internet Protocol (IP) vormt de basis onder al het verkeer op Internet. Ieder apparaat dat met het internet is verbonden, heeft een uniek numeriek adres namelijk het IP-adres.

Er bestaan twee versie van het Internet Protocol: versie 4 (IPv4) en versie 6 (IPv6). Deze versies zijn niet compatibel met elkaar. Dit betekent dat een computer met een IPv4-adres niet kan communiceren met een computer die alleen een IPv6-adres heeft. Wel kunnen ze naast elkaar worden gebruikt. Veel apparaten bieden inmiddels ondersteuning voor zowel IPv4 als IPv6. IPv6 zal uiteindelijk IPv4 volledig vervangen. In de tussentijd kunnen IPv4 en IPv6 gewoon naast elkaar gebruikt worden. Bijna alle apparatuur ondersteunt inmiddels zowel IPv4 als IPv6.

## Wat is IPv4?
De IPv4-standaard dateert van 1981. Een voorbeeld van een IPv4-adres is `94.198.159.35`. IPv4 kent een zogenaamde adresruimte van 32 bits. Dit betekent dat er op basis van het IPv4 protocol wereldwijd ruim 4 x 10^9 (4 miljard) unieke IP-adressen kunnen worden uitgegeven. Dat lijkt heel veel, maar dat is het niet. Bedenk maar eens dat er inmiddels ruim 7 miljard mensen op aarde zijn, en dat een groot deel van deze mensen steeds meer apparaten gebruiken die een verbinding met het internet nodig hebben.

## Wat is IPv6?
IPv6-standaard dateert van 1998 en is de opvolger van het oude IPv4. Een voorbeeld van een IPv6-adres is `2a00:d78:0:712:94:198:159:35`. IPv6 kent een adresruimte van 128 bits en dat betekent dat er veel meer unieke IP-adressen beschikbaar zijn: 3,4 x 10^38 (een 3 met 38 nullen) tegenover de 4 x 10^9 (een 4 met 9 nullen).

## Waarom IPv6?

* Kosten: IPv6-adressen zijn kosteloos beschikbaar. Voor IPv4-adressen moet ondertussen steeds meer worden betaald. Dit zorgt voor een toetredingsdrempel voor nieuwe (innovatieve) dienstaanbieders. Denk aan een nieuwe internetprovider die om te beginnen veel IPv4-adressen nodig heeft.
* 'End-to-end'-connectiviteit: Met IPv6 kan ieder apparaat, en daarmee iedere gebruiker, op internet over een eigen adres beschikken. Dit in tegenstelling tot IPv4 waar schaarste providers dwingt om zuinig met deze adressen om te gaan. Gebruikers delen hierdoor vaak één IPv4-adres met elkaar. Met IPv6 kunnen diensten die 'end-to-end'-connectiviteit vereisen makkelijker worden geleverd, omdat gebruikers over een eigen IPv6-adres kunnen beschikken.
* Snelheid: Uit [ervaringen van o.a. Facebook en LinkedIn ](https://blog.apnic.net/2016/08/15/optimized-content-providers-connect-faster-ipv6/) blijkt dat het delen van IPv4-adressen ook ten koste gaat van de snelheid.

## Hoe staat het met de adoptie van IPv6?
Wereldwijd is IPv6 bezig met een flinke opmars. Het aantal servers en ook eindgebruikers groeit al jaren bijna exponentieel. Grote partijen zoals Google, Facebook en XS4ALL zien de voordelen en kiezen voor IPv6. Nederland loopt helaas achter bij veel andere vergelijkbare landen, zeker als het gaat om eindgebruikers die over IPv6-connectiviteit beschikken. Landen als Duitsland en België doen het bijvoorbeeld veel beter.

Statistieken van IPv6-adoptie:
* [APNIC IPv6 Measurements](https://stats.labs.apnic.net/ipv6/)
* [World IPv6 Launch](http://www.worldipv6launch.org/measurements/)
* [Akamai IPv6 adoption](https://www.akamai.com/us/en/about/our-thinking/state-of-the-internet-report/state-of-the-internet-ipv6-adoption-visualization.jsp)
* [Google IPv6 statistics](https://www.google.com/intl/en/ipv6/statistics.html)
* [Cisco IPv6 statistics](http://6lab.cisco.com/stats/)


## Bestaat er ook een IP versie 5 (IPv5)?
IPv5 is ooit bedacht als een standaard voor internettelefonie. IPv5 is niet verder gekomen dan het experimentele stadium en nooit daadwerkelijk gebruikt.


# II. Voor eigenaren/beheerders
## Aandachtspunten e-mailserver op IPv6
Verschillende e-mailproviders (Gmail, Office 365) stellen de volgende twee eisen aan IPv6 ontvangen e-mail:
* Een mailserver op IPv6 vereist het gebruik van een reverse DNS opvraagbaar PTR-record. Google vereist daarnaast dat dit IPv6 adres (wat is vastgelegd in het PTR-record) overeenkomt met het IPv6 adres wat wordt verkregen via de normale omzetting van de PTR DNS-naam naar een IPv6 adres. Dit wordt "forward-confirmed reverse DNS" genoemd.
* Via een IPv6 mailserver verzonden e-mail moet óf de SPF-controle (“mag dit IP-adres mailen voor dit afzenderdomein?”) óf de DKIM-controle (“is deze mail ondertekend met de geldige digitale handtekening van dit afzenderdomein?”) succesvol doorstaan.

## Aandachtspunten implementatie
https://www.surf.nl/binaries/content/assets/surf/nl/kennisbank/2011/rapport_201102_IPv6_Case_Study_Leidraad_voor_de_invoering_van_IPv6_in_organisaties-1.pdf

https://kpnlokaleoverheid.nl/wp-content/uploads/2009/03/Whitepaper-IPv6-versie-1-5-26-06-2013.pdf

# III. Voor bezoekers/gebruikers.
## Hoe kom ik aan een IPV6 adres?
## Hoe weet ik of een domein over IPv6 communiceert.

# Interessante bronnen
* Pas toe of leg uit-lijst
* Deze eisen zijn gebaseerd op de best practice 'Policy Issues for Receiving Email in a World with IPv6 Hosts' van M³AAWG: https://www.m3aawg.org/sites/default/files/document/M3AAWG_Inbound_IPv6_Policy_Issues-2014-09.pdf
