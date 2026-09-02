---
title: Manage a concierge
description: Learn how to create a Brand Concierge from a website, configure its integrations, skills, instructions, tone, and visual style, and test it before deployment.
toc: true
---

# Manage a concierge

A concierge is created from a brand website and can be refined with integrations, skills, instructions, tone and voice settings, visual styles, and chat components. Use the preview to test changes before you deliberately deploy the concierge to visitors.

## Overview

| Item | Details |
|---|---|
| Primary user | Marketer using self-serve configuration |
| Additional support | Commerce and B2B integrations may require codes, keys, or setup from an IT, commerce, or sales team |
| Typical time | About 5 minutes to create a baseline concierge; ongoing time is required for refinement and testing |
| Deployment | Separate from creation; creating a concierge does not make it visible to website visitors |

>[!NOTE]
>
>A sandbox can contain multiple concierges. Each concierge has its own configuration, and concierges can be deleted from the concierge list.

## Create a concierge

Creating a concierge from a single website URL is the recommended starting point for a first-time user. The system creates a working baseline without requiring manual configuration.

1. Enter the brand's website URL and select **Create**.

1. Review the generated brand expression. The system analyzes the website's tone and proposes attributes such as formality, warmth, playfulness, and energy. Adjust the values as needed and select **Continue**.

1. Review the generated brand profile. The profile can include the brand goal, products and services, target audience, brand values, key differentiators, and common use cases. Edit the profile as needed and select **Continue**.

1. Review the generated starting instructions, guardrails, and suggestions. For example, guardrails can exclude legal topics, compliance topics, or competitor discussions, while suggestions can provide follow-up prompt ideas. Edit the content as needed and select **Save**.

1. Wait for the system to apply the baseline configuration. The system also creates a default visual style using colors and fonts drawn from the website and activates baseline skills and integrations, such as a general question-and-answer skill connected to website content.

1. Test the concierge in the preview. Desktop and mobile views are available. Select **New** to restart a test conversation.

>[!IMPORTANT]
>
>Creating a concierge does not make it visible to visitors. Deployment is a separate, deliberate step. You can revise the configuration any time before deployment.

## Understand what is configured automatically

The following items are configured automatically when you create a concierge:

| Item | Configuration |
|---|---|
| Knowledge Base content | Built from the site's top pages through a background crawl that starts automatically |
| Knowledge Base Search integration | Automatically points to the crawled content |
| Site Advisory skill | Active by default so the concierge can answer general questions immediately |

## Understand skills and integrations

Composer, the interface used to build and configure a concierge, uses two related concepts:

- **Integration:** A connection to a data source, such as website content or a live product catalog. An integration retrieves information but does not make decisions by itself.
- **Skill:** A behavior that determines what the concierge does, when it does it, and which integrations it can use.

An integration can serve multiple skills, and a skill can use multiple integrations. For example, a single product catalog connection can support several product-related use cases without being rebuilt for each skill.

## Configure integrations

Select **Browse Integrations** to view the available integration catalog.

| Integration | Purpose | Notes |
|---|---|---|
| Knowledge Base Search | Searches website content | Configured automatically when the concierge is created |
| Content AI Search | Searches AEM Sites content | Relevant for customers of AEM Sites as a Cloud Service |
| Product Catalog | Displays product cards or links from an uploaded product list | Intended for smaller, non-commerce catalogs |
| Commerce MCP | Connects to a live Adobe Commerce catalog for product search, product details, and comparisons | Not enabled by default; requires codes or keys from the commerce or IT team |
| Meeting Booking | Allows visitors to book a meeting with a sales representative | B2B capability |
| Live Chat | Connects visitors with a live sales representative | B2B capability |

### Turn on and configure an integration

1. Open the integration tile and select **Edit**.

1. For **Knowledge Base Search**, select the knowledge source to search. You can rename the connection, for example `Website content`.

1. For **Commerce MCP**, enter the following values supplied by the Adobe Commerce or IT team and connect:
   - Environment ID
   - Website code
   - Store code
   - Store view code
   - API key

1. Select **Save**. The integration is shown as connected and can be previewed, edited, or removed.

You can add more than one instance of the same integration, such as instances that point to different knowledge sources. A skill can be configured to use a specific integration instance.

### Integration information that requires confirmation

The following details were not established in the source material and should be confirmed before publication as product documentation:

- The full production URL for signing in to `experienceplatform.adobe.com`.
- Whether a concierge has a limit on the number of integration instances.
- The roadmap and process for custom or bring-your-own integrations, which were mentioned as planned but not detailed.

## Configure skills

Skills determine what a concierge can do for visitors. Select **Browse Skills** to view the available skill catalog.

| Skill | Purpose | Required integration or configuration |
|---|---|---|
| Site Advisory | Answers general brand questions, including FAQs, policies, pricing, how-to guidance, and support topics | Website content; active by default |
| Adobe Commerce Catalog Discovery | Searches, browses, filters, and retrieves details about products from a live catalog | Commerce MCP integration |
| Adobe Commerce Product Comparison | Provides a side-by-side comparison of named products | Commerce MCP integration |
| Book Meeting with Sales | Suggests and facilitates booking a meeting | Meeting Booking integration |
| Live Chat with Sales | Suggests and facilitates a live chat handoff | Live Chat integration |

### Turn on and configure a skill

1. Open the skill tile and select **Modify**.

1. Set the skill's name, description, and intents. Intents are the phrases or topics that should trigger the skill, such as `pricing` or `compare products`. You can add multiple intents.

