---
title: Route Conversations to Representatives
description: Choose how Brand Concierge decides which sales representative receives a live chat or a meeting booking, using round robin, a direct agent, or custom routing rules.
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
# Route conversations to representatives {#routing}

Routing answers one question: when this visitor asks for a person, *which* person do they get?

You pick a routing type separately for the **[!UICONTROL Meeting Booking]** integration and the **[!UICONTROL Live Chat]** integration, so a concierge can distribute meetings evenly while sending every chat to one specialist, or any other combination.

## Routing types {#routing-types}

| Routing type | Who gets the conversation | Requires [!DNL Marketo Engage] |
| --- | --- | --- |
| **[!UICONTROL Round robin]** | Distributed across all eligible representatives | No |
| **[!UICONTROL Direct agent]** | One representative you name | No |
| **[!UICONTROL Custom routing]** | The representatives assigned to the highest-priority routing rule the visitor qualifies for | Yes |

Round robin is available by default and needs no configuration. You set the routing type on the integration itself. See [Activate Live Chat and Meeting booking](configure-in-composer.md).

### Round robin {#round-robin}

Round robin behaves differently for meetings than for chats, because the two have different goals.

**For meeting booking**, round robin distributes meetings evenly. The first eligible representative who has connected a calendar is offered first. Once a meeting is booked with them, they are taken out of the pool and the next representative is offered. With five representatives, the first five meetings go to five different people. After everyone has received one, the pool resets and the cycle starts again.

The pool also resets every 24 hours, so that each day's meetings are distributed evenly.

>[!NOTE]
>
>The 24-hour round robin reset runs on UTC, not on the representative's local time zone.

**For live chat**, there is no sequential rotation. Every eligible representative is notified of the incoming chat at the same time, and the first one to accept takes the conversation.

### Direct agent {#direct-agent}

Every meeting or chat from this concierge goes to the single representative you select. Use this for a campaign landing page owned by one account executive, or for a region with one specialist.

### Custom routing {#custom-routing}

Custom routing evaluates the rules you build in [!DNL Adobe Marketo Qualifier] against the visitor's [!DNL Marketo] lead and company attributes. Use it when the right representative depends on something you know about the visitor, such as:

* **Geography** — visitors from a set of countries go to the regional team.
* **Product interest** — visitors interested in a specific product go to that product's specialists.
* **Business unit, company size, or industry** — any combination of lead and company attributes.

>[!IMPORTANT]
>
>Custom routing is the one part of live chat and meeting booking that requires [!DNL Adobe Marketo Engage], because the rules are built on [!DNL Marketo] lead and company attributes. Round robin and direct agent work without it.

## Create a custom routing rule {#create-rule}

1. In [!DNL Adobe Marketo Qualifier], under **[!UICONTROL Administration]**, select **[!UICONTROL Routing rules]**.

   The list shows every rule in your organization with its priority, name, creator, and creation date.

   ![Routing rules page listing existing rules with Priority, Name, Created by, and Created on columns](../assets/sales-handoff-routing-1.png){width="800" zoomable="yes"}

1. Select **[!UICONTROL Create rule]** and give the rule a name.

1. Build the criteria.

   The left panel lists the available [!DNL Marketo] attributes from the **[!UICONTROL Company]** and **[!UICONTROL Lead]** (person) objects. Search for an attribute, then drag it onto the canvas to add a condition.

1. Set an operator and a value for each condition.

   Operators include **[!UICONTROL equals]**, **[!UICONTROL does not equal]**, and **[!UICONTROL contains]**, among others. For example, `Country` **[!UICONTROL equals]** `United States`.

1. Combine conditions into groups.

   Add several conditions to one group and join them with **[!UICONTROL AND]** or **[!UICONTROL OR]**. Add more groups and join the groups with **[!UICONTROL AND]** or **[!UICONTROL OR]** as well. Nesting conditions inside groups this way lets you express complex criteria, such as *(country is United States OR Canada) AND (product interest contains Analytics)*.

1. Assign the rule to representatives.

   Under the assignment section, search for a representative by name and select them from the list. Add as many representatives as you want. Any of them can receive a conversation that matches the rule.

1. Select **[!UICONTROL Save]**.

## How priority is applied {#priority}

Every routing rule has a priority. Priority only matters when a visitor qualifies for more than one rule.

When that happens, only the highest-priority matching rule is applied, and the conversation is routed to the representatives assigned to that rule. Rules the visitor also qualifies for, but which rank lower, are ignored.

>[!NOTE]
>
>A lower number means a higher priority. A rule with priority 1 wins over a rule with priority 2. The person who creates a rule sets its priority.

Within the winning rule, the representatives assigned to it are the eligible pool, and the round robin and all-agent behavior described above applies to that pool.

## Next step {#next}

With representatives set up and routing decided, add the capabilities to a concierge. See [Activate Live Chat and Meeting booking](configure-in-composer.md).
