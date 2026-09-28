---
name: domain-register
description: Register a domain on HeadlessDomains.com using MPP or GFA Gems after checking the live namespace capabilities and payment networks.
---

# Domain Register

This skill describes the standard MPP and GFA Gems registration route. Payment methods and networks vary by namespace and runtime readiness. Read `GET /api/v1/domains/capabilities`, obtain a current quote, and follow the returned payment challenge rather than assuming a network is available.

Native namespaces also expose a separate `POST /api/v1/x402/domains/register` route for Base USDC when the x402 route is operational. Partner namespaces use the standard registration route and provider preflight; they do not use the dedicated x402 route.

## Usage

Endpoint: `POST https://headlessdomains.com/api/v1/domains/register`

### Request

- Method: `POST`
- URL: `https://headlessdomains.com/api/v1/domains/register`
- Headers:
  - `Content-Type: application/json`
- Body:
  - `domain` (string, required): The domain to register.
  - `namespace` (string, required): The namespace.
  - `years` (integer, required): Registration duration in years.
  - `agreed_to_terms` (boolean, required): Must be true.
  - `payment_method` (string, required): `mpp` or `gems`.
  - `receipt` (string, optional): MPP payment authorization receipt (if challenged).

### Payment Flow (MPP)

1. Send the initial POST request without a `receipt`.
2. Receive a `402 Payment Required` challenge.
3. Fulfill the payment and obtain a receipt.
4. Re-submit the POST request including the `receipt`.

### Example Request

```bash
curl -X POST https://headlessdomains.com/api/v1/domains/register \
  -H "Content-Type: application/json" \
  -d '{"domain": "myagent", "namespace": "agent", "years": 1, "agreed_to_terms": true, "payment_method": "mpp"}'
```
