# alt.anonymous.messages-to-mail.
A program which downloads articles from alt.anonymous.messages, tries to
decrypt all of them with the keys accessible on the current keychain, and
remails the ones which succeed to the current user, for reading with any
sensible e-mail software.

## Requirements.
slrn, zsh, sendmail-compatible local mail delivery, gpg.

## Ideas.
Symmetric encryption, passphrase-protected keys read from gpg-agent.

## INSTALL.
`git clone https://github.com/qybta/a.a.m-mail ~/aam`;
`crontab =(crontab -l;echo '*/271 * * * * ~/aam/check-mail')`;

Read the source for more information. It isn't much.

## Anonymity.
alt.anonymous.messages unfortunately doesn't provide a very large anonymity
set, but this is augmented some by using Tor for retrieving the messages. For
nation states to deanonymize Tor users without any prior suspicion is
currently hard, but not impossible. If you're under suspicion, as is
well-known, you're basically fucked using only Tor. Deanonymizing a.a.m users
without getting the secret key should be impossible, at least until "they" can
crack/procure the keys.

On the server side, assuming non-adversarial news-server, you can hide in the
anonymity set of other usenet users by using a random and well used server,
and paying in some anonymous manner if it costs you, of course. With
adversarial news-server "they" can easily distinguish you from others
by seeing which articles you download, so it's hardly worth hiding the
timing information. Downloading a fixed somewhat large number at a random
time would be preferable, but I couldn't do that to a free news-server.

On the receiving side, this becomes a question of information security.
Full disk encryption, fascist firewalls, updated software and few running
services for a reduced attack surface, is a must. Don't even think about
web-browsing. For added security, use a second computer for the attempted
decryption, preferably one that hasn't been connected to the internet.
