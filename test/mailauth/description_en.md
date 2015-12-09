An e-mail message can easily be forged. Attackers often abuse this
vulnerability for phishing, and to send spam, viruses and other nasties that
are delivered by e-mail. DKIM and SPF provide electronic mailboxes with the
means to validate the sender and the sending system of a mail message, and to
verify that the content of the message has not been altered in transit. DMARC
provides a policy on how to handle incoming mail messages that do not pass the
DKIM or SPF checks. All three standards use the DNS system to publish their
information for receiving mail systems.
