# I. Algemeen

## Phishingprotectie
Phishing wordt door aanvallers toegepast om e-mails te vervalsen en betrouwbaar te laten lijken, terwijl ze dat in werkelijkheid niet zijn. De standaarden SPF, DKIM en DMARC worden gebruikt om de integriteit (echtsheidskenmerken, e-mailauthenticatie) van e-mail te borgen, zodat ontvangers kunnen controleren of e-mails ook daadwerkelijk afkomstig zijn van de veronderstelde afzender. Dit betekent dat phishingmails van aanvallers beter kunnen worden herkend, en dat de kans op misbruik afneemt.

SPF, DKIM en DMARC werken op domeinnaamniveau, en maken gebruik van DNS als mechanisme om bepaalde informatie te delen met het gehele internet. Ondanks het feit dat het gebruik van DNSSEC niet noodzakelijk is voor deze standaarden, wordt het gebruik ervan sterk aangeraden. Doordat DNSSEC de authenticiteit en integriteit van DNS antwoordberichten borgt, kan deze worden gebruikt als onderliggende beveiligingslaag voor andere beveiligingsstandaarden zoals SPF, DKIM en DMARC.

## Wat is DKIM?
DKIM staat voor Domain Keys Identified Mail. Met DKIM kunnen e-mailberichten worden gewaarmerkt. De ontvanger van een e-mail kan op die manier controleren of een e-mailbericht écht van de afzender afkomstig is en of het bericht onderweg ongewijzigd is gebleven. DKIM houdt zelf geen spam tegen, maar markeert legitieme e-mail als geldig met behulp van een DKIM handtekening. De ontvangende mailserver kan vervolgens op basis van de public key in het DNS-record valideren of de DKIM handtekening klopt. Een spamfilter kan vervolgens op basis van een foutieve of ontbrekende DKIM handtekening e-mail beschouwen als SPAM. Het gebruik van DKIM helpt dus wel om spam te bestrijden.

## Wat is SPF?
Het protocol Sender Policy Framework (afgekort SPF) heeft als doel spam te verminderen. SPF controleert of een verzendende mailserver die e-mail namens een domein wil versturen, ook daadwerkelijk gerechtigd is om dit te mogen doen. SPF voegt een extra informatieveld toe aan het DNS-record van een domein. In dit record wordt op basis van IP-adressen en/of hostnames vermeld welke mailservers namens dit domein e-mail mogen verzenden (een whitelist). Staat een mailserver niet in dit record en verzendt deze toch e-mail met het betreffende domein als afzender, dan wordt de e-mail beschouwd als SPAM.

## Wat is DMARC?
DMARC staat voor Domain-based Message Authentication, Reporting and Conformance. Met behulp van deze standaard kan een e-mailprovider kenbaar maken hoe andere (ontvangende) mailservers om dienen te gaan met de resultaten van de SPF- en/of DKIM-controles van ontvangen e-mails. Dit gebeurt door het publiceren van een DMARC beleid in het DNS-record van een domein. In versimpelde vorm stelt dit beleid bijvoorbeeld: “als de DKIM-handtekening niet klopt of ontbreekt, of als de verzendende mailserver niet voorkomt in de lijst met geautoriseerde mailserver, behandel deze e-mail dan als SPAM”.

Dit betekent wel dat een beheerder van een domein dient te borgen dat DKIM en SPF goed blijven functioneren, omdat fouten ook kunnen resulteren in het beschouwen van legitieme e-mailberichten als SPAM.

# II. Voor domeinnaamhouders
## Hoe weet ik of de e-mailvoorziening van mijn domein gebruik maakt van de standaarden SPF, DKIM en DMARC?
Doe de e-mailtest op Internet.nl.

## Hoe voeg ik ondersteuning voor deze standaarden toe?
Vraag het aan uw e-mailprovider. Als deze geen ondersteuning biedt voor deze standaarden, stap dan over op een e-mailprovider die dit wel ondersteund.

## Wat kan ik nog meer doen om e-mailgebruikers van mijn domein te beschermen tegen SPAM?
Het implementeren van de standaarden SPF, DKIM en DMARC is een belangrijke eerste stap. Het is echter ook belangrijk om de inkomende e-mailberichten op correcte wijze te beoordelen en classificeren, zodat de pakkans van SPAM berichten groter wordt. Hiermee neemt namelijk het risico op SPAM en Phishing voor e-mailgebruikers af.


# II. Voor e-mailgebruikers

## Hoe kan ik zien of mijn e-mailadres gebruik maakt van SPF, DKIM en/of DMARC?
Doe de e-mailtest op Internet.nl.

## Wat moet ik doen om inkomende e-mail te controleren op het gebruik van SPF, DKIM en/of DMARC?
Vraag je e-mailprovider om inkomende e-mail te controleren op het gebruik van deze standaarden, en om dit te gebruiken in de classificatie voor SPAM.

##
