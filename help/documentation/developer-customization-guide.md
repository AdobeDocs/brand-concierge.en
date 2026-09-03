---
title: Developer and customization guide
description: Learn how to install the Brand Concierge Web SDK and Web Client, customize appearance and content, handle client-side events, and export conversation data.
role: Developer,Admin
level: Experienced
toc: true
---

# Developer and customization guide {#developer-customization-guide}

This guide is for developers and technical teams implementing or customizing a Brand Concierge deployment. It covers installing the Web SDK and Web Client, customizing appearance and content, listening to client-side events through callback functions, and exporting conversation data for reporting.

## Web SDK and Web Client installation {#installation}

### Prerequisites {#prerequisites}

* The organization is an Adobe Experience Platform (AEP) customer.
* The page is instrumented with the Adobe Experience Platform Web SDK.
* The datastream ID used on the page is enabled for Brand Concierge.

### Step 1: Inject the Web SDK {#inject-web-sdk}

Add the following to the page's `<head>` section:

```html
<script>
  !(function (n, o) {
    o.forEach(function (o) {
      n[o] ||
        ((n.__alloyNS = n.__alloyNS || []).push(o),
        (n[o] = function () {
          var u = arguments;
          return new Promise(function (i, l) {
            n[o].q.push([i, l, u]);
          });
        }),
        (n[o].q = []));
    });
  })(window, ["alloy"]);
</script>
<script src="https://cdn1.adoberesources.net/alloy/2.31.1/alloy.min.js"></script>
```

### Step 2: Inject the Web Client {#inject-web-client}

Add the following after the Web SDK script, still in the `<head>` section:

```html
<script src="https://experience.adobe.net/solutions/experience-platform-brand-concierge-web-agent/static-assets/main.js"></script>
```

### Step 3: Configure the Web SDK {#configure-web-sdk}

Call `alloy("configure", ...)` with your organization's own values in place of the placeholders below:

```javascript
alloy("configure", {
  defaultConsent: "in",
  edgeDomain: "edge.adobedc.net",
  edgeBasePath: "ee",
  datastreamId: "YOUR_DATASTREAM_ID",
  orgId: "YOUR_IMS_ORG_ID",
  debugEnabled: true,
  idMigrationEnabled: false,
  thirdPartyCookiesEnabled: false,
  prehidingStyle: ".personalization-container { opacity: 0 !important }",
  onBeforeEventSend: (options) => {
    const x = options.xdm;
    const params = new URLSearchParams(window.location.search);
    const titleParam = params.get("title");
    if (titleParam) {
      x.web.webPageDetails.name = titleParam;
    } else {
      x.web.webPageDetails.name = "default-page";
    }
    return true;
  }
});
alloy("sendEvent", {});
```

| Field | Description |
|---|---|
| `datastreamId` | The datastream ID configured for this page, enabled for Brand Concierge. |
| `orgId` | The IMS Org ID the concierge is configured under. |
| `debugEnabled` | Set to `false` in production once integration is verified. |
| `prehidingStyle` | CSS applied before personalization content loads, to avoid a flash of unstyled content. |
| `onBeforeEventSend` | Optional hook to modify the XDM payload before it is sent — commonly used to set page name or context. |

### Step 4: Initialize the Web Client {#initialize-web-client}

After the Web SDK configure call, initialize the Web Client by calling the bootstrap API:

```javascript
window.adobe.concierge.bootstrap({
  instanceName: "alloy",
  stylingConfigurations: window.styleConfigurations,
  selector: "#brand-concierge-mount"
});
```

