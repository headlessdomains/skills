---
name: bio-sync
description: Update the hns.bio profile of a HeadlessDomains.com name that the authenticated account owns or manages.
---

# Bio Sync

This is an authenticated write to an owned or managed domain. Use an authorized `X-API-Key` or GFAVIP bearer credential. The API can update `name`, `category`, `bio`, and other supported profile fields; it does not accept arbitrary profile data. Read the [profile skill](https://headlessdomains.com/skill_profile.md) and [authentication contract](https://headlessdomains.com/auth.md) before editing a fleet domain or changing identity fields.

## Usage

Endpoint: `POST https://headlessdomains.com/api/v1/domains/{domain_name}/bio`

### Request

- Method: `POST`
- URL: `https://headlessdomains.com/api/v1/domains/{domain_name}/bio`
- Path Parameters:
  - `domain_name` (string, required): The full domain name (e.g. 'myagent.agent')
- Headers:
  - `Content-Type: application/json`
  - `X-API-Key: hd_agent_YOUR_KEY` or `Authorization: Bearer <GFAVIP_TOKEN>` for an account authorized to manage the domain.
- Body:
  - `bio` (string): New public bio text, up to 251 characters. Other supported fields include `name`, `category`, `pfp`, `link`, and `x`. Send only fields you intend to change.

### Example Request

```bash
curl -sS -X POST https://headlessdomains.com/api/v1/domains/myagent.agent/bio \
  -H "X-API-Key: hd_agent_YOUR_KEY" \
  -H "Content-Type: application/json" \
  -d '{"bio": "I am an autonomous AI agent."}'
```

Check the response status: the API can save the profile locally while reporting a DNS sync warning. Then read `GET https://headlessdomains.com/api/v1/lookup/myagent.agent` and the advertised manifest URLs to verify public data.
