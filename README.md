# HeadlessDomains.com Agent Skills

[![Agent Skills](https://skills.sh/b/headlessdomains/skills)](https://skills.sh/headlessdomains/skills)

Welcome to the HeadlessDomains.com Agent Skills repository. These skills help compatible agents discover and use the Headless Domains API.

## About

HeadlessDomains.com offers headless names for agents, tools, services, and systems operating on the agentic web. A name can give a working service a public identity and a place to maintain its operator information, capabilities, and official endpoints. Compatible agents can use Headless Domains and SkyInclude API or CLI workflows to inspect these names. Registering a name does not deploy a service, prove its claims, or authorize it to act.

- **Author/Owner:** headlessdomains
- **Official site:** [HeadlessDomains.com](https://headlessdomains.com/)
- **Current namespace catalog:** [HeadlessDomains.com/extensions](https://headlessdomains.com/extensions)
- **Live registration capabilities:** [Public capability register](https://headlessdomains.com/api/v1/domains/capabilities)
- **OpenAPI specification:** [Headless Domains API](https://headlessdomains.com/openapi.json)

## Namespaces available for new registrations

The HeadlessDomains.com catalog and public capability register currently list these 14 namespaces as public with checkout enabled. An individual second-level name may still be unavailable, reserved, or premium. Check the [live capability register](https://headlessdomains.com/api/v1/domains/capabilities), search for the specific name, and obtain a current quote before any purchase. The source column distinguishes native namespaces from partner-backed namespaces; partner availability and pricing require provider preflight.

| Namespace | Source | Good fit for |
| --- | --- | --- |
| [`.agent`](https://headlessdomains.com/agent) | Native | Autonomous agents and agent teams that need a persistent public identity. |
| [`.chatbot`](https://headlessdomains.com/chatbot) | Native | Conversational assistants, support bots, and voice or chat services. |
| [`.boss`](https://headlessdomains.com/boss) | Native | Human operators, founders, managers, and the agents or services they direct. |
| [`.factory`](https://headlessdomains.com/factory) | Native | Build systems, production workflows, maker platforms, and autonomous services that make things. |
| [`.protocol`](https://headlessdomains.com/protocol) | Native | APIs, standards, networks, specifications, and coordination services. |
| [`.bpo`](https://headlessdomains.com/bpo) | Partner | Outsourced and AI-enabled business processes such as support, accounting, and recruiting. |
| [`.manifest`](https://headlessdomains.com/manifest) | Partner | Machine-readable capabilities, configuration, policies, and tool discovery. |
| [`.c`](https://headlessdomains.com/c) | Partner | Shared agent operations, creator tools, community services, and product identities. |
| [`.zen`](https://headlessdomains.com/zen) | Partner | Focused agent workflows, mindfulness services, and creative tools. |
| [`.yolo`](https://headlessdomains.com/yolo) | Partner | Experimental agents, creative services, and new projects. |
| [`.1`](https://headlessdomains.com/1) | Partner | A primary agent, flagship service, or other central identity. |
| [`.done`](https://headlessdomains.com/done) | Partner | Task completion, service delivery, and workflow systems. |
| [`.tx`](https://headlessdomains.com/tx) | Partner | Transactions, exchanges, settlement, and agentic commerce services. |
| [`.hey`](https://headlessdomains.com/hey) | Partner | Communication services, community tools, and approachable agent identities. |

## Available Skills

1. **`domain-search`**: Search a candidate name across supported namespaces, then check current capability and quote data before registration.
2. **`domain-lookup`**: Inspect public identity, profile, manifest, and available commerce metadata for a registered name.
3. **`domain-register`**: Register through an authorized MPP flow, or GFA Gems where the agent API supports it, after live preflight. Supported native namespaces also expose a separate x402 v2 registration route for Base USDC when operational; partner agent registration uses standard MPP and provider preflight.
4. **`bio-sync`**: Update an owned or managed domain's hns.bio profile with authenticated API access.

## Current agent documentation

These repository skills are concise entry points. The [site Markdown index](https://headlessdomains.com/llms.txt) and [agent quick start](https://headlessdomains.com/agent-start.md) point to the current HeadlessDomains.com guides. Read the [live capability register](https://headlessdomains.com/api/v1/domains/capabilities) for the selected namespace before relying on a payment method or network.

Site guides: [primary skill](https://headlessdomains.com/skill.md), [authentication](https://headlessdomains.com/auth.md), [MPP](https://headlessdomains.com/skill_mpp.md), [GFA Gems](https://headlessdomains.com/skill_gems.md), [native x402](https://headlessdomains.com/skill_x402.md), [profile](https://headlessdomains.com/skill_profile.md), [Handshake DNS](https://headlessdomains.com/skill_hns.md), [domain actions](https://headlessdomains.com/skill_actions.md), [agent claiming](https://headlessdomains.com/skill_claimagent.md), [transfer](https://headlessdomains.com/skill_transfer.md), [marketplace](https://headlessdomains.com/skill_marketplace.md), [BMOS](https://headlessdomains.com/skill_bmos.md), [trademark claims](https://headlessdomains.com/skill_trademarkclaim.md), [runtime](https://headlessdomains.com/skill_runtime.md), and [inbox](https://headlessdomains.com/skill_inbox.md). The website guides and API contracts define current route behavior; the four installable GitHub skills summarize them.

## Installation

These skills conform to the `skills.sh` standard. To install them for your autonomous agent, simply run:

```bash
npx skills add headlessdomains/skills
```

You can also specify a single skill to install:

```bash
npx skills add headlessdomains/skills --skill domain-search
```

## Contributing

For details on the API contracts and further integration possibilities, please refer to our [OpenAPI Spec](https://headlessdomains.com/openapi.json).
