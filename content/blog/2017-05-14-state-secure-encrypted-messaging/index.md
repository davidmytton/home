---
title: "The state of secure, encrypted messaging"
date: 2017-05-14
modified: 2017-05-14
draft: false
tags: ["Security"]
summary: "Everyone should have an expectation of being able to communicate with 
someone else in a verifiably secure manner."
url: the-state-of-secure-encrypted-messaging
---

Everyone should have an expectation of being able to communicate with someone
else in a verifiably secure manner. I have a particular fascination with secure
communications and encryption and I’ve spent a lot of time thinking through my
own pragmatic approach to secure messaging.

This is my write up of the current state of things as I’ve found it.

## E-mail encryption & PGP

E-mail seems to be considered a secure way to communicate but it is actually
about as safe as sending a postcard in the mail, despite it being used for all
sorts of private and confidential communications.

[Progress has been
made](https://www.google.com/transparencyreport/saferemail/) with major
providers encrypting mail in transit, but once it reaches your inbox, the
message is still open to the provider or anyone who might gain access to your
mail account.

Sensitive files, personal information and discussions many would want to keep
secret are stored in inboxes, often indefinitely. If you use a free email
service, your emails are scanned for advertising.

The solution is encryption, and PGP is the standard. However, there are a
multitude of problems that make PGP unworkable:

- The security model itself relies on the security of the keys. If the keys
  become compromised, all past messages can be decrypted i.e. It has no [forward
  secrecy](https://en.m.wikipedia.org/wiki/Forward_secrecy).
- Managing keys is a hassle — you have to very careful with your private key.
  Storing them in the cloud defeats the point and [browser based encryption has
  concerns](https://tonyarcieri.com/whats-wrong-with-webcrypto), so it has to be
  stored on your local system which can leave it vulnerable to malware or a
  permissions mistake. It is recommended to [store keys on a hardware device
  such as a
  YubiKey](https://www.yubico.com/support/knowledge-base/categories/articles/use-yubikey-openpgp/) but
  setting one up to handle PGP is not particularly easy.
- There are no good mobile email clients which support PGP. There are several
  apps for iOS ([which is the only secure mobile
  OS](https://blog.cryptographyengineering.com/2017/03/05/secure-computing-for-journalists/))
  but they are either outdated, have minimal functionality or require an odd
  workflow rather than being a fully featured mobile client. Further, you have
  to trust they are doing the right things with your keys. And if you follow
  best practice and use a YubiKey, you cannot plug that into a mobile device.
- Encrypted email cannot be parsed by your mail server spam filters, apply
  intelligent filtering or for server side search. I actually think that Apple
  Mail on OS X has better search than GMail, but search on iOS isn’t as good and
  with the volume of emails I get, using something
  like [Sanebox](https://www.sanebox.com/) (which is what I use) or [Priority
  Inbox](https://gmail.googleblog.com/2010/08/email-overload-try-priority-inbox.html) simply
  wouldn’t work as well on encrypted messages.

As a result, it is very difficult to get non-technical users to adopt PGP and if
you make use of it yourself, you lose a lot of necessary functionality for
keeping your inbox manageable.

I did find an interesting approach used by a small number of mail providers
whereby they will encrypt all incoming email with your public PGP key (after
spam filtering) so all your messages are encrypted in storage. There are some
challenges with this approach, such as being unable to easily encrypt your “Sent
Mail” folder, which will of course contain the full email thread but you could
simply disable remote storage of sent mail. And of course it only protects
messages on your side – the recipient still has a plain text
copy! [Mailbox.org](https://mailbox.org/en/) seemed to be the most reputable of
the few mail providers who offer this but you still face all the same problems
above as if you had used PGP in the first place.

Given all the above limitations, with modern workflows and mobile access in
particular (indeed, mobile accessis the most secure way to manage your email),
using PGP is basically unworkable. [A
conclusion](https://moxie.org/blog/gpg-and-me/) many [others have come
to](https://www.schneier.com/blog/archives/2016/12/giving_up_on_pg.html).

## iMessage & WhatsApp

Probably the two most widely used, mobile-first messaging apps. WhatsApp is
significantly further ahead because of its cross platform capabilities, but
iMessage is also popular due to it being the iOS default.

For me, the most convenient aspect of iMessage is its support for all Apple
platforms. You can seamlessly move between iPhone, iPad, Mac and Watch. Whenever
I try a new messaging app, this is the biggest thing that always brings me back
to iMessage.

[It is also
secure](https://techcrunch.com/2014/02/27/apple-explains-exactly-how-secure-imessage-really-is/),
but the key model means that you have to trust Apple. I believe that given Tim
Cook’s public position on privacy and security — specifically stating that
iMessage communication cannot be read — Apple has so much to lose in reputation
by allowing access to the police/security services that they won’t risk it. As
such, we can trust the service. This is sufficient for most people.

WhatsApp is owned by Facebook, a company I do not trust. However, the end to end
encryption is [implemented using the Signal
protocol](https://whispersystems.org/blog/whatsapp-complete/) and backed by
Moxie Marlinspike, who I do trust. The fact that so many people use WhatsApp and
its group messaging functionality is also a major point in its favor. [The
recent Guardian
reporting](https://docs.google.com/document/d/1nqlE6UQjbUmgoMeJCePVcY5flqn8hAhmfIjeVE8PnEk/edit) to
the contrary is [simply
wrong](https://whispersystems.org/blog/there-is-no-whatsapp-backdoor/), and
highly damaging to the Guardian’s reputation for quality journalism.

[The problem with both of these
services](https://theintercept.com/2016/06/22/battle-of-the-secure-messaging-apps-how-signal-beats-whatsapp/) is
the metadata that is collected. Information about who you are communicating with
and when [can reveal a
lot](https://www.newyorker.com/news/news-desk/whats-the-matter-with-metadata),
and should be considered as sensitive as the content itself. They are also both
operated by corporations who you may or may not trust to manage the keys for you
and backups to the cloud are enabled by default, so it is trivial for them to
access your communications without having to break into or backdoor the service
itself.

## Signal and Keybase

These apps are both best in class when it comes to security. They are both open
source and are highly regarded in the security community. Signal is the most
mature and used by [high profile potential
targets](http://www.vanityfair.com/news/2016/08/how-the-clinton-campaign-is-foiling-the-kremlin).
And in the case of Keybase, you control the keys.

The problem for casual users is convenience. Compared to WhatsApp and iMessage,
they are not very popular and there is limited support for non-mobile platforms.
Signal has a desktop client but it is not standalone and requires Chrome to be
running. This makes for a sub-optimal UX, especially if you don’t use Chrome as
your browser. The UI doesn’t really fit into the design guidelines of macOS and
unless it is open and running, you won’t get notifications.

Keybase just recently released their iOS and Android app, but it is quite
obvious it has been built using a non-native framework (React Native) with some
lag and buginess (at least on iOS). It is still early and I am particularly
interested in it for KBFS, which is the first client-encrypted cloud filesystem.
Once that comes to the mobile app and the bugs resolved, then it will be a great
alternative to iCloud Drive/Google Drive/Dropbox.

## Other apps?

The only generally accepted “secure” apps are those mentioned above. Apps like
CryptoCat ([dubious security history](https://tobtu.com/decryptocat.php))
and [Telegram](https://en.wikipedia.org/wiki/Telegram_%28messaging_service%29#Security) are
not.

[Wire](https://wire.com/en/) looks interesting but I’ve not had an opportunity
to test it.

## Mobile apps only for casual use?

For me, iMessage, WhatsApp, Signal and Keybase all suffer from the same problem
of not being appropriate for long form communication. The mobile-first approach
with a small screen means it is difficult to use them as a replacement for
email, especially if you are dealing with attachments.

The rise of voice based computing and assistants like Google Home, Alexa and
Siri will also be hampered by encrypting your messages. Users might like to be
able to have their mail read to them, or to instruct the assistant to dictate a
reply to messages. There’s obviously little point encrypting messages if you’ve
already read them out to an assistant which uses cloud services to transcribe
the audio!

And good luck trying to get your lawyer or accountant to communicate with you
only using Signal or Keybase!

## A pragmatic approach

Users will ultimately use the services which: a) most people use; b) have the
least friction. This means email, iMessage and WhatsApp. Those who really need
security and/or are tech savvy will use Signal. Keybase looks promising, but
there’s still a risk it will remain niche.

The big problem is that users don’t really seam to care about secure messaging.
Most people simply don’t think about this often, and have a superficial view of
why privacy is important, usually centering around the argument: “[I have
nothing to hide](https://en.wikipedia.org/wiki/Nothing_to_hide_argument)”. Most
people also generally agree that the security services should have unfettered
access to communication for investigatory purposes. That is a reasonable
position but has more nuance because this is about broad, mass surveillance
rather than targeted monitoring with judicial safeguards (which I have no
problem with).

Given the inevitible use of email, iMessage and WhatsApp, there are some ways to
mitigate risk:

- [Have an aggressive retention
  policy](https://www.schneier.com/blog/archives/2015/01/the_security_of_10.html) for
  deleting your files & emails. What doesn’t exist can’t be leaked! Only store
  the data you truly need or have a legal requirement to retain for a period of
  time.
- Don’t use email as storage. Anything important and/or sensitive should be
  stored elsewhere, in an encrypted or otherwise secured form.
- Use the retention options in your messaging app: expiring messages are
  supported by Signal and [iMessage allows you to auto-delete your history after
  a period of time](https://support.apple.com/en-us/HT201287) (but note this
  doesn’t apply to messages sync’d to macOS, which you must manually delete).
- Disable SMS.
- Consider email to be public. If you wouldn’t be happy saying it in public,
  then don’t send it via email.
- Don’t send attachments. Upload files to cloud storage and share the link. Then
  you control whether the file remains shared or not, and precisely who can
  access it.
- Use a second channel to [verify any requests sent via
  email](https://krebsonsecurity.com/2017/02/irs-scam-blends-ceo-fraud-w-2-phishing/#more-37923).

Finally, [a good checklist of general security
principles](https://techsolidarity.org/resources/journalist_checkup.html) is
worth reviewing.
