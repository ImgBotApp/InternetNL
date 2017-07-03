We testen of de DANE-fingerprint die je domein presenteert geldig is voor je
 websitecertificaat. Met DANE kan je informatie over jouw websitecertificaat
 publiceren in een speciaal DNS-record, een TLSA-record. Clients, zoals 
webbrowsers, kunnen het certificaat nu niet alleen via de 
certificaatautoriteit, maar ook via het TLSA-record controleren op 
authenticiteit. Een client kan het TLSA-record ook als signaal gebruiken om 
alleen via HTTPS (en niet via HTTP) te verbinden. DNSSEC is een 
noodzakelijke randvoorwaarde voor DANE. Let op: gevallen waarbij we een 
geldige TLSA-record maar geen DNSSEC detecteren óf waarbij we het opvragen 
van het TLSA-record mislukt, worden ook beschouwd als fouten in deze test.
