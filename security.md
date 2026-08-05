# Security & Production checklist

This file lists important security and production-hardening steps required before accepting real funds or going to production.

- Do NOT store private keys or seed phrases in source control.
- Use hardware wallets or secure KMS/HSM to store any custodial keys.
- For user authentication, prefer server-side sessions and secure cookies, or delegate to wallet-signature-based login (SIWE / Sign-In With Ethereum).
- Run the application through security audits (smart contracts and backend).
- Use separate hot and cold wallets for custodial services; restrict hot wallet spending.
- Enforce rate-limiting, input validation, and strong authentication for API endpoints.
- Use HTTPS everywhere, set secure cookie flags, Content Security Policy, and other common security headers.
- Centralize logging and monitoring; configure alerts for abnormal activity.
- For CEX integrations (Bybit, Binance), store API keys in a secure vault (AWS KMS / HashiCorp Vault) and never commit them to the repo.
- Implement KYC/AML procedures if you intend to custody or trade on behalf of users.

Recommended next steps before production
1. Add automated tests and end-to-end tests on testnets.
2. Integrate a proper database (Postgres) and ORM (Prisma) for users and transactions.
3. Implement SIWE (Sign-In With Ethereum) for wallet login instead of storing passwords.
4. Deploy on a staging environment and run internal audits and external penetration tests.
