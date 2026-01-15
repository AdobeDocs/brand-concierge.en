---
title: Documentation and FAQ
description: Learn how to configure and use key features of Brand Concierge.
role: User,Admin
level: Beginner
---
# Brand Concierge help

Learn how to configure and use key features of Brand Concierge. Find answers to common questions about setup, data integration, privacy, customization, performance measurement, and technical requirements.

## Key features {#key-features}

Brand Concierge has a number of key features including:

* **Guided onboarding:** Follow a step-by-step setup for knowledge, skills, and brand expression. 
* **Knowledge integration:** Upload and manage sources like CSV files with website links. 
* **Configure skills** Integrate skills such as product advisory. 
* **Control branding:** Adjust the voice, tone, and response length to meet your particular brand's standard and approach.
* **Preview and iterate:** Use a comprehensive preview interface to simulate conversations and conduct live adjustments. 
* **Feedback system:** Use a feedback system that allows users to provide thumbs up or down ratings, along with detailed feedback forms covering response coverage, tone, quality, and features.
* **Analytics dashboard:** Take advantage of an analytics dashboard powered by Customer Journey Analytics for metrics like conversations, sentiment, and engagement.

## Get started {#getting-started}

You can access Brand Concierge from the Adobe Experience Cloud dashboard. At a high level, you perform these tasks on the Homepage walkthrough:

