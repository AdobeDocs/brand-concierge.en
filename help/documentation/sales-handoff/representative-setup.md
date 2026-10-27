---
title: Set Up Representatives in Adobe Marketo Qualifier
description: Connect a representative's Outlook or Google calendar, set the meeting confirmation email, define calendar and live chat availability, and review who is set up.
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
# Set up representatives in Adobe Marketo Qualifier {#representative-setup}

Before a concierge can offer a meeting or a live chat, at least one representative has to be set up in [!DNL Adobe Marketo Qualifier]. Each representative does this once, in their own profile.

The sequence is: an administrator adds the users, then each representative connects a calendar, writes their confirmation email, and declares when they are available for meetings and for chat.

## Add users to the organization {#add-users}

An administrator adds each sales representative as a user in the [!DNL Adobe Admin Console] and grants them access to [!DNL Adobe Marketo Qualifier]. For the general procedure, see [Add a user to the org](../user-and-access-management/add-a-user-to-the-org.md) and [Add a user to the role](../user-and-access-management/add-a-user-to-the-role.md).

Representatives complete the remaining steps themselves.

## Connect your calendar {#connect}

The calendar connection is what makes real availability visible to a concierge. Without it, the representative is not eligible for meeting booking.

1. Sign in to [Adobe Experience Cloud](https://experience.adobe.com/){target="_blank"} and select **[!UICONTROL Adobe Marketo Qualifier]**.

   ![Adobe Experience Cloud homepage with the Adobe Marketo Qualifier card](../assets/meetings-connect-1.png){width="800" zoomable="yes"}

1. In the left panel, under **[!UICONTROL Configuration]**, select **[!UICONTROL Profile settings]**, and then open the **[!UICONTROL Calendar configuration]** tab.

1. Choose the calendar you want to connect, either [!DNL Microsoft Outlook] or [!DNL Google Calendar].

   ![Calendar configuration tab showing the Outlook and Google calendar connection options](../assets/meetings-connect-2.png){width="600" zoomable="yes"}

1. Sign in with an existing account or add a new one, and grant the requested permissions.

   ![Microsoft account picker shown during the calendar connection](../assets/meetings-connect-3.png){width="600" zoomable="yes"}

1. Review the confirmation email that a visitor receives when they book a meeting with you.

   A default subject line and body are set for you. Edit either one, and choose whether to include a [!DNL Microsoft Teams] meeting link in the invitation.

   ![Meeting confirmation email settings with an editable subject line and body](../assets/meetings-connect-4.png){width="600" zoomable="yes"}

1. Select **[!UICONTROL Save]**.

## Set calendar availability {#calendar-availability}

Connecting a calendar tells [!DNL Adobe Marketo Qualifier] when you are *busy*. Calendar availability tells it when you are *willing* to take a meeting. Both are applied.

1. In **[!UICONTROL Profile settings]**, open the **[!UICONTROL Calendar availability]** tab.

   ![Calendar availability tab before any availability has been set](../assets/meetings-availability-1.png){width="600" zoomable="yes"}

1. Set your meeting rules.

   | Setting | What it controls |
   | --- | --- |
   | Meeting duration | How long a booked meeting runs, and therefore the length of each offered slot |
   | Buffer time | The gap enforced between the end of one meeting and the start of the next |
   | Minimum notice | How far ahead a visitor must book. For example, set 4 hours to keep visitors from booking a slot that starts in 10 minutes |
   | Time zone | The time zone your availability hours are expressed in. Visitors always see slots converted to their own time zone |

1. Set your available hours for each day of the week.

   A day can be one continuous block, such as 8:00 AM to 5:00 PM, or several blocks, such as 8:00 AM to 12:00 PM and 2:00 PM to 5:00 PM. Leave a day empty to take no meetings on that day.

   >[!NOTE]
   >
   >To add another block of time to a day, select the plus sign (![plus sign icon](../assets/icon-plus-sign.png)).

   ![Calendar availability tab with weekday hours and a split time range configured](../assets/meetings-availability-2.png){width="600" zoomable="yes"}

1. Select **[!UICONTROL Save]**.

### How a slot becomes bookable {#slot-logic}

A time slot is offered to a visitor only when it survives all three checks:

1. It falls inside the available hours you set here.
1. It is not already occupied by an event on your connected calendar. An existing 9:00 AM meeting removes the 9:00 AM slot.
1. It satisfies your minimum notice and buffer time.

## Set live chat availability {#chat-availability}

Live chat availability is separate from calendar availability. A representative can be available for chat but take no meetings, or the reverse.

1. In **[!UICONTROL Profile settings]**, open the **[!UICONTROL Live chat availability]** tab.

1. Set your time zone, then set the days and hours when you are willing to receive a live chat. Weekends can be included.

   ![Live chat availability tab with days and hours configured](../assets/meetings-availability-3.png){width="600" zoomable="yes"}

1. Select **[!UICONTROL Save]**.

>[!NOTE]
>
>Availability hours make you *eligible* for chats. Your live status in the chat inbox decides whether you receive them right now. See [Chat inbox](chat-inbox.md).

## Review who is set up {#manage-members}

This section is for administrators only. Under **[!UICONTROL Administration]**, select **[!UICONTROL Manage members]** to see the state of every representative in one place: who has connected a calendar, who has set live chat availability, and who has disconnected a calendar.

Use this before activating the integrations in Composer. A representative who appears here without a connected calendar is not eligible for meeting booking, and one without live chat availability is not eligible for live chat.

![Manage members page listing representatives and their calendar and live chat setup state](../assets/manage-members-1.png){width="800" zoomable="yes"}

## Next step {#next}

With at least one representative set up, decide how visitors are matched to representatives. See [Route conversations to representatives](routing-rules.md).
