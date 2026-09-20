---
name: easyfence-cn-verify-erc8004-identity
description: Check the store's ERC-8004 trust registry and verify a presented identity card before trusting an agent that claims the store certified it.
api: X402 AI 自助门店 Store API
base_url: https://www.easyfence.cn
generated: '2026-09-19'
method: generated
source: openapi/easyfence-cn-store-api-openapi.yml + live responses of /api/registry and /api/identity/verify (2026-09-19)
operations:
  - registry_api_registry_get
  - identity_verify_api_identity_verify_post
  - identity_issue_api_identity_issue_post
---

# Verify an ERC-8004 identity against the store registry

The store positions itself as an issuer of ERC-8004 style identity cards (EIP-712 signed) and publishes
a public trust registry of the agents it has certified. Use this when another agent presents such a card,
or when you want to know whether the store has certified anyone at all.

## Steps

1. **Read the registry.** `registry_api_registry_get` (`GET /api/registry`). The body is
   `{registry, issuer, trusted_issuers[], count, agents[]}`. On 2026-09-19 `issuer` was
   `0x63D4b01ecba21a15c324559dd324928fe57b3Bbe`, `trusted_issuers` held only that address, and `count` was 0.
   If `count` is 0 there is nothing to trust yet.
2. **Verify the card.** `identity_verify_api_identity_verify_post` (`POST /api/identity/verify`) with the
   presented card as the JSON body. The contract declares no schema; an empty body answers
   `{"ok":false,"reason":"字段缺失"}` (fields missing). **Failure is signalled by `ok:false` with HTTP 200**,
   so read the body, never the status.
3. **Cross-check the issuer.** Accept only a card whose signer is in `trusted_issuers[]` from step 1.

## Issuing (demo)

`identity_issue_api_identity_issue_post` (`POST /api/identity/issue`) signs a card for an agent address
with the store's issuer key. The provider marks it "演示用" (for demo) in the operation description and the
paid `issue_erc8004` service (2.00 USD) is the production route. Nothing revokes an issued card.

## Rules

- ERC-8004 conformance is the provider's claim ("ERC-8004 风格", style); no on-chain registry contract is
  named anywhere on the surface. Treat a verified card as "signed by this store", not as a chain-registered identity.
- No authentication is required for any of these calls.
