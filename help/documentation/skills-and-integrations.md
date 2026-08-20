---
title: Skills and Integrations Framework
description: Learn how skills and integrations work together in the concierge framework. Skills define behavior, while integrations connect to data and provide capability.
role: User, Admin
level: Beginner
---
# Skills and Integrations Framework {#skills-and-integrations}

An integration (formerly known as a tool) is a connection to a data source or backend. A skill is a behavior.

One integration can be used by many skills. One skill can use several integrations. You configure them independently and map them together.

## Skills

A skill is the behavior layer of a concierge. It is a named, reusable unit that defines a single job the concierge can do: what it handles, when it steps in, and how it responds. A skill holds no data of its own; it borrows capability from the integrations attached to it.

Every skill is made of five parts:

| Part | What it is |
| --- | --- |
| Name | The skill's identifier |
| Description | What the skill is for, its purpose in plain terms |
| Use when | The trigger condition. This is the routing signal that tells the concierge when to invoke this skill rather than another |
| Integrations | The specific tools this skill is permitted to call to do its job. A skill can only use what is attached here |
| Instruction file | The detailed instructions governing how the skill behaves and how it interprets a request, formats its response, and applies its guardrails |

How a skill behaves at runtime: when a user message arrives, the platform matches it against each active skill's "use when" trigger and routes the message to the matching skill. That skill then runs its instructions and calls only the integrations attached to it. Its instructions are composed into the concierge's overall runtime behavior alongside the brand profile and any other active skills.

A skill decides what to do and when. It does not itself connect to any data; that is the integration's role.

_Example of the Site Advisory skill_

![Site Advisory skill detail panel showing its description, Use when triggers, attached Knowledge Base Search integration, and skill instructions](assets/skills-and-integrations-1.png){width="800" zoomable="yes"}

## Integrations

An integration is the capability layer of a concierge. It is a connection to an external or backend system (a knowledge base, a content source, a live commerce catalog) that actually fetches data or performs an action. Where a skill is judgment, an integration is capability.

Every integration has these characteristics:

| Characteristic | What it means |
| --- | --- |
| Connection and credentials | An integration authenticates to its backend using its own configuration, for example, a commerce environment ID and API key. This config is what points it at the right data source |
| Exposed capabilities | An integration makes one or more callable capabilities available, the individual actions a skill can invoke. Commerce MCP, for instance, exposes product search, product details, variants, and facet discovery as separate capabilities |
| Reusable | One integration can be attached to many skills, and the same integration serves many concierges and customers. This reuse is the core efficiency of the framework |

How an integration behaves at runtime: when a skill fires and decides it needs data, it calls one of the integration's tools. The integration executes that call against the live backend and returns structured data to the skill, which the skill then uses to form its response.

An integration provides capability but exercises no judgment. It waits to be called by a skill, does the specific job asked of it, and returns the result.

### Capabilities and limits (the self-serve boundary)

- **Self-serve, no engineering:** Edit instructions, edit "use when" triggers, attach or detach existing integrations, enable or disable a skill, and connect a supported integration (like Commerce MCP with valid credentials).

- **Not self-serve, needs engineering:** Create a brand-new tool or connector that does not already exist in the catalog, add a new guardrail category the framework does not support, or change what data a backend exposes.

- **Trigger overlap between two skills is a configuration risk:** If two skills could plausibly fire on the same message, routing can be inconsistent. Write triggers to avoid genuine ambiguity rather than relying on the router to resolve it.

## Integrations available out of the box

Below are the four integrations shown in Composer's **Browse integrations** panel.

| Integration | What it does | Notes |
| --- | --- | --- |
| Knowledge Base Search | Source for a brand's product info, pricing, features, and documentation, populated through site crawl | This one is auto-created at concierge creation, populated by the site crawl |
| Content AI Search | Searches the brand's content via Content AI | An alternative content source; typically only one of Knowledge Base Search or Content AI Search is required at a time |
| Entity Linking/Product Catalog mapping | Resolves product or brand mentions in a user's message to specific catalog entities | Supporting integration, used alongside a search integration rather than alone |
| Commerce MCP | Adobe-managed Commerce MCP server: product search, details, variants, and facet/attribute discovery, backed by Adobe Live Search | Not in the baseline; added manually for Commerce use cases |

