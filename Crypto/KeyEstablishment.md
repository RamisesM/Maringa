#### Key establishment

- Symmetric-key algorithms require both the sender and the recipient of a message
to have the same secret key. All early cryptographic systems required one of
those people to somehow receive a copy of that secret key over a physically
secure channel.

- Nearly all modern cryptographic systems still use symmetric-key algorithms
internally to encrypt the bulk of the messages, but they eliminate the need for
a physically secure channel by using Diffie–Hellman key exchange or some other
public-key protocol to securely come to agreement on a fresh new secret key for
each message (**forward secrecy**).

##### Forward secrecy

Diffie-Hellman is a way of generating a shared secret between two people in such
a way that the secret can't be seen by observing the communication. That's an
important distinction: You're not sharing information during the key exchange,
you're creating a key together.

```
(g^a mod p)^b mod p = g^ab mod p
(g^b mod p)^a mod p = g^ba mod p
```

Here, a and b are secrets from each side. Only (g^a mod p) and (g^b mod p) are
transmitted. They arrive at the same number without ever knowing each other
secrets.


##### Public key infrastructure (PKIs)

Public key infrastructures have been proposed as a way around this
problem of identity authentication. In their most usual implementation, each
user applies to a 'certificate authority' for a digital certificate which serves
for other users as a non-tamperable authentication of identity, at the risk of
compromising every user in case the CA itself is compromised.

Several countries and other jurisdictions have passed legislation or issued
regulations encouraging PKIs by giving (more or less) legal effect to these
digital certificates. Several commercial firms, and a few government
departments, have established such certificate authorities. VeriSign is the most
prominent commercial firm.

This does nothing to solve the problem though, as the trustworthiness of the CA
itself is still not guaranteed for any particular individual. It is a form of
argument from authority fallacy. For actual trustworthiness, personal
verification that the certificate belongs to the CA and establishment of trust
in the CA are required. This is usually not possible.

For those new to such things, these arrangements are best thought of as
electronic notary endorsements that “this public key belongs to this user”. As
with notary endorsements, there can be mistakes or misunderstandings in such
vouchings. Additionally, the notary itself can be untrusted. There have been
several high-profile public failures by assorted certificate
authorities.

##### Web of trust

At the other end of the conceptual range is the web of trust system, which
avoids central Certificate Authorities entirely. Each user is responsible for
getting any certificate from another before using that certificate to
communicate with, vet digital signatures from, ... the user claimed to be
associated with the particular public key in a certificate. PGP (and GPG, an
implementation of the OpenPGP Internet Standard) employ just such a web of trust
mechanism. Together they are the most widely used high quality cryptographic
system in the world.
