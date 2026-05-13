---
title: Frequently Asked Questions
description: Get answers to frequently asked questions about Adobe Brand Concierge.
role: User,Admin
level: Beginner
TQID: https://experienceleague.adobe.com/R-s7wgJ5jtCXnBiLMVdW-6db7cTgSgaJwq4x6IlEJqY
product_v2:
  - id: b6ee73fe-bdc6-47d9-99a2-80194514dd40
    internal-label: Brand Concierge
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
    internal-label: Customer profiles
---
# Frequently asked questions

Read this section for answers to frequently asked questions regarding Brand Concierge.

## General

### Why use Brand Concierge? What problem does it solve?

More research happens on external AI tools (for example, ChatGPT, Gemini) instead of on brand websites. Visitors increasingly want to "get to the point"—for example, "Tell me about X," "Can I do Y?" Brand Concierge helps you keep that conversation on your site: when visitors land on your pages (including from an AI assistant), they can continue the conversation with an assistant trained on your content. You deliver a consistent, on-brand experience instead of losing them to generic answers elsewhere.

### How is Brand Concierge different from chatbots?

Brand Concierge stands apart from traditional chatbots by leveraging generative AI that is specifically trained on your organization's content and customer data, rather than relying on scripted answers or generic web results. This enables the assistant to provide personalized responses informed by individual customer behavior, deeply integrate with your Adobe tools and data, continuously learn from each interaction, and accurately interpret customer intent beyond basic keyword matching.

### Can I use Brand Concierge for both B2C and B2B?

Yes. Use cases include:

* **B2C:** Product discovery, shopping assistance, customer support, personalized recommendations.
* **B2B:** Guided evaluations, feature comparisons, meeting scheduling, sales representative routing, consultation booking.

### What industries can use Brand Concierge?

Brand Concierge can be used across a wide range of industries, including retail and e-commerce, travel and hospitality, financial services, healthcare (with compliance controls), media and entertainment, and technology and software. Essentially, any industry that helps customers find information and make decisions can benefit from implementing Brand Concierge.

## Data and privacy

### Is customer data safe?

Yes. Brand Concierge ensures customer data is safe by adhering to GDPR and CCPA compliance, processing data on Adobe's secure infrastructure, providing you with control over data usage, and safeguarding conversations through encryption and audit logging.

All conversations happen on your properties, not third-party servers.

### What data sources can I connect?

You can connect the following types of data sources to Brand Concierge:

| Data Source Type | Available Sources/Details |
|------------------|---------------------------|
| **Product and content** | Product catalogs<br>Inventory systems<br>Knowledge bases and documentation<br>Website content via CSV URL upload<br>Adobe Experience Manager content<br>Adobe Commerce data |
| **Customer data** | Adobe Experience Platform profiles<br>Adobe Analytics behavior data<br>First-party customer attributes<br>Third-party APIs (configured) |
| **CSV file format** | One column containing website URLs<br>Brand Concierge crawls URLs and extracts content automatically<br>Processing status updates in real-time<br>Multiple CSV files can be uploaded for different content areas |

All data follows your governance rules.

### Can customers opt out of personalization?

Yes. Customers who opt out receive helpful responses without behavioral personalization. You configure opt-out handling to match your privacy policies.

### Are there consent or privacy implications?

Yes. **Conversation data:** If the conversation includes personal or identifiable information, collection, storage, and use must comply with your consent and privacy policy (for example, GDPR, CCPA). **Analytics:** When Concierge sends events to Experience Platform or analytics, those events may be subject to your existing consent and governance (for example, consent strings, data usage labels). We recommend treating Concierge like any other first-party digital experience: ensure your site's consent banner and preferences cover conversational and chat data and analytics, and align event data to your consent strategy. Have legal and compliance review before go-live.

## Profiles and personalization

### Does Concierge use customer profiles (for example, Real-Time CDP) to tailor responses? What if the visitor is partway through a journey?

In the current scope, Concierge is focused on anonymous visitors: it answers from the conversation and your knowledge base (website and catalog), not from a live lookup of identity or journey state in Real-Time CDP. Roadmap capabilities include lead nurturing, handover to sales, and retargeting, which will align more with known profiles and journey context. Tailoring responses by "does this visitor have a profile?" or "where are they in a journey?" is a future enhancement. For now, the experience is consistent for anonymous visitors.

## Rollout and timeline

### How long does it typically take to go live?

With parallel work and active collaboration, many implementations reach go-live in about 6-9 weeks. Staging can start quickly once your inputs (URLs, catalog, brand guidelines) are ready. After agreement and production setup, you move through quality tuning and a controlled rollout (for example, 5% then scaling to 100% over about a week).

## Configuration and control

### How do I control brand voice?

