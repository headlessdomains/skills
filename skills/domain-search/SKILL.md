---
name: domain-search
description: Search names across supported HeadlessDomains.com namespaces and check current registration capabilities.
---

# Domain Search

Search a candidate label or full name with the public API. The [repository catalog](../../README.md#namespaces-available-for-new-registrations) describes the 14 currently public namespaces; the [live capability register](https://headlessdomains.com/api/v1/domains/capabilities) is authoritative for current launch phase and checkout support. Search results do not reserve a name or guarantee its final price. Partner names require provider preflight before registration.

For the platform's current search and registration workflow, read the [HeadlessDomains.com agent skill](https://headlessdomains.com/skill.md).

## Usage

Endpoint: `GET https://headlessdomains.com/api/v1/domains/search?q={query}`

### Request

- Method: `GET`
- URL: `https://headlessdomains.com/api/v1/domains/search`
- Query Parameters:
  - `q` (string, required): A candidate label or full name (for example, `myagent` or `myagent.agent`). A label can return results across supported namespaces; a full name targets its namespace.

### Example Request

```bash
curl -sS "https://headlessdomains.com/api/v1/domains/search?q=myagent"
```