1. [Create a concierge](#homepage)
1. [Add knowledge sources](#knowledge-sources)
1. [Configure skills](#skills-configuration)
1. [Specify your Brand Expression](#brand-expression).

For a video tutorial, see [Create your first concierge](../getting-started/create-first-concierge.md)

The following sections describe each task and the interface options in detail.

## Create a concierge {#homepage}

The Brand Concierge Homepage is designed for ease of use and efficiency, guiding you through essential setup steps with a dedicated first-time user walkthrough. A prominent top banner outlines key actions such as specifying your concierge's name and purpose, adding knowledge sources, configuring relevant skills, and defining your brand expression. 

As you progress, a visual tracker clearly displays which setup components have been completed and highlights any remaining tasks. To further support your efforts, the Homepage features an inspirational section with videos and demonstrations of concierge capabilities, such as product recommendations. You also have quick access to Experience League documentation for more in-depth technical insights. 

Once setup is complete, a configuration summary provides a comprehensive view of your details, organized with tabs to facilitate ongoing adjustments and refinements.

**Key elements**

* **First-Time User Walkthrough**: A top banner with steps to set up your concierge (name/purpose, knowledge sources, skills, brand expression).
* **Progress Tracker**: Visual indicators of completed vs. pending setup components. 
* **Inspirational Section**: Videos and demos showcasing concierge capabilities (for example, product recommendations).
* **Documentation Links**: Quick access to Experience League resources for deeper tech insights.
* **Configuration Summary**: Post-setup view of all details, with tabs for refinement.

**To create a concierge**

1. Navigate to the walkthrough banner, then click **[!UICONTROL Get started]**. 
1. Enter a name for your concierge and define its purpose (for example, _Recommend personalized products_).
1. Follow the guided steps to proceed.
1. Once setup is complete, return to the Homepage to monitor or edit your concierge.

>[!TIP]
>
>Brand Concierge automatically saves your progress. An incomplete setup may limit functionality but will not block any attempts to preview.

### Knowledge Sources {#knowledge-sources}

[!UICONTROL Knowledge Sources] help you manage the data sources that power your concierge's answers. You can access [!UICONTROL Knowledge Sources] after you upload your initial files. [!UICONTROL Knowledge Sources] has a number of key elements to consider, such as:

* **Source List:** Displays all uploaded items, such as CSV files with website links, and indicates their status as either processed or pending.
* **Upload Interface:** Allows you to drag and drop or browse for CSV files that contain URLs, which the system will crawl to extract knowledge.
* **Connection Options:** Enable you to link specific knowledge sources to relevant skills for more targeted use.

**To add a knowledge source** 

1. From the Homepage, click **[!UICONTROL Knowledge Sources]**.

1. Name the knowledge source.

1. Click **[!UICONTROL Add]** to upload a CSV file. 

   Ensure that it includes a column for website URLs.

1. Allow for a few moments for processing. 

   This step resolves fairly quickly as status updates in real-time.  

1. Once added, return to the Homepage. 

   By this point, you should see the new source added to the Homepage.

   Use the Homepage to edit or delete your knowledge sources as needed. You can also reconnect a knowledge source if any changes occur.

### Configure skills {#skills-configuration}

Use the [!UICONTROL Skills Configuration] interface to shape your concierge's expertise by configuring skills like **Product Advisory**. Answer the questionnaire to provide inputs that Adobe consultants will later use for prompt engineering. Skills Configuration has a number of key elements to consider, such as:

* **Skill Selector:** You can choose from available skills, such as Product Advisory for making product recommendations.
* **Questionnaire:** You will complete a series of prompts to provide product knowledge, business rules, keywords to avoid, and source connections.
* **Preview:** You have the option to make live tweaks and see how your adjustments impact responses, with links to the preview page.
* **Enable Meeting Booking:** You can enable visitors to schedule meetings directly with business representatives.

**To configure skills**

1. Navigate to the progress tracker in the Homepage, then click **[!UICONTROL Configure skills]**.
1. Select a skill (for example, Product Advisory).
1. Answer the ensuing configuration questions. 

   Question examples include: _What should the concierge know about products?_, _What business rules should be followed?_, _Which keywords should be avoided?_

1. Connect relevant [knowledge sources](#knowledge-sources).
1. Enable additional features (meeting booking).
1. Submit for processing.

### Brand expression {#brand-expression}

You can use the _[!UICONTROL Brand expression]_ interface to customize the personality and style of your concierge's responses. You can access Brand Expression from the setup stages or through the preview sidebar for ongoing changes.

With Brand Expression, you can use sliders to customize your concierge's voice and tone settings. You can select from options such as "Friendly", "Professional", and "Energetic". Additionally, you can configure response lengths to your liking. You can set your concierge to return short, medium, or long outputs, depending on your brand's vision.

**To customize your brand expression**

1. From the Homepage, click **[!UICONTROL Customize Brand Expression]**.
2. Next, configure your brand's voice, tone, and preferred response length.
3. Select **[!UICONTROL Save]** to ensure that the changes are reflected in future responses.

### Preview and test {#preview-and-test}

Test your concierge before launching to customers using the Preview and Tester View modes.

>[!BEGINTABS]

>[!TAB Preview mode]

Use the Preview mode to simulate conversations while making real-time adjustments.

1. After your setup, navigate back to the Homepage and click **[!UICONTROL Preview]**.
1. Use the chat interface to input your query (for example, _Recommend a laptop under $1000_).
1. Review concierge responses.
1. Use the right-hand panel to adjust your brand expression settings.
1. Click **[!UICONTROL Share]** to generate link for team feedback.

>[!TAB Tester view]

Use the Tester view to gather structured feedback on concierge performance and simulate the end-user experience.

1. From preview, click **[!UICONTROL Tester View]**.
1. Use the Tester view to simulate end-user conversations.
1. Use the thumbs up and down mechanism to rate each response that you receive.
1. Complete feedback form for thumbs down:
   **Response coverage:** Did it address the intent?
   **Brand tone:** Aligned with personality?
   **Response quality:** Clear and structured?
   **Response features:** Helpful follow-ups?
1. Add comments and specific observations.
1. Submit feedback for dashboard review.

>[!ENDTABS]

### Feedback {#feedback}

After testing, you can use the feedback tab in the Homepage to provide feedback and detailed reviews. 

The feedback section provides several important features to help you monitor and evaluate your Brand Concierge's performance. The following elements are available:

* **Performance Snapshot:** Displays cards summarizing key metrics, including total conversations, unique users, sentiment trends, and engagement rate.
* **View Report Button:** Allows you to open a dashboard powered by Customer Journey Analytics for in-depth access to advanced analytics and performance metrics.
* **Feedback List:** Presents a table of feedback sessions. You can click on individual rows to view the full chat transcript for each session.
* **Feedback Panel:** Shows rating cards on the right side of the interface. Hovering over or clicking these cards will highlight the relevant portions of the chat transcript for easy reference.

**To submit feedback**

1. Navigate to the Brand Concierge Homepage and select **[!UICONTROL Feedback]**.
1. Use the provided snapshot to view information on high-level trends.
1. To access a deep dive powered by Customer Journey Analytics, select **[!UICONTROL View Report]**.
1. You can also inspect the panel for additional connected feedback.
1. When finished, you can export the insights to use later and refine your workflow.

### Configurations {#configurations}

The _[!UICONTROL Configurations]_ tab is a read-only summary view that you can use to review your concierge's full setup. This directly mirrors the Homepage after completion of the initial setup and provides summaries of your details, knowledge sources, skills, and configured Brand Expression. You can use this feature as a reference prior to previewing or sharing your concierge.

## What you can do with Brand Concierge

Lean about the customer features, business capabilities, and uses cases for Brand Concierge.

### Customer features

Brand Concierge offers a conversational interface that lets customers find products, compare options, and get answers using natural language. With personalized recommendations, rich product comparisons, and the ability to escalate to a live agent, customers enjoy a seamless, intuitive experience. Interaction is flexible - customers can use text, voice, or images—and every answer is based on your brand's trusted documentation and customer context. 

* Ask questions in natural language and get personalized recommendations.
* Compare products side-by-side with visual displays.
* Get answers sourced from your brand documentation.
* Switch to a live agent with full conversation history.

### Business capabilities

Brand Concierge empowers businesses with advanced conversational AI capabilities for customer engagement. It helps brands drive conversion by guiding customers to the right products, reduces support costs through instant, accurate answers, and ensures consistent brand voice and compliance. With robust analytics, seamless AI-to-human handoff, and deep Adobe integrations, Brand Concierge optimizes both customer experience and business performance.

* Guide customers to the right products to increase conversion.
* Reduce support costs with instant, accurate answers.
* Control brand voice, tone, and compliance requirements.
* Track performance with Customer Journey Analytics dashboard.
* Enable seamless AI-to-human handoff including meeting scheduling.
* Integrate with Adobe Experience Platform, and Experience Manager.

## Use cases

Brand Concierge supports both B2C and B2B use cases across multiple industries.

| Industry | Use cases |
|---|---|
| Retail and e-commerce | Customers can discover products and receive personalized recommendations. Brand Concierge provides guidance on sizing and fit, helps users find suitable gifts, and matches styles or preferences based on customer input. |
| B2B sales | Brand Concierge guides customers through product evaluations, offers detailed feature and pricing comparisons, assists with scheduling sales meetings, and provides industry-specific recommendations tailored to business clients. |
| Customer support | Users can receive instant answers sourced directly from the knowledge base. Brand Concierge supplies information on policies and procedures, helps troubleshoot issues, and provides updates on order status and tracking. |
| Travel and hospitality | Customers receive personalized destination recommendations, assistance with planning itineraries, support throughout the booking process, and answers to travel policy questions. |
| Financial services | Brand Concierge offers product comparisons to help customers choose the right financial solutions, provides account information, delivers compliance-aware guidance, and enables meeting scheduling with financial advisors. |

## Frequently asked questions

Read this section for answers to frequently asked questions regarding Brand Concierge.

### General

#### How is Brand Concierge different from chatbots?

Brand Concierge stands apart from traditional chatbots by leveraging generative AI that is specifically trained on your organization's content and customer data, rather than relying on scripted answers or generic web results. This enables the assistant to provide personalized responses informed by individual customer behavior, deeply integrate with your Adobe tools and data, continuously learn from each interaction, and accurately interpret customer intent beyond basic keyword matching.

#### Can I use Brand Concierge for both B2C and B2B?

Yes. Use cases include:

* **B2C:** Product discovery, shopping assistance, customer support, personalized recommendations.
* **B2B:** Guided evaluations, feature comparisons, meeting scheduling, sales representative routing, consultation booking.

#### What industries can use Brand Concierge?

Brand Concierge can be used across a wide range of industries, including retail and e-commerce, travel and hospitality, financial services, healthcare (with compliance controls), media and entertainment, and technology and software. Essentially, any industry that helps customers find information and make decisions can benefit from implementing Brand Concierge.

### Data and privacy

#### Is customer data safe?

Yes. Brand Concierge ensures customer data is safe by adhering to GDPR and CCPA compliance, processing data on Adobe's secure infrastructure, providing you with control over data usage, and safeguarding conversations through encryption and audit logging.

All conversations happen on your properties, not third-party servers.

#### What data sources can I connect?

You can connect the following types of data sources to Brand Concierge:

| Data Source Type | Available Sources/Details |
|------------------|---------------------------|
| **Product and content** | Product catalogs<br>Inventory systems<br>Knowledge bases and documentation<br>Website content via CSV URL upload<br>Adobe Experience Manager content<br>Adobe Commerce data |
| **Customer data** | Adobe Experience Platform profiles<br>Adobe Analytics behavior data<br>First-party customer attributes<br>Third-party APIs (configured) |
| **CSV file format** | One column containing website URLs<br>Brand Concierge crawls URLs and extracts content automatically<br>Processing status updates in real-time<br>Multiple CSV files can be uploaded for different content areas |

All data follows your governance rules.

#### Can customers opt out of personalization?

Yes. Customers who opt out receive helpful responses without behavioral personalization. You configure opt-out handling to match your privacy policies.

### Configuration and control

#### How do I control brand voice?

You can control your brand voice directly in the UI by configuring elements such as tone (ranging from formal to casual), language (from simple to technical), and personality (for example, helpful, enthusiastic, or professional). Additionally, you can define response patterns using templates and examples, and establish guardrails to enforce compliance rules and boundaries. Begin with Adobe's reference prompts and tailor these settings to reflect your brand's unique identity.

#### What happens when Brand Concierge can't answer a question?

You can configure fallback behaviors to determine how Brand Concierge responds when it cannot answer a question. Options include displaying a graceful "I can't help with that" message, suggesting alternative questions, linking to self-service resources, or automatically escalating the inquiry to a human agent. Choose what works best for your brand.

#### Can I customize the visual design?

Yes. Customize all visual elements, including:

* Colors and branding
* Fonts and typography
* Button styles
* Widget positioning
* Card layouts
* Response formatting

SDKs provide default components and full customization options.

#### How long does setup take?

The length of setup can depend on your type of implementation. A basic implementation that includes an existing product catalog, standard FAQ content, and default settings can take around 3-5 days to setup. On the other hand, advanced implementations with custom integrations, extensive personalization, complex workflows, and custom compliance rules can take around 2-4 weeks to complete.

#### How does the preview and testing work?

Brand Concierge includes built-in testing tools:

| Testing Tool | Features |
|--------------|----------|
| **Preview mode** | Simulate customer conversations<br>Adjust settings in real-time<br>See changes instantly<br>Share preview links with your team |
| **Tester View** | Rate responses with thumbs up/down<br>Provide structured feedback across 4 categories<br>Add detailed comments<br>Track feedback in dashboard |

All testing happens before you deploy to customers.

#### Can customers schedule meetings with our team?

Yes, customers can schedule meetings with your team using the Meeting Booking skill. To enable this feature, activate the skill in Skills Configuration, define activation intents (such as "speak with sales"), connect your calendar or scheduling system, and set your availability and meeting types. Once configured, customers can request meetings during conversations, and Brand Concierge will facilitate the scheduling process without requiring them to leave the chat.

#### Who handles the prompt engineering?

Adobe consultants handle prompt engineering in the background:

1. You answer configuration questions in the Skills page.
1. Provide product knowledge, business rules, and avoid keywords.
1. Submit your inputs.
1. Adobe consultants use your answers to engineer optimized prompts.
1. Changes reflect in your concierge automatically.

This ensures your concierge uses best-practice AI prompt patterns while maintaining your specific brand requirements.

### Performance and analytics

#### How do I measure success?

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

#### What should I do if sentiment drops?

If you notice a drop in sentiment, investigate the underlying causes by reviewing recent failed queries, checking for content gaps, analyzing negative feedback, testing for appropriate tone, and verifying any technical issues. Once the root causes are identified, promptly address them and continue to monitor for improvement.

### Integration and technical

#### Do I need other Adobe products?

No, but they enhance performance:

| Integration Option | Capabilities |
|-------------------|--------------|
| **Standalone** | Works with your product catalog and content |
| **With Adobe Experience Platform** | Unified customer profiles<br>Advanced personalization<br>Cross-channel consistency |
| **With Adobe Commerce** | Real-time inventory<br>Order history<br>Cart integration |
| **With Adobe Experience Manager** | Content management<br>Dynamic updates<br>Multi-site support |

#### What if my site isn't on Adobe?

Brand Concierge works with any platform. The JavaScript SDK integrates with any website, and mobile SDKs work with any app backend.

#### How does agent handoff work?

When agent handoff is triggered, Brand Concierge transfers the full conversation history, customer profile and ID, identified intent, details of products discussed, and any resolution attempts to the agent. This ensures that agents have complete context and can continue the conversation seamlessly, without requiring customers to repeat information.

#### Can I support multiple languages?

Yes. Configure language support per assistant based on your customer base. Brand Concierge detects customer language and responds accordingly.
