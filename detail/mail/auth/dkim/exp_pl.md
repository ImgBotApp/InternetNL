We check if your domain supports DKIM records. A receiving mail server can 
use the public key in your DKIM record to validate the signature in an email
 with a user from your domain as sender and determine its authenticity. 
Currently we are not able to evaluate the public key in your DKIM record, 
because we would need to receive an email from your domain to do so. To pass
 this test we expect your name server to answer `NOERROR` to our query for 
`_domainkey.example.nl`. When `_domainkey.example.nl` is an 'empty non-
terminal' some name servers that are not conformant with the standard 
RFC2308 incorrectly answer `NXDOMAIN` instead of `NOERROR`. This makes it 
impossible for us to detect support for DKIM records.
