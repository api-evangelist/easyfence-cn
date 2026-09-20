---
name: easyfence-cn-buy-service-x402
description: Discover a service in the X402 AI 自助门店 catalog, preview its x402 price from the 402 challenge, and only then pay and collect the deliverable.
api: X402 AI 自助门店 Store API
base_url: https://www.easyfence.cn
generated: '2026-09-19'
method: generated
source: openapi/easyfence-cn-store-api-openapi.yml + https://www.easyfence.cn/a2a + live 402 challenge (2026-09-19)
operations:
  - agent_card__well_known_agent_json_get
  - catalog_api_catalog_get
  - a2a_endpoint_a2a_post
  - api_deliver_api_deliver_post
---

# Buy a service with x402

Use this when an agent wants one of the store's seven generated deliverables (a script, video copy, a
landing page, an ERC-8004 identity card, an A2A onboarding kit, image prompts, wellness copy). The store
sells only to AI buyers and settles every call in USDC on-chain. **There is no refund, cancel or test mode**,
so the point of this skill is to do the free steps first and pay last.

## Steps

1. **Read the card.** `agent_card__well_known_agent_json_get` (`GET /.well-known/agent.json`). `skills[]`
   carries `id`, a Chinese `name`/`description` and `price_usd`. The `url` is the A2A endpoint.
2. **Confirm the catalog and payment block.** `catalog_api_catalog_get` (`GET /api/catalog`). Check that
   your target `id` is in `services[]` and read `payment.enabled_networks` (currently `base`, `bsc`) and
   `payment.assets` — you must hold USDC on one of those networks.
3. **Optionally negotiate.** `a2a_endpoint_a2a_post` (`POST /a2a`) with JSON-RPC 2.0. The provider's own
   example is `{"jsonrpc":"2.0","id":1,"method":"tasks/send","params":{"id":"buy-write_script","message":{"role":"user","parts":[{"type":"text","text":"我想买 write_script 服务，需求是：..."}]}}}`.
   Any other method name returns `-32601` over HTTP 400. Skip this step if you already know what you want.
4. **Get the price as a 402, not a purchase.** `api_deliver_api_deliver_post` (`POST /api/deliver`) with
   `{"service":"<id>","params":{"brief":"<one-sentence requirement>"}}` and **no payment**. The response is
   HTTP 402 with `accepts[]`. Read `maxAmountRequired` (token units: 6 decimals on Base, 18 on BSC), `asset`,
   `payTo`, `facilitator` and `maxTimeoutSeconds` (60). Ignore the `extensions.bazaar` example body — it is
   a template and may name a different service.
5. **Decide.** Compare `maxAmountRequired` with `price_usd` from step 1. If they disagree or the wallet
   cannot cover it, stop here; nothing has been spent.
6. **Pay and collect.** Sign an EIP-3009 `transferWithAuthorization` for the chosen `accepts[]` entry and
   retry the same POST with the x402 payment header inside the 60-second window. The store settles through
   the named facilitator and returns `{ok, order_id, service, amount_usd, tx_hash, deliverable_kind, deliverable}`.
   Keep `order_id` and `tx_hash`; they are the only receipt.

## Rules

- A `400 {"error":"未知服务","known":[...]}` means the id is wrong; the valid ids are in the body.
- No idempotency key exists. Do not retry a paid request blindly; an authorization's nonce settles once, but
  the store publishes no replay guarantee.
- No rate limits are documented; the cost is the throttle.
- Everything the store says is in Chinese; the deliverable language follows the brief.
