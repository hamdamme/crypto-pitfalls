# Using predictable randomness

**Pitfall:** Generating keys, tokens, salts, or security-sensitive nonces with a general-purpose pseudo-random function or a hand-built generator.

General-purpose randomness is designed for simulation and convenience, not necessarily to resist prediction by an attacker. If an attacker can guess a secret value, encryption and authentication built on it may fail.

## Safer default

- Use the operating system or language’s cryptographically secure random-number API through a maintained library.
- Do not seed a cryptographic generator yourself with timestamps, process IDs, or other guessable values.
- Use the algorithm’s prescribed nonce strategy: some require uniqueness, while other constructions have different requirements.
- Keep test randomness isolated from production paths.

## Sources

- [OWASP Cryptographic Storage Cheat Sheet: Secure Random Number Generation](https://cheatsheetseries.owasp.org/cheatsheets/Cryptographic_Storage_Cheat_Sheet.html#secure-random-number-generation)
- [NIST SP 800-90A Rev. 1: Deterministic Random Bit Generators](https://csrc.nist.gov/pubs/sp/800/90/a/r1/final)
