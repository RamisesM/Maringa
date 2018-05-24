#### RSA

RSA (Rivest–Shamir–Adleman) is one of the first public-key cryptosystems and is
widely used for secure data transmission. In such a cryptosystem, the encryption
key is public and it is different from the decryption key which is kept secret
(private). In RSA, this asymmetry is based on the practical difficulty of the
factorization of the product of two large prime numbers, the "factoring
problem".

RSA is a relatively slow algorithm, and because of this, it is less commonly
used to directly encrypt user data. More often, RSA passes encrypted shared keys
for symmetric key cryptography which in turn can perform bulk
encryption-decryption operations at much higher speed.

- A basic principle behind RSA is the observation that it is practical to find
three very large positive integers e, d and n such that with modular
exponentiation for all integer m (with 0 ≤ m < n):

  ![](rsa1.svg)

  and that even knowing e and n or even m it can be extremely difficult to find d.

##### Steps

###### Key generation

- The public key consists of the modulus n and the public (or encryption)
exponent e.

-The private key consists of the private (or decryption) exponent d, which
must be kept secret.

###### Key distribution

Suppose that Bob wants to send information to Alice. If they decide to use RSA,
Bob must know Alice's public key to encrypt the message and Alice must use her
private key to decrypt the message. To enable Bob to send his encrypted
messages, Alice transmits her public key (n, e) to Bob via a reliable, but not
necessarily secret, route. Alice's private key (d) is never distributed.

After Bob obtains Alice's public key, he can send a message M to Alice.

To do it, he first turns M (strictly speaking, the un-padded plaintext) into an
integer m (strictly speaking, the padded plaintext), such that 0 ≤ m < n by
using an agreed-upon reversible protocol known as a padding scheme. He then
computes the ciphertext c, using Alice's public key e, corresponding to:

![](rsa2.svg)

This can be done reasonably quickly, even for 500-bit numbers, using modular
exponentiation. Bob then transmits c to Alice.

###### Decryption

Alice can recover m from c by using her private key exponent d by computing:

![](rsa3.svg)

Given m, she can recover the original message M by reversing the padding scheme.

##### Padding schemes