You can control your brand voice directly in the UI by configuring elements such as tone (ranging from formal to casual), language (from simple to technical), and personality (for example, helpful, enthusiastic, or professional). Additionally, you can define response patterns using templates and examples, and establish guardrails to enforce compliance rules and boundaries. Begin with Adobe's reference prompts and tailor these settings to reflect your brand's unique identity.

### What happens when Brand Concierge can't answer a question?

You can configure fallback behaviors to determine how Brand Concierge responds when it cannot answer a question. Options include displaying a graceful "I can't help with that" message, suggesting alternative questions, linking to self-service resources, or automatically escalating the inquiry to a human agent. Choose what works best for your brand.

### Can I customize the visual design?

Yes. Customize all visual elements, including:

* Colors and branding
* Fonts and typography
* Button styles
* Widget positioning
* Card layouts
* Response formatting

SDKs provide default components and full customization options.

### How long does setup take?

The length of setup can depend on your type of implementation. A basic implementation that includes an existing product catalog, standard FAQ content, and default settings can take around 3-5 days to setup. On the other hand, advanced implementations with custom integrations, extensive personalization, complex workflows, and custom compliance rules can take around 2-4 weeks to complete.

### How does the preview and testing work?

Brand Concierge includes built-in testing tools:

| Testing Tool | Features |
|--------------|----------|
| **Preview mode** | Simulate customer conversations<br>Adjust settings in real-time<br>See changes instantly<br>Share preview links with your team |
| **Tester View** | Rate responses with thumbs up/down<br>Provide structured feedback across 4 categories<br>Add detailed comments<br>Track feedback in dashboard |

All testing happens before you deploy to customers.

### Can customers schedule meetings with our team?

Yes, customers can schedule meetings with your team using the Meeting Booking skill. To enable this feature, activate the skill in Skills Configuration, define activation intents (such as "speak with sales"), connect your calendar or scheduling system, and set your availability and meeting types. Once configured, customers can request meetings during conversations, and Brand Concierge will facilitate the scheduling process without requiring them to leave the chat.

### Who handles the prompt engineering?

Adobe consultants handle prompt engineering in the background:

1. You answer configuration questions in the Skills page.
1. Provide product knowledge, business rules, and avoid keywords.
1. Submit your inputs.
1. Adobe consultants use your answers to engineer optimized prompts.
1. Changes reflect in your concierge automatically.

This ensures your concierge uses best-practice AI prompt patterns while maintaining your specific brand requirements.

## Brand expression and tone

### If I set "playful and enthusiastic" in Brand Expression, will the AI overdo it?

It can. Some customers have reported that the AI tends to overdo enthusiasm when set to "playful and enthusiastic"—for example, double exclamation points or strong superlatives. For regulated or medical audiences (for example, pharma, early life nutrition), we recommend dialing down enthusiasm and playfulness while keeping the tone conversational and casual. Use moderate settings and tune based on feedback; for regulated industries, lean toward "conversational" rather than "enthusiastic."

## Performance and analytics

### How do I measure success?

You can measure success using the Brand Concierge dashboard. Use the dashboard to track metrics such as:

| Metric | What It Tracks |
|--------|----------------|
| **Engagement** | Conversation volume, session length |
| **Satisfaction** | Sentiment scores, feedback ratings |
| **Conversion** | Purchase rates for assisted vs. unassisted |
| **Topics** | Most common questions and requests |
| **Handoff** | Escalation rates and reasons |
| **Performance** | Response accuracy, resolution time |

You can also integrate with Adobe Analytics for deeper analysis.

### What should I do if sentiment drops?

If you notice a drop in sentiment, investigate the underlying causes by reviewing recent failed queries, checking for content gaps, analyzing negative feedback, testing for appropriate tone, and verifying any technical issues. Once the root causes are identified, promptly address them and continue to monitor for improvement.

## Integration and technical

### Do I need other Adobe products?

No, but they enhance performance:

| Integration Option | Capabilities |
|-------------------|--------------|
| **Standalone** | Works with your product catalog and content |
| **With Adobe Experience Platform** | Unified customer profiles<br>Advanced personalization<br>Cross-channel consistency |
| **With Adobe Commerce** | Real-time inventory<br>Order history<br>Cart integration |
| **With Adobe Experience Manager** | Content management<br>Dynamic updates<br>Multi-site support |

### What if my site isn't on Adobe?

Brand Concierge works with any platform. The JavaScript SDK integrates with any website, and mobile SDKs work with any app backend.

### How does agent handoff work?

When agent handoff is triggered, Brand Concierge transfers the full conversation history, customer profile and ID, identified intent, details of products discussed, and any resolution attempts to the agent. This ensures that agents have complete context and can continue the conversation seamlessly, without requiring customers to repeat information.

### Can I support multiple languages?

Yes. Configure language support per assistant based on your customer base. Brand Concierge detects customer language and responds accordingly.
