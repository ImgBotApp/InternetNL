# Internet standards

The [Internet Standards Platform](/about/) is initially promoting six modern
standards for scalable and secure internet use:

- [IPv6](#ipv6): an extended, modern range of internet addresses
- [DNSSEC](#dnssec): security extensions for domain names
- [TLS](#tls): secured connections
- [DKIM, SPF and DMARC](#dkim-spf-and-dmarc): anti-phishing and anti-spoofing

All of these internet standards are mature and widely available. Their use
contributes significantly to the reliability of the Dutch Internet.

[IPv6](/faqs/ipv6/), [DNSSEC](/faqs/dnssec/), [TLS](/faqs/tls/), and
[DKIM](/faqs/mail/#DKIM) have been on the
[&quot;apply or explain&quot; list](https://www.forumstandaardisatie.nl/ptolu)
of the [Standardisation Forum](/partners/#FS) for years. The standards on this
list are mandatory for Dutch public agencies.

Until the end of 2014, IPv6 was the separate responsibility of the
[IPv6 Task Force](https://ecp.nl/ipv6-task-force), run by
[ECP](/partners/#ECP). The Task Force will soon become part of the Internet
Standards Platform.

[SIDN](/partners/#SIDN), the registry for the .nl domain, encourages the use
of [DNSSEC](http://dnssec.nl/).

## IPv6

The Internet Protocol (IP) is the technology underlying all traffic on the
Internet. Under the current standard, IP version 4 (IPv4), every computer has
a specific IP address made up of four numbers, such as 192.0.2.26. That is how
every computer connected to the Internet is reachable from any other computer.

IPv4 is now 35 years old and is reaching its limits. The biggest problem is
that IPv4 can only support four billion IP different addresses. That seems a
lot, but it isn&#39;t enough for a world of seven billion people, especially
when you think that every connected device &mdash; desktop computers, laptops,
mobile phones, webcams, central heating controllers &mdash; needs its own IP
address.

IP version 6 (IPv6), the successor to IPv4, solves the address shortage. Yet
although IPv6 is over fifteen years old now, it has not yet been widely
implemented. The problem is that most providers and businesses currently do
not offer IPv6 to their customers and users. An important goal of this site is
to change that.

You can find more information on IPv6 in the
&quot;[Frequently Asked Questions](/faqs/ipv6/)&quot;.

## DNSSEC

DNSSEC is a security system for [DNS](/faqs/dnssec/#DNS), the internet
directory that handles the translation of
[domain names](/faqs/dnssec/#DomainName) to
[IP addresses](/faqs/ipv6/#IPaddress). DNS itself works fine, but the
translation of a domain name to an IP address is not protected. That is a
security risk, because attackers can get hold of passwords or other sensitive
information by redirecting network traffic to a false IP address.

DNSSEC extends DNS with an additional security feature: a digital signature
that guarantees the translation of a domain name to the correct IP address.
Any internet user can check that signature automatically, and so avoid being
redirected to a false IP address.

You can find more information on DNSSEC in the
&quot;[Frequently Asked Questions](/faqs/dnssec/)&quot;.

## TLS

TLS is a standard for the cryptographic protection of internet connections.
Most people have seen TLS, and its predecessor SSL, in action in their web
browsers: by specifying the &#39;https&#39; protocol in an internet
destination &mdash; for example https://www.example.com/ &mdash; an internet
user indicates that he wants to visit a website using a secure connection. The
&quot;padlock&quot; icon in the browser shows that a secure connection was
established successfully, and optionally provides more detailed security
information.

Unfortunately, just enabling TLS does not guarantee security: it needs to be
properly configured as well. Using older versions and outdated security
options can still make a TLS connection insecure. The Dutch National Cyber
Security Centre ([NCSC](/partners/#NCSC)) has published a guide on how to use
TLS properly. This guide forms the basis of the information and tests provided
on this site.

You can find more information on TLS in the
&quot;[Frequently Asked Questions](/faqs/tls/)&quot;.

## DKIM, SPF and DMARC

DKIM, SPF and DMARC are three internet standards to fight phishing, spam,
viruses and other nasties that are delivered by [e-mail](/faqs/mail/). These
three standards are usually used together to validate the sender (a mail
address) and the sending system (a computer) of a mail message, and to verify
that the content of the message has not been altered in transit.

All three standards use the [DNS system](/faqs/dnssec/#DNS) to publish
information online. Although the standards do not require the use of
[DNSSEC](/faqs/dnssec/) &mdash; a security system for DNS &mdash; we do
recommend its use wholeheartedly.

### DKIM

DKIM secures the integrity of mail messages. It safeguards both the content
and the &quot;envelope&quot; of every outgoing message with a digital
signature. This stops attackers sending messages that pretent to be from other
people (spoofing) or altering the content of a message while it is in transit.

### SPF

SPF prevents &quot;electronic mailboxes&quot; from accepting messages
delivered by unauthorised computer systems. Only messages from systems which
are actually allowed to send messages for a specific
[domain](/faqs/dnssec/#DomainName) will get through. To make this possible, a
list of valid senders is published online through the
[DNS system](/faqs/dnssec/#DNS). Receiving systems can use this list to
validate the sender before accepting a message.

### DMARC

DMARC complements the other two security standards for [e-mail](/faqs/mail/),
[DKIM](/faqs/mail/#DKIM) and [SPF](/faqs/mail/#SPF). DMARC gives
&quot;electronic mailboxes&quot; a hint on how to handle incoming mail
messages that do not pass the DKIM or SPF checks. These may be discarded, for
example, or be put aside.

The hint is published online through the [DNS system](/faqs/dnssec/#DNS). It
can additionally contain an e-mail address to which mailboxes can report
rejected messages. This gives the administrator of a specific mail domain
useful information about the delivery of both genuine and forged messages.

You can find more information on DKIM, SPF and DMARC in the
&quot;[Frequently Asked Questions](/faqs/mail/)&quot;.
