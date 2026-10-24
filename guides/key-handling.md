# Exposing cryptographic keys

**Pitfall:** Hard-coding a secret key in source code, committing it to version control, or giving every component broad access to it.

Encryption does not help if the key is exposed alongside the protected data. A leaked key may remain in commit history, logs, build artifacts, backups, or developer machines even after a file is edited.

## Safer default

- Keep production secrets out of source control; use an appropriate secret-management facility.
- Limit which services and people can access each key, and avoid reusing one key for unrelated purposes.
- Plan how keys are backed up, rotated, revoked, and recovered before depending on them.
- Treat a committed secret as exposed: revoke or rotate it and investigate where it may have propagated.

## Sources

- [OWASP Key Management Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Key_Management_Cheat_Sheet.html)
- [OWASP Cryptographic Storage Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Cryptographic_Storage_Cheat_Sheet.html)