1. If the skill requires an integration, attach the required integration. For example, a commerce skill requires Commerce MCP. Alternatively, select **Use recommended** to let Composer select an appropriate integration automatically.

1. Review and edit the skill's starting instructions as needed.

1. Select **Save** and test the change in the live preview.

>[!TIP]
>
>If two skills could respond to the same question, routing can become inconsistent. Keep skill triggers distinct and specific instead of using overlapping intents.

### Custom skill information that requires confirmation

The source material mentions a planned capability for creating fully custom skills but does not provide a roadmap or process. Confirm availability and authoring steps before documenting this capability as supported.

## Add concierge instructions

Use the concierge instructions field to keep responses aligned with brand guidelines. Instructions can define:

- Trademark usage
- Response structure
- Topics to avoid

Type instructions directly into the text field. When you save the instructions, the concierge automatically updates its behavior. Test the result immediately in the live preview.

The same area also includes the following editable content:

- **Guardrails:** Behaviors or topics the concierge should avoid.
- **Suggestions:** Follow-up prompt ideas that can be shown after a response.

## Configure tone and voice

Tone and voice settings control response length and tone attributes, including:

- Formal or casual
- Warm or neutral
- Playful or serious

Selections are saved automatically. Test the result in the live preview after making changes.

## Configure the visual style

Visual style settings control the concierge's appearance, including but not limited to:

- Colors
- Fonts
- Welcome message text
- Legal disclaimer text
- Card colors

Edit the settings in the user interface and use the live preview to review changes. Select **Save** to make the changes permanent.

>[!NOTE]
>
>The source material states that a fully custom look and feel may be possible beyond the options available in the user interface, through a separate deployment script. The deployment-script procedure was not included and should be documented separately after it is confirmed.

## Configure chat components

Chat components control the individual elements that visitors see in the chat window. Select a component in the user interface to open its settings in a side panel.

| Component | What it controls |
|---|---|
| Chat bubble | The appearance of visitor messages and concierge messages |
| Start prompt or prompt pills | Suggested opening questions, especially those shown on mobile |
| Follow-up suggestions | Suggested next questions after a response |
| Input bar | The message box visitors use to enter a question |
| Citations | Whether and how source references appear in a response |
| Feedback | The thumbs-up or thumbs-down rating control shown after each response |
| Product card | The layout and styling of product cards, including colors and buttons |

## Configure B2B capabilities

Meeting Booking and Live Chat allow visitors to book meetings with sales representatives or start a live chat with a representative. These capabilities are powered by a companion product called Sales Qualifier.

### Roles and responsibilities

- **Marketer:** Configures the skill and integration in Brand Concierge.
- **Sales representative:** Connects their own calendar and configures availability.

### Set up Meeting Booking or Live Chat

1. In **Browse Integrations**, open **Meeting Booking** or **Live Chat**. By default, everyone in the organization is available as a potential team member; no separate step is required to add team members at this stage.

1. Have each sales representative sign in to `experienceplatform.adobe.com`, open **Sales Qualifier**, and go to **Profile Settings**.

1. Have each representative connect a calendar, such as Outlook. Microsoft Teams can optionally be included. The representative can also set the meeting invitation subject and email text.

1. Configure availability. Availability is pulled from the calendar by default and can be further limited by:
   - Meeting length
   - Buffer time between meetings
   - Minimum required notice
   - Specific available time windows

1. Configure Live Chat availability separately, using a similar process.

1. In Brand Concierge, open **Managed Members** and confirm that the representatives are shown as available.

1. Turn on the **Meeting Booking** and/or **Live Chat** integration.

1. Go to **Browse Skills** and select **Book Meeting with Sales** and/or **Live Chat with Sales**. Set the triggers, attach the corresponding integration, and save the skill.

1. Select **Simulate** to test the end-to-end experience. Enter a sample question and confirm that it routes to the correct skill and engagement flow.

### Behavior after deployment

When the capabilities are live:

- Incoming live chats appear to available representatives in real time.
- Booked meetings appear in a meetings view.
- A Meeting Performance Report is available in analytics.
- Meeting and chat engagements are sent to Marketo as activities, alongside existing activity data.

### B2B information that requires confirmation

The source material identifies the following items as unresolved:

- Live Chat does not have its own analytics dashboard; this was described as a product gap in progress rather than a documentation gap.
- The exact `experienceplatform.adobe.com` sign-in path for Sales Qualifier.
- Whether Meeting Booking and Live Chat require separate licensing or entitlements.

## Share a preview link

A shareable preview link lets stakeholders review and interact with a concierge without Composer access and without deploying the concierge to a live website.

1. From the concierge preview screen, generate a shareable preview link.

1. Share the link with reviewers.

1. Reviewers can interact with the concierge through the link without signing in to Composer.

### Preview-link information that requires confirmation

Confirm the following details before publishing this procedure as a complete product workflow:

- The exact location and label of the share action in the user interface.
- Whether preview links expire or can be revoked.
- Whether preview-link usage is tracked separately from live analytics.

## Test before deployment

Use the preview or simulation experience after each significant configuration change. At minimum, verify the following:

- The concierge answers general questions from the intended website content.
- Each skill responds only to its intended triggers.
- Required integrations are connected and point to the correct data source.
- Product searches and comparisons use the intended Commerce MCP or Product Catalog instance.
- Meeting Booking and Live Chat route to the intended representatives.
- Tone, voice, instructions, guardrails, and suggestions produce the expected responses.
- Visual styles and chat components display correctly on desktop and mobile views.
- Stakeholders can review the experience through the shareable preview link, if one is used.
