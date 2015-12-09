**This page is still a work in progress; this information will be available
soon.**

At the bottom of this page we provide links to more information on standards
for e-mail authentication.

## General

### What do DKIM, SPF and DMARC do?

DKIM, SPF and DMARC are three internet standards to fight phishing, spam,
viruses and other nasties that are delivered by e-mail. These three standards
are usually used together to validate the sender (a mail address) and the
sending system (a computer) of a mail message, and to verify that the content
of the message has not been altered in transit.

All three standards use the [DNS system](/faqs/dnssec/#DNS) to publish
information online. Although the standards do not require the use of
[DNSSEC](/faqs/dnssec/) &mdash; a security system for DNS &mdash; we do
recommend its use wholeheartedly.

### What is DKIM?

DKIM secures the integrity of mail messages. It safeguards both the content
and the &quot;envelope&quot; of every outgoing message with a digital
signature. This stops attackers sending messages that pretent to be from other
people (spoofing) or altering the content of a message while it is in transit.

### What is SPF?

SPF prevents &quot;electronic mailboxes&quot; from accepting messages
delivered by unauthorised computer systems. Only messages from systems which
are actually allowed to send messages for a specific
[domain](/faqs/dnssec/#DomainName) will get through. To make this possible, a
list of valid senders is published online through the
[DNS system](/faqs/dnssec/#DNS). Receiving systems can use this list to
validate the sender before accepting a message.

### What is DMARC?

DMARC complements the other two security standards for e-mail,
[DKIM](/faqs/mail/#DKIM) and [SPF](/faqs/mail/#SPF). DMARC gives
&quot;electronic mailboxes&quot; a hint on how to handle incoming mail
messages that do not pass the DKIM or SPF checks. These may be discarded, for
example, or be put aside.

The hint is published online through the [DNS system](/faqs/dnssec/#DNS). It
can additionally contain an e-mail address to which mailboxes can report
rejected messages. This gives the administrator of a specific mail domain
useful information about the delivery of both genuine and forged messages.

TODO

## For owners of an e-mail domain

TODO

## For internet users

TODO

## More information

- CIP white paper "[E-mailauthenticatie](http://www.cip-overheid.nl/wp-content/uploads/2014/06/20140528_Emailauthenticatie_def.pdf)"
- M3AAWG publication "[Trust in Email Begins with Authentication](https://www.m3aawg.org/sites/maawg/files/news/M3AAWG_Email_Authentication_Update-2015.pdf)"
- M3AAWG publication "[Protecting Parked Domains Best Common Practices](https://www.m3aawg.org/sites/maawg/files/news/M3AAWG_Parked_Domains_BP-2015-02.pdf)"
- [Mailman and DMARC](http://wiki.list.org/DEV/DMARC)
- Virus Bulletin: [Using DMARC to improve your email reputation](https://www.virusbtn.com/virusbulletin/archive/2014/11/vb201411-DMARC)
- [DKIM](http://www.dkim.org/), [SPF](http://www.openspf.org/) and
  [DMARC](http://dmarc.org/)
- [DKIM on 'apply or explain' list of Standardisation Forum](https://lijsten.forumstandaardisatie.nl/open-standaard/dkim)
