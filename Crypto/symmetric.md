#### Symmetric Cryptography

Symmetric-key algorithms are algorithms for cryptography that use the same
cryptographic keys for both encryption of plaintext and decryption of
ciphertext.

- The keys may be identical or there may be a simple transformation to
go between the two keys.
- The keys, in practice, represent a shared secret between two or more parties
that can be used to maintain a private information link. This requirement that
both parties have access to the secret key is one of the main drawbacks of
symmetric key encryption, in comparison to public-key encryption (also known as
asymmetric key encryption).

##### Types

Symmetric-key encryption can use either stream ciphers or block ciphers.

- Stream ciphers encrypt the digits (typically bytes), or letters (in substitution
ciphers) of a message one at a time. An example is the Vigenere Cipher.

- Block ciphers take a number of bits and encrypt them as a single unit, padding the
plaintext so that it is a multiple of the block size. Blocks of 64 bits were
commonly used. The Advanced Encryption Standard (AES) algorithm approved by NIST
in December 2001, and the GCM block cipher mode of operation use 128-bit blocks.

##### Security

- Symmetric ciphers have historically been susceptible to known-plaintext attacks,
chosen-plaintext attacks, differential cryptanalysis and linear cryptanalysis.
Careful construction of the functions for each round can greatly reduce the
chances of a successful attack.

- When used with asymmetric ciphers for key transfer, pseudorandom key generators
are nearly always used to generate the symmetric cipher session keys. However,
lack of randomness in those generators or in their initialization vectors is
disastrous and has led to cryptanalytic breaks in the past. Therefore, it is
essential that an implementation uses a source of high entropy for its
initialization.
