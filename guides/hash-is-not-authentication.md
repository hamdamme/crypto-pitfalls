# Treating a hash as proof of authenticity

**Pitfall:** Assuming that a plain hash proves who created a message or that it came from a trusted source.

A cryptographic hash can summarize data and help detect a change when compared with a trusted digest. If an attacker can replace both the data and its hash, the hash alone does not authenticate the data or its sender.

## Safer default

- Use a keyed message authentication code (MAC), such as HMAC, when parties share a secret key and need integrity/authentication.
- Use a digital signature when verification should rely on a public key.
- Obtain the expected digest, MAC key, or verification key through a trusted channel and verify it before relying on the result.

## Sources

- [NIST FIPS 198-1: The Keyed-Hash Message Authentication Code (HMAC)](https://csrc.nist.gov/pubs/fips/198-1/final)
- [NIST FIPS 186-5: Digital Signature Standard](https://csrc.nist.gov/pubs/fips/186-5/final)
