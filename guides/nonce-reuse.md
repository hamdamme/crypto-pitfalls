# Reusing a nonce

**Pitfall:** Using the same nonce (sometimes called an IV) more than once with the same key, when the algorithm requires uniqueness.

A nonce is often public, but its reuse rules are part of the algorithm’s security. For ChaCha20-Poly1305, RFC 8439 requires a unique nonce per invocation under a given key; reuse repeats both the keystream and the one-time authentication key, which can expose relationships between plaintexts and undermine authentication.

## Safer default

- Use a maintained library or protocol that manages nonce construction and limits.
- Follow the exact requirements for the chosen algorithm. “Random” is not a universal substitute for “unique.”
- Consider concurrency, multiple senders, process restarts, backups, and counter rollback when a design requires counters.
- If you cannot establish whether a key/nonce pair was reused, do not assume affected ciphertexts are safe; get a cryptographic review and follow the protocol’s key-rotation and incident process.

## Sources

- [RFC 8439, Sections 2.8 and 4](https://www.rfc-editor.org/rfc/rfc8439.html)
- [NIST SP 800-38D: GCM and GMAC](https://csrc.nist.gov/pubs/sp/800/38/d/final)
