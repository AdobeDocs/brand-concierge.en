---
title: Brand Concierge overview
description: Learn what Brand Concierge is, how its main components fit together, and the glossary of key terms you will encounter throughout the Composer interface.
---
# Brand Concierge overview

Brand Concierge is an agentic platform that enables businesses and brands to launch personalized conversational experiences on their customer-facing surfaces: websites, mobile apps, and other digital properties. Every conversation is grounded in the brand's own content and guardrails, and integrations let insights from those conversations flow into the rest of the brand's ecosystem, such as Marketo Engage.

## Main components

A Brand Concierge deployment has two major pieces:

| Piece | What it is |
|---|---|
| **Visitor Experience** | The brand-facing surface, such as a website or mobile app, where visitors engage with the concierge and get responses in real time. |
| **Composer** | The practitioner interface used to design concierge experiences and manage concierges, integrations, configurations, evaluations, deployment, and analytics. |

## Composer modules

Within Composer, the major modules are:

- [User and access management](../user-and-access-management/add-a-user-to-the-org.md)
- [Knowledge source creation and management](../knowledge-sources/knowledge-sources.md), shared across concierges
- [Concierge management](../concierge-management/concierge-management.md): integrations, skills, concierge instructions, tone and voice, visual style, and chat components
- [Evaluation](../evaluation/evaluation.md)
- [Deployment](../deployment/deployment.md)
- [Go-live checklist](../go-live-checklist/go-live-checklist.md)
- [Analytics](../analytics/analytics.md)

## How the pieces connect

A knowledge source (content) is queried by an integration (connection), which is called by a skill (behavior), all wrapped in a concierge (the overall experience) that visitors interact with.

## Glossary

These terms appear throughout Composer's interface.

| Term | Definition |
|---|---|
| **Concierge** | The AI chat experience itself: one per brand, website, or use case. An account can have several. |
| **Composer** | The interface used to build and manage concierges, distinct from what website visitors see. |
| **Knowledge source** | The content a concierge is permitted to use when answering questions, such as website pages or a product list. Without one, the concierge has nothing to answer from. |
| **Integration** | A connection to a system that can retrieve information, such as website content or a live product catalog. |
| **Skill** | A specific capability the concierge can perform, such as answering general questions, comparing products, or booking a meeting. A skill uses one or more integrations to perform its function. |
| **Guardrails** | Rules defining what the concierge should not do or discuss, such as competitors or legal advice. |
| **Evaluation** | A structured test consisting of sample questions paired with expected answers, used to assess concierge performance. |
| **Datastream ID** | A technical identifier that specifies where visitor activity data is sent within Adobe systems. It is provided by the IT or analytics team. |
| **Sandbox** | An isolated workspace within an organization. An organization may have more than one; each can hold multiple concierges. |
| **IMS org** | Adobe's term for an organization's overall account. |
| **MCP** (for example, Commerce MCP) | An Adobe-managed connector to a specific system, such as a live product catalog, configured using codes or keys provided by IT or the commerce team. |
| **CJA (Customer Journey Analytics)** | Adobe's analytics product. Brand Concierge automatically provisions a starter dashboard here with no additional setup required. |

>[!NOTE]
>
>Marketers can usually skip [User and Access Management](../user-and-access-management/add-a-user-to-the-org.md) entirely (someone in IT completes it once) and start at [Knowledge Sources](../knowledge-sources/knowledge-sources.md). Return to user and access management only when setting up new teammates.
