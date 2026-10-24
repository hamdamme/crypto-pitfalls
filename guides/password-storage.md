# Using a fast hash for passwords

**Pitfall:** Storing passwords as plaintext, encrypted values, or fast general-purpose hashes such as SHA-256.

If a password database is exposed, an attacker can test guesses offline. Fast hashes make each guess cheap. A salt prevents precomputed tables from being reused across accounts, but it does not make a fast hash slow.

## Safer default

- Use a maintained password-hashing function through a framework or library, with a unique salt per password.
- Follow current guidance for parameters and rehash when the stored parameters become outdated.
- Never log passwords or store them in reversible form for ordinary login verification.
- Add rate limits and multi-factor authentication where appropriate; these complement password hashing.

## Sources

- [OWASP Password Storage Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html)
- [RFC 9106: Argon2 Memory-Hard Function for Password Hashing and Proof-of-Work Applications](https://www.rfc-editor.org/rfc/rfc9106.html)
