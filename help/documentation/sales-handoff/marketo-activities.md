---
title: Brand Concierge Data in Marketo Engage
description: Understand the lead source fields and the three concierge activity types written to Adobe Marketo Engage, and how to use them in Smart Lists and Smart Campaigns.
role: User, Admin
level: Beginner
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
# Brand Concierge data in Marketo Engage {#marketo-activities}

When [!DNL Adobe Marketo Engage] is connected, every visitor who fills in a form, books a meeting, or starts a live chat becomes a person record in [!DNL Marketo], and their concierge engagement is written to that record as native activity types. That means you can build Smart Lists and Smart Campaigns on concierge behavior exactly as you would on any other [!DNL Marketo] activity.

>[!NOTE]
>
>Live chat and meeting booking themselves do not require [!DNL Marketo Engage]. Without it, the data described on this page stays in [!DNL Adobe Marketo Qualifier]. See [Live chat and meeting booking overview](overview.md#prerequisites).

## Lead creation and source attribution {#lead-creation}

A person created through a concierge is tagged so you can always tell where they came from.

| Field | Value |
| --- | --- |
| **[!UICONTROL Person Source]** | `Brand Concierge` |
| **[!UICONTROL Original Source Type]** | `Chat` |
| **[!UICONTROL Original Source Info]** | `Concierge` |
| **[!UICONTROL Registration Source Type]** | `Chat` |
| **[!UICONTROL Registration Source Info]** | `Concierge` |

![Marketo person record Info tab showing Person Source set to Brand Concierge and the chat and concierge source fields](../assets/sales-handoff-marketo-1.png){width="800" zoomable="yes"}

## Activity types {#activity-types}

Three native activity types are pushed to the person record. All three are available as triggers and filters.

![Marketo Activity Log for a person showing Engage with Concierge, Schedule Meeting in Concierge, and Engage with Live Chat in Concierge entries](../assets/sales-handoff-marketo-2.png){width="800" zoomable="yes"}

### Engage with Concierge {#engage-with-concierge}

Logged when a visitor engages with the concierge.

| Attribute | Description |
| --- | --- |
| Concierge Name | The concierge the visitor engaged with |
| Conversation ID | The identifier of the conversation. Use it in Composer to open the full transcript |
| Page URL | The page where the engagement happened |
| Created At | When the conversation was created |
| Duration | How long the conversation lasted |

>[!NOTE]
>
>Some attributes on this activity type, including topics discussed, summary, and language, are not populated yet. They are planned for a future release.

### Schedule Meeting in Concierge {#schedule-meeting}

Logged **twice** for a single booking, which is what lets you separate intent from outcome.

**First, on initiation.** The visitor selected the option to schedule a meeting and the booking form appeared. Meeting status is `Started`.

| Attribute | Description |
| --- | --- |
| Meeting Status | `Started` |
| Page URL | The page where the visitor initiated the booking |
| Concierge ID | The concierge the visitor engaged with |
| Person ID | The [!DNL Marketo] person record |

**Then, on booking.** The visitor confirmed a slot. Meeting status is `Scheduled`.

| Attribute | Description |
| --- | --- |
| Meeting Status | `Scheduled` |
| Sales Representative Name | The representative the meeting was booked with |
| Sales Representative Email | The representative's email address |
| Scheduled For | The date and time of the meeting |
| Meeting Duration | The length of the booked meeting |
| Routing Type | The routing that resolved this representative's calendar |
| Page URL | The page where the visitor booked |
| Concierge ID | The concierge the visitor engaged with |
| Person ID | The [!DNL Marketo] person record |

>[!TIP]
>
>Build a Smart List on `Meeting Status` is `Started` but not `Scheduled` to find everyone who started booking a meeting and abandoned it. That is a ready-made nurture or retargeting audience.

### Engage with Live Chat in Concierge {#engage-with-live-chat}

Logged after a live chat ends.

| Attribute | Description |
| --- | --- |
| Conversation Status | `Ended` if the chat was closed deliberately, `Dropped` if the visitor left the site and the chat timed out |
| Notified Agents | The email addresses of every agent who was notified of this chat |
| Conversation Score | The 0 to 3 rating the representative gave the conversation. See [Score the conversation](chat-inbox.md#conversation-score) |
| Page URL | The page where the live chat was initiated |
| Concierge ID | The concierge the visitor engaged with |
| Session ID | The live chat session identifier |
| Start Time | When the chat started |

>[!TIP]
>
>Conversation score is the highest-value attribute here, because a human who actually spoke to the visitor set it. Use it for lead scoring, retargeting, personalization, and handoff to sales and CRM.

## Use concierge data in a Smart Campaign {#smart-campaign}

In a Smart Campaign's **[!UICONTROL Smart List]**, search for `concierge` to see everything available.

![Marketo Smart List showing the concierge triggers and filters available for Brand Concierge activity](../assets/sales-handoff-marketo-3.png){width="800" zoomable="yes"}

| Category | Available items |
| --- | --- |
| **[!UICONTROL Triggers]** | Engages with Concierge, Engages with Live Chat in Concierge, Schedules Meeting in Concierge |
| **[!UICONTROL Filters]** > Activity History | Engaged with Concierge, Engaged with Live Chat in Concierge, Scheduled Meeting in Concierge |
| **[!UICONTROL Filters]** > Inactivity Filters | Not Engaged with Concierge, Not Engaged with Live Chat in Concierge, Not Scheduled Meeting in Concierge |

Drag a trigger or filter onto the canvas, then select **[!UICONTROL Add Constraint]** to narrow it.

### Constraints {#constraints}

| Trigger or filter | Constraints |
| --- | --- |
| Engaged with Concierge | Concierge Name, Page URL, Created At, Duration, Date of Activity |
| Scheduled Meeting in Concierge | Concierge Name, Sales Representative Name, Meeting Status, Scheduled For, Meeting Duration, Routing Type, Page URL, Date of Activity |
| Engaged with Live Chat in Concierge | Concierge Name, Sales Representative Name, Conversation Status, Conversation Score, Start Time, Accepted Time, End Time, Closed By, Duration, Discussed Topic, Page URL, Language, Date of Activity |

## Next step {#next}

Review how meetings and chats are performing in [Monitor meetings and live chats](monitor.md).
