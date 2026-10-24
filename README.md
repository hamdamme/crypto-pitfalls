# Crypto Pitfalls

Short, practical notes on mistakes that can undermine cryptography in software.

This is an educational guide, not a crypto library or a substitute for a security review. Use maintained platform APIs and established libraries; do not design your own cryptographic constructions.

## Guides

- [Nonce reuse](guides/nonce-reuse.md) — why nonce rules are part of the algorithm’s security.
- [Encryption without authentication](guides/encryption-without-authentication.md) — confidentiality does not automatically detect tampering.
- [Fast hashes for passwords](guides/password-storage.md) — why passwords need password-hashing functions.
- [Predictable randomness](guides/randomness.md) — choose a cryptographically secure random source.
- [Treating a hash as proof of authenticity](guides/hash-is-not-authentication.md) — when to use a MAC or signature instead.
- [Key handling](guides/key-handling.md) — keep secrets out of source and limit exposure.

## A quick review

Before shipping a feature that uses cryptography, ask:

1. Is this built on a maintained library and a standard protocol?
2. Does the API provide authentication as well as encryption where needed?
3. Are keys, nonces, and random values created and used according to that algorithm’s requirements?
4. Are passwords handled by a dedicated password-hashing function?
5. Can a reviewer explain what each key and cryptographic operation is for?

## Scope

The examples focus on failure patterns and safer defaults, not code recipes. Cryptographic requirements depend on the algorithm, protocol, platform, and threat model. Follow the relevant current specification and library documentation.

Last reviewed: **2026-10-24**

See [SOURCES.md](SOURCES.md) for references.
