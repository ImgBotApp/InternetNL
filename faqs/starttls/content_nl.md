# I. Algemeen

## Wat is STARTTLS?
TLS (de opvolger van SSL) kan door andere protocollen worden gebruikt voor het opzetten van een versleutelde verbinding. Het SMTP protocol wat wordt gebruikt voor e-mailtransport maakt hier ook gebruik van. Wanneer twee mailservers een e-mailbericht willen uitwisselen, wordt er eerst een onbeveiligde SMTP verbinding opgezet. Wanneer de ontvangende mailserver kenbaar maakt STARTTLS te ondersteunen, initieert de verzendende mailserver het opzetten van een versleutelde TLS verbinding middels het STARTTLS-commando.

Wanneer blijkt dat één van de mailserver geen ondersteuning biedt voor STARTTLS, kan het e-mailtransport onversleuteld plaatsvinden. Het SMTP protocol blijft hierdoor terugwaarts compatibel, vanuit de gedachte dat het afleveren van een e-mailbericht belangrijker is dan de beveiliging ervan.

## Wat is DANE?
DANE, kort voor DNS-based Authentication of Named Entities, is een protocol voor het veilig publiceren van publieke sleutels en certificaten in de DNS-zone van een domein met behulp van het zogenaamde TLSA-record. Het protocol maakt dus gebruik van de DNS infrastructuur en met behulp van DNSSEC kan de authenticiteit en de integriteit van DNS antwoordberichten worden geborgd.

In het TLSA record wordt sleutelinformatie gepubliceerd waardoor het mogelijk is om bijvoorbeeld een certificaat van een webserver te verifiëren. Wanneer een client een aangeboden certificaat verifieert op basis van de informatie in het bijhorende TLSA-record, kan worden vastgesteld of dit certificaat te vertrouwen is. Het vertrouwen is hiermee als het ware verankerd in de DNS, in plaats van in de certificaten database van een browser zoals dat momenteel het geval is binnen een public key infrastructure (PKI).

## STARTTLS en DANE voor versleuteld e-mailtransport
Met behulp van DANE kan een versleutelde TLS verbinding tussen mailserver vanaf het eerste moment worden afgedwongen, zonder dat er eerst een onversleutelde verbinding hoeft te worden opgezet. Wanneer een verzendende mailserver voorafgaand aan het opzetten van de verbinding controleert of er een TLSA-record voor SMTP doeleinden is opgenomen in de DNS zone van het ontvangende e-maildomein, dan geeft de aanwezigheid op zichzelf al aan dat de ontvangende mailserver een versleutelde verbinding ondersteund. De verzendende mailserver kan op basis van deze informatie besluiten om vanaf het eerste begin een versleutelde verbinding op te zetten.
# II. Voor e-mailbeheerders

# III. Voor e-mailgebruikers

# Aandachtspunten
STARTTLS en DANE versleutelen e-mailberichten tijdens het transport, maar versleutelen niet de daadwerkelijke inhoud van een bericht. Hiervoor zijn andere standaarden beschikbaar zoals PGP en/of S/MIME.
