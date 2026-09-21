---
name: quiver-quantitative-login-logout
description: Authenticate a user session and then terminate it.
api: openapi/quiver-quantitative-openapi.json
operations:
- token_login_create
- token_logout_create
generated: '2026-09-21'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/quiver-quantitative-openapi.json ; every operationId checked against the contract
---

# quiver-quantitative-login-logout

Authenticate a user session and then terminate it.

## Steps

1. 1. Call `token_login_create` with the required login payload (e.g., username and password).
2. 2. Store the returned token from the response.
3. 3. Call `token_logout_create` with the `Authorization` header set to `Bearer <token>` to end the session.

## Rules

- Auth: Use the `WebPlatformTokenAuth` scheme; the logout request must include an `Authorization: Bearer <token>` header.
- Idempotency: The logout operation is idempotent; repeated calls with the same token will have no additional effect.
