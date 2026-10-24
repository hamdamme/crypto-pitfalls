# Encryption without authentication

**Pitfall:** Encrypting data while assuming that encryption alone will also detect tampering.

Confidentiality and integrity are separate properties. Some encryption modes do not authenticate ciphertext, so an attacker may be able to alter it without detection. The exact consequences depend on the construction and how the application handles decrypted data.

## Safer default

- Prefer a maintained library API for authenticated encryption with associated data (AEAD), such as AES-GCM or ChaCha20-Poly1305 where supported.
- Check that authentication succeeds before using or exposing decrypted data.
- Do not combine separate encryption and authentication primitives yourself unless a reviewed protocol explicitly requires it.
- If a legacy system cannot use AEAD, get expert review of its authentication design and migration plan.

## Sources

- [OWASP Cryptographic Storage Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Cryptographic_Storage_Cheat_Sheet.html)
- [NIST SP 800-38D: GCM and GMAC](https://csrc.nist.gov/pubs/sp/800/38/d/final)
- [RFC 8439: ChaCha20 and Poly1305](https://www.rfc-editor.org/rfc/rfc8439.html)
