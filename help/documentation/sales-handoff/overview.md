---
title: Live Chat and Meeting Booking Overview
description: Learn how Brand Concierge hands a visitor off to a human, either as a live chat with an available representative or as a booked meeting on a representative's calendar.
role: User, Admin
level: Beginner
TQID: https://experienceleague.adobe.com/vfX6M2-ts7d2-AxKGjaP1Ygkk3FGSGRl4CHslcKYSXU
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
---
# Live chat and meeting booking overview {#overview}

A concierge answers most questions on its own. Some conversations need a person: a pricing negotiation, a procurement questionnaire, a demo request. Live chat and meeting booking are the two ways Brand Concierge hands that conversation to a human without losing the context the visitor already provided.

* Live chat connects the visitor to an available representative immediately, in the same chat window.
* Meeting booking offers the visitor real open slots from a representative's calendar and books the meeting.

Both are offered by the same skill, **[!UICONTROL Handoff to sales]**, and both route through [!DNL Adobe Marketo Qualifier] (formerly [!DNL Sales Qualifier]), where your representatives connect their calendars, set their availability, and take chats.

## How a handoff works {#how-it-works}

Four pieces have to line up before a visitor can reach a person.

| Piece | What it does | Where you set it up |
| --- | --- | --- |
| Representative profile | Connects a calendar and declares when the representative is available for meetings and for chat | [!DNL Adobe Marketo Qualifier] > **[!UICONTROL Profile settings]** |
| Routing | Decides *which* representative gets this visitor | [!DNL Adobe Marketo Qualifier] > **[!UICONTROL Routing rules]**, and the routing type on each integration |
| Integrations | **[!UICONTROL Meeting Booking]** and **[!UICONTROL Live Chat]** give the concierge the ability to check availability, start a chat, and book a slot | Composer > **[!UICONTROL Browse integrations]** |
| Skill | **[!UICONTROL Handoff to sales]** decides *when* to offer a handoff, based on the visitor's intent | Composer > **[!UICONTROL Browse skills]** |

At runtime, the visitor says something that matches one of the skill's **[!UICONTROL Use when]** conditions. The skill fires and calls whichever integrations are attached to it. Routing then resolves a representative, and the visitor is offered a chat, a meeting, or both.

>[!NOTE]
>
>Skills and integrations are the general building blocks of a concierge. For the underlying model, see [Skills and Integrations Framework](../skills-and-integrations.md).

## The visitor experience {#visitor-experience}

When the skill fires, the concierge explains the options and presents them as buttons in the conversation.

![Concierge response offering a handoff, with Chat with a specialist now and Schedule meeting buttons below it](../assets/sales-handoff-visitor-1.png){width="800" zoomable="yes"}

### Live chat {#visitor-live-chat}

If the visitor chooses to chat, the concierge shows a connecting state while routing finds an available representative.

![Concierge showing a Connecting to a specialist status after the visitor selects Chat with a specialist now](../assets/sales-handoff-visitor-2.png){width="800" zoomable="yes"}

Before the representative joins, the visitor completes a short pre-chat form. Those answers travel with the conversation and appear to the representative as **[!UICONTROL Form details]** in the chat inbox, so the visitor does not have to repeat anything.

The visitor can end the chat at any time and is asked to confirm.

![End chat confirmation dialog asking the visitor to confirm ending the chat with the specialist](../assets/sales-handoff-visitor-4.png){width="800" zoomable="yes"}

### Meeting booking {#visitor-meeting-booking}

If the visitor chooses to book a meeting, the concierge shows a calendar with the slots that are genuinely open on the routed representative's calendar, in the visitor's own time zone.

![Book a meeting card in the conversation showing a month calendar and a list of available time slots](../assets/sales-handoff-visitor-3.png){width="800" zoomable="yes"}

After the visitor confirms a slot, the visitor receives the representative's confirmation email, which optionally includes a [!DNL Microsoft Teams] link. The conversation context goes to the representative with the invitation.

## What you need before you start {#prerequisites}

* Access to [!DNL Adobe Marketo Qualifier], with your representatives added as users in the [!DNL Adobe Admin Console].
* At least one representative who has connected a calendar. The **[!UICONTROL Meeting Booking]** integration cannot be activated until one has.
* At least one representative who has set live chat availability. The **[!UICONTROL Live Chat]** integration cannot be activated until one has.
* A concierge in Composer that you can add integrations and skills to.

>[!NOTE]
>
>Live chat and meeting booking do not require [!DNL Adobe Marketo Engage]. Without it, representative, meeting, and chat data stays in [!DNL Adobe Marketo Qualifier]. Two things do require [!DNL Marketo Engage]: custom routing rules, which are built on [!DNL Marketo] lead and company attributes, and the concierge activity types that are written back to the [!DNL Marketo] person record.

## Set up live chat and meeting booking {#setup-path}

Work through these in order.

1. [Set up representatives in Adobe Marketo Qualifier](representative-setup.md) — connect a calendar, define the confirmation email, and set calendar and live chat availability.
1. [Route conversations to representatives](routing-rules.md) — choose round robin, a direct agent, or custom rules built on [!DNL Marketo] attributes.
1. [Activate live chat and meeting booking](configure-in-composer.md) — connect the two integrations and activate the **[!UICONTROL Handoff to sales]** skill.
1. [Chat inbox](chat-inbox.md) — what representatives do once a chat arrives, including scoring the conversation.
1. [Brand Concierge data in Marketo Engage](marketo-activities.md) — the lead fields and activity types written back to [!DNL Marketo], and how to use them in Smart Campaigns.
1. [Monitor meetings and live chats](monitor.md) — the bookings list and the performance dashboard.

## Data retention {#retention}

Live chat conversations are retained for 30 days.
