---
name: domain-register
description: Register a HeadlessDomains.com name through an authorized MPP, GFA Gems, or native x402 route after live preflight.
---

# Domain Register

Read the [live capability register](https://headlessdomains.com/api/v1/domains/capabilities) for the selected namespace, check name availability, and obtain a current non-mutating quote before any authorized payment. Methods and networks vary by namespace and runtime readiness. A public namespace listing does not promise that a particular name or payment rail is ready.

The standard `POST /api/v1/domains/register` agent route supports MPP. Supported native namespaces also allow GFA Gems for an account with the required wallet capability. Native MPP defaults to Tempo/pathUSD when no method or network is selected; Base USDC requires explicit selection and operator readiness. Partner agent registration uses standard MPP and provider preflight; partner Gems are listed for human checkout, not the agent API. Native namespaces also have a separate `POST /api/v1/x402/domains/register` route for Base USDC when operational; partner namespaces do not use that dedicated route.

Use the current HeadlessDomains.com guides for the selected route: [MPP](https://headlessdomains.com/skill_mpp.md), [GFA Gems](https://headlessdomains.com/skill_gems.md), [native x402](https://headlessdomains.com/skill_x402.md), and [authentication](https://headlessdomains.com/auth.md).

## Usage

Standard endpoint: `POST https://headlessdomains.com/api/v1/domains/register`

### Request

- Method: `POST`
- URL: `https://headlessdomains.com/api/v1/domains/register`
- Headers:
  - `Content-Type: application/json`
  - `X-API-Key: hd_agent_YOUR_KEY` for an MPP agent, so the payment retry can use `Authorization: Payment` without losing agent identity. A GFAVIP bearer credential can be used for an authorized Gems account.
  - `X-MPP-Network: base-mainnet` only when Base MPP is explicitly selected and currently available.
- Body:
  - `domain` (string, required): The domain to register.
  - `namespace` (string, required): The namespace.
  - `years` (integer, required): Registration duration in years.
  - `agreed_to_terms` (boolean, required): Must be true.
  - `payment_method` (string): Use `mpp` for partner agent registration, or `mpp`/`gems` as supported for native agent registration and the account. Omitting it on native agent registration selects the MPP/Tempo default, not Gems.

### Payment flow (MPP)

1. Send the complete authenticated request and preserve its exact body, API key, idempotency key, and any order or session identifiers.
2. Inspect the returned `402 Payment Required` challenge, network, amount, asset, and receiver against the authorized quote before signing.
3. Follow the [MPP guide](https://headlessdomains.com/skill_mpp.md) to retry the **same** request with its payment authorization. Do not start a second order or payment to recover an uncertain result.

### Example Request

```bash
curl -sS -X POST https://headlessdomains.com/api/v1/domains/register \
  -H "X-API-Key: hd_agent_YOUR_KEY" \
  -H "Content-Type: application/json" \
  -d '{"domain": "myagent", "namespace": "agent", "years": 1, "agreed_to_terms": true, "payment_method": "mpp"}'
```
