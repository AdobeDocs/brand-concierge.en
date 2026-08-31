---
title: Analyze concierge performance
description: Learn how to review concierge analytics, inspect conversation transcripts, add visitor questions to evaluation sets, and open detailed Customer Journey Analytics reports.
toc: true
---

# Analyze concierge performance

**Who this is for:** Marketers using the self-serve experience. No setup is required after the concierge is deployed.

**Recommended cadence:** Review analytics as needed. A weekly check-in is a reasonable starting point.

Analytics help you understand how visitors engage with a live concierge. After deployment, the **Analytics** tab automatically displays conversation metrics and provides access to individual transcripts and a more detailed Customer Journey Analytics report.

## View analytics

1. Open the concierge and select the **Analytics** tab.

1. Set the date range for the period you want to review.

1. Optionally filter the results by conversation type.

The Analytics tab displays the following metrics automatically:

| Metric | Description |
|---|---|
| Conversations | The number of conversations during the selected period. |
| Engaged visitors | The number of visitors who engaged with the concierge. |
| Positive sentiment | The amount of positive sentiment identified in conversations. |
| Messages per conversation | The average number of messages exchanged in a conversation. |

>[!NOTE]
>
>No configuration is required to view these metrics after the concierge is deployed.

## Review conversation transcripts

Conversation transcripts let you review what visitors asked and how the concierge responded.

1. In the Analytics view, select a conversation.

1. Read the full transcript.

1. Review whether visitors selected a thumbs-up or thumbs-down rating for individual answers.

Each conversation has a unique conversation ID. Use this ID to match the transcript to records in other systems when your implementation supports that workflow.

### Add a conversation to an evaluation set

If a visitor asks a question that is useful for future testing, add it directly to an evaluation set from the transcript.

1. Open the conversation transcript.

1. Select **Add to Evaluation**.

Adding real visitor questions helps keep evaluation sets grounded in the questions visitors actually ask. For more information about evaluation sets, see `Evaluate a concierge` LINK.

>[!TIP]
>
>Review transcripts regularly and add representative questions—not only questions that received negative feedback—to help maintain a balanced evaluation set.

## Open the Customer Journey Analytics report

Select **View Report** to open a more detailed dashboard in Adobe Customer Journey Analytics (CJA). The dashboard is automatically provisioned and does not require additional configuration.

The CJA dashboard includes:

* Weekly conversation trends
* Repeat engagement, including conversations per person
* Messages per conversation
* Visitor feedback trends
* Visitor intent
* Visitor sentiment and tone
* Concierge recommendations made during conversations

Use the dashboard to examine trends over time and identify changes in visitor engagement, feedback, intent, and sentiment.

## Export conversations

The source material identifies the conversation ID as a way to match transcripts with records in other systems, but it does not document an export mechanism.

>[!IMPORTANT]
>
>Do not treat conversation IDs as an export workflow. A dedicated walkthrough from Product or Engineering is required before documenting how to export conversations or transcripts.

## Source scope and open questions

This article covers the analytics capabilities described in the source material:

* Analytics-tab metrics
* Conversation transcripts and visitor feedback
* Adding conversations to evaluation sets
* The Customer Journey Analytics dashboard
* The documented limitation around conversation export

The supplied source ends with an unfinished `10` heading. No additional section is included here.
