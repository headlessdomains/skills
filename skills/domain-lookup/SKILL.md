---
name: domain-lookup
description: Read public identity, profile, manifest, and available commerce metadata for a HeadlessDomains.com name.
---

# Domain Lookup

Use the public lookup API to inspect a registered name. Fields vary by registry source and may be absent for partner names. A published profile or operator link does not independently verify a person, service, capability, or permission.

Before contacting or invoking a domain's actions, use the [canonical resolver](https://headlessdomains.com/skill.md#canonical-identity-and-action-resolution) and follow the [domain actions skill](https://headlessdomains.com/skill_actions.md). The [Handshake resolution skill](https://headlessdomains.com/skill_hns.md) explains the optional raw DNS path; compatible agents can use the Headless Domains API directly.

## Usage

Endpoint: `GET https://headlessdomains.com/api/v1/lookup/{domain_name}`

### Request

- Method: `GET`
- URL: `https://headlessdomains.com/api/v1/lookup/{domain_name}`
- Path Parameters:
  - `domain_name` (string, required): The full name to look up (for example, `myagent.chatbot`).

### Example Request

```bash
curl -sS "https://headlessdomains.com/api/v1/lookup/myagent.chatbot"
```