![Browse integrations panel showing four integration cards: Content AI Search, Entity Linking, Knowledge Base Search, and Commerce MCP](assets/skills-and-integrations-2.png){width="800" zoomable="yes"}

## Skills available out of the box

Four skills ship in the catalog. Each one lists its recommended integrations.

| Skill | What it is for | Recommended integrations |
| --- | --- | --- |
| Site Advisory | General brand questions: policies, FAQs, programs, how-to, and support | Knowledge Base Search, Content AI Search, and Entity Linking |
| Product Advisory | Discover and research products: name-based product cards and prose product questions | Knowledge Base Search, Entity Linking/Catalog mapping |
| Adobe Commerce Catalog Discovery | Search, browse, filter, and get full details on products against a live catalog | Commerce MCP tools: Search Commerce Products, Product Details, Product Variants, Product Facets, and Searchable Attributes |
| Adobe Commerce Product Comparison | Side-by-side comparison of two or more named products in a table for Commerce | Commerce MCP tools: Search Commerce Products, Product Details |

The two commerce skills are catalog-only capabilities and depend on the Commerce MCP integration, which is not part of the baseline. In a non-commerce concierge, Site Advisory and Product Advisory run against the auto-created Knowledge Base Search instead.

![Browse skills panel showing four skill cards: Product Advisory, Adobe Commerce Catalog Discovery, Adobe Commerce Product Comparison, and Site Advisory](assets/skills-and-integrations-3.png){width="800" zoomable="yes"}

## What is wired at concierge creation

When a concierge is created via one-click setup, the baseline is assembled for you.

| Wired at creation | Detail |
| --- | --- |
| Knowledge base (data) | The early crawl builds a knowledge base from the site's top 10 to 15 pages, found via the sitemap. This is the content store, not a skill or integration |
| Knowledge Base Search (integration) | Built-in integration, connected to the crawled knowledge base and used to search it. The crawl does not create this; it points at what the crawl produced |
| Site Advisory (skill) | Active in the baseline, wired to call Knowledge Base Search, which queries the crawled knowledge base |

## FAQ

**What is the difference between a skill and an integration?**

An integration is a connection to a data source or backend; it is what the concierge can reach out to, such as a knowledge base or a live commerce catalog. A skill is a behavior; it decides what the concierge does, when it does it, and which integrations it is allowed to use.

**Rule of thumb:** An integration is a capability; a skill is the judgment about when and how to use that capability.

**Can the same integration be used by more than one skill?**

Yes, and this is intentional. Commerce MCP's tools are shared across both Catalog Discovery and Product Comparison. Building an integration once and reusing it across many skills and many customers is the core efficiency of the 2.0 framework; it is what removes the per-customer custom build.

**Can a practitioner add an entirely new capability without engineering?**

Only if an integration for it already exists in the catalog. A practitioner can freely map, configure, and instruct any existing integration; that is self-serve. But if the capability requires a backend or connector that does not exist yet (a new API or a new data source type), that is an engineering task to build the integration first. Once it exists in the catalog, configuring it becomes self-serve again.

**How is this different from BC 1.0's single system prompt?**

In 1.0, behavior was driven by one large system prompt (the manifest), which was hard to edit safely and generally required engineering to change. In 2.0 the manifest still exists, but it is composed from modular pieces rather than written as one block. That is what makes behavior configurable by a practitioner and makes individual guardrails and instructions legible and auditable instead of buried in one prompt.

**What exactly does the early crawl create?**

The crawl creates a knowledge base, a searchable store of the site's content, built from the top 10 to 15 pages found via the sitemap. This is the data layer only. The crawl does not create a skill or an integration; it produces the content that they later act on.

**If the crawl creates the knowledge base, what is the Knowledge Base Search integration?**

Knowledge Base Search is a built-in integration whose job is to search that knowledge base. The knowledge base is the data; Knowledge Base Search is the capability that queries it. They are two separate things: one is the content, the other is the tool that reads the content. It is a common mistake to treat them as the same; they are not.

**How does the concierge answer a general question at creation, end to end?**

Three layers work in sequence, and they map exactly onto the skill, integration, and data model:

- The early crawl creates the knowledge base from the site's pages (data).
- The built-in Knowledge Base Search integration searches that knowledge base (integration).
- The Site Advisory skill is wired to call Knowledge Base Search (behavior).
