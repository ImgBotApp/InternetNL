We check if your domain has an SPF record. A receiving mail server can use 
your whitelisted sending mail servers and the accompanying policy from your 
SPF record to determine the authenticity of a received email with your 
domain as sender. Currently we do not evaluate the SPF policy. In order for 
SPF to be effective against abuse of your domain for phishing and spam, you 
need to set an active policy i.e. `~all` (soft fail) or `-all` (hard fail). 
As a quick win we recommend to set a 'hard fail' policy for (sub-)domains 
that you do not use for sending mail to prevent abuse by others. Having more
 than one SPF record in the same domain is not valid and will lead to a test
 failure.