| Parameter | Type | Required | Description |
|---|---|---|---|
| `instanceName` | string | Yes | The Web SDK instance name. |
| `stylingConfigurations` | JSON object | Yes | The Web Client styling configuration (see [Visual and content customization](#customization)). |
| `selector` | string | Yes | CSS selector for the HTML element the Web Client mounts into. |
| `onEvent` | function | No | Callback for client-side events (see [Client-side events and callback functions](#events)). |

## Visual and content customization {#customization}

The `stylingConfigurations` object passed into `bootstrap()` controls appearance, behavior, and text throughout the Web Client. It is organized into several areas.

### Metadata {#metadata}

```javascript
"metadata": {
  "brandName": "Your Brand",
  "version": "1.0.0",
  "language": "en-US",
  "namespace": "brand-concierge"
}
```

### Behavior {#behavior}

Controls the functional behavior of individual chat features.

```javascript
"behavior": {
  "input": {
    "enableVoiceInput": true
  },
  "chat": {
    "messageAlignment": "left",
    "messageWidth": "80%"
  },
  "privacyNotice": {
    "title": "Privacy Notice",
    "text": "By using this automated chatbot, you consent that any personal information you provide in the chat may be collected, used, analyzed, disclosed, and retained by Adobe and its service providers, in accordance with the Adobe Privacy Policy. Please do not enter any sensitive personal information (e.g., financial or health data)."
  },
  "disclaimer": {
    "attachWithInput": true
  },
  "chatTranscript": {
    "enabled": true,
    "maxSessions": 1,
    "maxMessagesPerSession": 20,
    "cleanupInterval": 24
  },
  "meetingForm": {
    "fieldsPerRow": 2,
    "title": { "text": "Schedule meeting", "alignment": "left" },
    "subtitle": { "text": "I'd be happy to help you schedule a meeting! Please fill out the form below, and we'll follow up with a calendar to confirm your day and time.", "alignment": "left" },
    "buttons": {
      "submit": { "text": "Schedule meeting", "alignment": "left" },
      "cancel": { "text": "Cancel", "alignment": "left" }
    }
  },
  "calendarWidget": {
    "title": { "text": "Book a meeting", "alignment": "left" },
    "subtitle": { "text": "Thanks! Here's a calendar where you can choose a time that works best for your schedule:", "alignment": "left" },
    "postTitle": { "text": "Once confirmed, you'll receive a calendar invite with all the details.", "alignment": "left" },
    "buttons": {
      "confirm": { "text": "Schedule a meeting", "alignment": "left" },
      "cancel": { "text": "Cancel", "alignment": "left" }
    }
  }
}
```

### Disclaimer {#disclaimer}

```javascript
"disclaimer": {
  "text": "AI responses may be inaccurate or misleading. Be sure to double check answers and sources."
}
```

### Text strings {#text-strings}

All user-facing copy is overridable through the `text` object. Common keys:

| Key | Purpose |
|---|---|
| `welcome.heading` / `welcome.subheading` | Welcome screen headline and subtext |
| `input.placeholder` | Input field placeholder text |
| `input.messageInput.aria` / `input.send.aria` / `input.mic.aria` | Accessibility labels for input controls |
| `error.network` / `error.general` | Error messages shown to the visitor |
| `loading.message` | Text shown while a response is generating |
| `feedback.dialog.title.positive` / `.negative` | Feedback dialog titles |
| `feedback.dialog.question.positive` / `.negative` | Feedback dialog prompt text |
| `feedback.toast.success` | Confirmation toast after feedback is submitted |
| `feedback.thumbsUp.aria` / `feedback.thumbsDown.aria` | Accessibility labels for feedback buttons |

### Arrays {#arrays}

Configurable lists of content:

```javascript
"arrays": {
  "welcome.examples": [
    {
      "text": "I want to edit and enhance my photos",
      "image": "https://example.com/idea-1.png",
      "backgroundColor": "#66BFE7"
    }
  ],
  "feedback.positive.options": [
    "Helpful and relevant recommendations",
    "Clear and easy to understand",
    "Friendly and conversational tone",
    "Visually appealing presentation",
    "Other"
  ],
  "feedback.negative.options": [
    "Not helpful or relevant",
    "Confusing or unclear",
    "Too formal or robotic",
    "Poor visual presentation",
    "Other"
  ]
}
```

### Assets {#assets}

```javascript
"assets": {
  "icons": {
    "company": "<svg>...</svg>"
  }
}
```

### Theme {#theme}

CSS custom properties controlling colors, fonts, and layout:

```css
"theme": {
  "--color-primary": "#1473e6",
  "--color-primary-hover": "#0056b3",
  "--color-button-primary": "#3B63FB",
  "--color-accent": "#9085ED",
  "--color-button-submit": "#4759e6",
  "--color-button-submit-hover": "#3a4bce",
  "--color-message-user": "#1473e6",
  "--font-family": "'Adobe Clean', adobe-clean, 'Trebuchet MS', sans-serif",
  "--main-container-background": "linear-gradient(135deg, #66ccff, #cc99ff, #ffcc99, #ccff99)",
  "--submit-button-fill-color": "white",
  "--card-text-background": "var(--color-background)",
  "--card-text-border-radius": "var(--border-radius-card)",
  "--message-concierge-link-decoration": "underline",
  "--message-max-width": "100%"
}
```

## Client-side events and callback functions {#events}

The event callback system lets a page observe Web Client lifecycle events, user interactions, responses, feedback, and errors in real time, useful for sending engagement data to Adobe Analytics, Google Analytics, or other third-party systems.

### Key characteristics {#key-characteristics}

* **Single callback** — one `onEvent` function receives all event types, distinguished by `event.eventType`.
* **Read-only** — event data is a cloned snapshot and cannot be used to modify the client's behavior.
* **Error-isolated** — exceptions thrown inside the callback are caught and logged; they do not break the Web Client.
* **Registered via `bootstrap()`** — passed the same way as `onBeforeEventSend`.

### Quick start {#quick-start}

```javascript
window.adobe.concierge.bootstrap({
  instanceName: "my-instance",
  selector: "#brand-concierge-mount",
  stylingConfigurations: { /* ... */ },
  onEvent: (event) => {
    console.log(event.eventType, event.timestamp, event.data);
  }
});
```

### Filtering by event type {#filtering}

```javascript
onEvent: (event) => {
  switch (event.eventType) {
    case "query:submitted":
      console.log("User query:", event.data.query);
      break;
    case "response:completed":
      console.log("Response received:", event.data.conversationId);
      break;
    case "card:clicked":
      console.log("Card clicked:", event.data.element.entity_info.productName);
      break;
    case "error:occurred":
      console.log("Error:", event.data.errorMessage);
      break;
  }
}
```

### Event types {#event-types}

| Event type | Value | Category | When it fires |
|---|---|---|---|
| `WEBCLIENT_INITIALIZED` | `webclient:initialized` | Lifecycle | Client finishes initialization (DOM mounted, content loaded) |
| `QUERY_SUBMITTED` | `query:submitted` | User interaction | User submits a message (typed or from suggestion) |
| `PROMPT_SUGGESTION_CLICKED` | `promptSuggestion:clicked` | User interaction | User clicks a prompt suggestion pill |
| `CARD_CLICKED` | `card:clicked` | User interaction | User clicks a card |
| `HISTORY_CLEARED` | `history:cleared` | User interaction | User clears the chat history |
| `RESPONSE_STARTED` | `response:started` | Response | First streaming chunk arrives from the API |
| `RESPONSE_COMPLETED` | `response:completed` | Response | Full response is received and rendered |
| `CARDS_RENDERED` | `cards:rendered` | Response | Cards (single image or carousel) finish rendering |
| `FEEDBACK_SUBMITTED` | `feedback:submitted` | Feedback | User submits a feedback form (thumbs up/down with details) |
| `ERROR_OCCURRED` | `error:occurred` | Error | An error occurs (network, API, or runtime) |

### Lifecycle events {#lifecycle-events}

`webclient:initialized` fires after the client has fully initialized: content loaded, CSS injected, chat UI rendered in the DOM.

```json
{
  "eventType": "webclient:initialized",
  "timestamp": 1741638123789,
  "data": {
    "instanceName": "my-instance"
  }
}
```

### User interaction events {#user-interaction-events}

`query:submitted` fires when the user submits a message, whether typed, from a prompt suggestion, or from a widget option.

```json
{
  "eventType": "query:submitted",
  "timestamp": 1741638124000,
  "data": {
    "query": "What photo editing tools do you offer?"
  }
}
```

`promptSuggestion:clicked` fires when the user clicks a prompt suggestion pill. It fires *before* the subsequent `query:submitted` event.

```json
{
  "eventType": "promptSuggestion:clicked",
  "timestamp": 1741638124100,
  "data": {
    "suggestion": "Tell me more about Photoshop"
  }
}
```

`card:clicked` fires when the user clicks a card.

```json
{
  "eventType": "card:clicked",
  "timestamp": 1741638124200,
  "data": {
    "element": {
      "entity_info": {
        "productName": "Adobe Photoshop",
        "productDescription": "Photo editing software",
        "productPageURL": "https://www.adobe.com/products/photoshop.html",
        "productImageURL": "https://example.com/photoshop.png"
      }
    }
  }
}
```

`history:cleared` fires when the user clicks the clear-chat-history button.

```json
{
  "eventType": "history:cleared",
  "timestamp": 1741638124400,
  "data": {}
}
```

### Response events {#response-events}

`response:started` fires when the first streaming chunk arrives from the API.

```json
{
  "eventType": "response:started",
  "timestamp": 1741638125000,
  "data": {
    "conversationId": "conv-abc-123",
    "interactionId": "int-xyz-456"
  }
}
```

`response:completed` fires when the full response has been received.

```json
{
  "eventType": "response:completed",
  "timestamp": 1741638126000,
  "data": {
    "conversationId": "conv-abc-123",
    "interactionId": "int-xyz-456"
  }
}
```

`cards:rendered` fires after cards render in the DOM. It fires separately from `response:completed` and indicates the display mode used.

```json
{
  "eventType": "cards:rendered",
  "timestamp": 1741638126100,
  "data": {
    "element": [
      { "entity_info": { "productName": "Adobe Photoshop" } },
      { "entity_info": { "productName": "Adobe Illustrator" } }
    ],
    "displayMode": "carousel"
  }
}
```

### Feedback events {#feedback-events}

`feedback:submitted` fires when the user completes and submits a feedback form (after thumbs up/down).

```json
{
  "eventType": "feedback:submitted",
  "timestamp": 1741638127000,
  "data": {
    "conversationId": "conv-abc-123",
    "interactionId": "int-xyz-456",
    "feedbackType": "negative",
    "selectedOptions": ["Incorrect information", "Not relevant"],
    "notes": "The response did not address my question about pricing."
  }
}
```

### Error events {#error-events}

`error:occurred` fires when the client encounters a network, API, or runtime error.

```json
{
  "eventType": "error:occurred",
  "timestamp": 1741638128000,
  "data": {
    "errorMessage": "Something went wrong. Please try again."
  }
}
```

### Event object structure {#event-object-structure}

Every event shares the same top-level shape:

```typescript
interface BrandConciergeEvent {
  eventType: string;  // e.g. "query:submitted"
  timestamp: number;  // Unix epoch, milliseconds
  data: object;       // Event-specific payload
}
```

### Data type reference: Element (product card) {#element-reference}

```typescript
interface Element {
  id?: string;
  type?: string;
  entity_info: {
    productName: string;
    productDescription: string;
    description: string;
    productPageURL: string;
    details: string;
    backgroundColor: string;
    learningResource: string;
    productImageURL: string;
    logo: string;
    variants?: Record<string, ElementVariant>;
    primary: ElementAction;
    secondary: ElementAction;
  };
}

interface ElementAction {
  label: string;
  url: string;
}
```

### Best practices {#best-practices}

* **Use for analytics and monitoring.** Track engagement, query patterns, and product interest; forward `error:occurred` to an error-tracking service; track card clicks for conversion analysis.
* **Keep the callback fast.** It runs synchronously on the main thread, so avoid blocking network calls:

```javascript
// Good — fire and forget
onEvent: (event) => {
  navigator.sendBeacon("/analytics", JSON.stringify(event));
}

// Avoid — blocking network call
onEvent: async (event) => {
  await fetch("/analytics", { body: JSON.stringify(event) });
}
```

* **Do not rely on strict event order** for state machines. Events fire in a logical sequence, but use `conversationId` and `interactionId` to correlate related events instead of assuming order.
* **Handle errors inside your own callback.** The client isolates and logs callback errors, but unhandled errors inside the callback can still lose analytics data:

```javascript
onEvent: (event) => {
  try {
    myAnalytics.track(event);
  } catch (e) {
    console.warn("Analytics tracking failed", e);
  }
}
```

## Export conversations using AEP Query Service {#export-conversations}

Brand Concierge writes conversation data — prompts, responses, and feedback — into Adobe Experience Platform (AEP) datasets. You can query these directly with Query Service (SQL) to build custom reports.

### Find the dataset and table name {#find-dataset}

1. Open Adobe Experience Platform.

1. Go to **[!UICONTROL Datasets]**.

1. Search for `cja_brand_concierge` to list the datasets related to Brand Concierge.

1. Open the dataset you need (for example, responses versus other flows, if more than one exists).

1. On the dataset details view, find the **[!UICONTROL Table name]** used by Query Service, and inspect the sample or preview data to confirm the columns (prompts, responses, feedback, timestamps, and so on).

>[!NOTE]
>
>Table names are tied to each dataset and differ by environment and sandbox. If you have multiple sandboxes or deployments, repeat these steps in the correct sandbox so the table name matches where data is written.

### Example query {#example-query}

```sql
SELECT *
FROM cja_brand_concierge_responses_dataset_5f5105bd_1c38_4ebc_8505_bd
WHERE timestamp >= TIMESTAMP '2026-03-16 00:00:00'
  AND timestamp <= NOW()
ORDER BY timestamp ASC;
```

>[!IMPORTANT]
>
>The table name above is only an illustration — do not hard-code it. Confirm the actual table name for your dataset in AEP first (see [Find the dataset and table name](#find-dataset)), and adjust the time filter, sort order, or other clauses to match your reporting needs. Run the query from your organization's Query Service workflow (UI, API, or connected client), using the same sandbox as the dataset.

### Run a query in the Query Service UI {#run-query-ui}

If you need a manual data pull for reporting, the Query Service UI provides a way to run and download results directly:

1. In Adobe Experience Platform, go to **[!UICONTROL Queries]**.

1. Enter the query in the editor and click **[!UICONTROL Run query]**.

1. Results appear in the **[!UICONTROL Results]** tab below the editor once the query completes. From there, you can download the results.

### Further reading {#further-reading}

* [Query Service API documentation](https://experienceleague.adobe.com/en/docs/experience-platform/query/home){target="_blank"} — Adobe's official reference for Query Service behavior, limits, authentication, and API paths, which change over time independent of this guide.
