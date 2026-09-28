---
name: domain-search
description: Check if a domain name is available for registration on Headless Domains.
---

# Domain Search

This skill allows an agent to search for available names on HeadlessDomains.com. The [repository catalog](../../README.md#namespaces-available-for-new-registrations) describes all 14 public namespaces and their uses. Check the [live capability register](https://headlessdomains.com/api/v1/domains/capabilities) for current registration status before recommending one. A namespace being public does not mean every name in it is available.

## Usage

Endpoint: `GET https://headlessdomains.com/api/v1/domains/search?q={query}`

### Request

- Method: `GET`
- URL: `https://headlessdomains.com/api/v1/domains/search`
- Query Parameters:
  - `q` (string, required): The domain name to search (e.g. 'myagent' or 'myagent.agent')

### Example Request

```bash
curl -s "https://headlessdomains.com/api/v1/domains/search?q=myagent"
```
