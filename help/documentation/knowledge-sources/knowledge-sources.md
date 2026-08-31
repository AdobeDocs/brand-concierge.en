---
title: Create and manage knowledge sources for Brand Concierge
description: Learn how to create AEM Sites, website link, and product catalog knowledge sources for Brand Concierge, monitor processing status, and resolve crawl issues.
toc: true
---

# Create and manage knowledge sources for Brand Concierge

A knowledge source is the content that a concierge can use when answering visitor questions. Every concierge requires at least one configured knowledge source. Knowledge sources are created independently and can be reused across multiple concierges.

A concierge answers questions using only its configured knowledge sources. It does not answer from general world knowledge.

>[!NOTE]
>
>If a visitor asks about information outside the configured knowledge sources, the concierge is designed to indicate that it does not have the information instead of generating an unsupported answer. Use the evaluation process to verify this behavior.

## Choose a knowledge source

The source material describes the following knowledge source types:

| Knowledge source | Use it when | Main capability |
| --- | --- | --- |
| AEM Sites (Content AI index) | The customer is an AEM Sites as a Cloud Service customer with Content AI enabled. | Uses an existing Content AI index and makes updated AEM Sites content available without a separate crawl or refresh step. |
| Website Links | The customer needs to crawl a website, regardless of the platform used to build it. | Crawls a sitemap, selected individual URLs, or URLs supplied in a CSV file. |
| Product Catalog | The customer has a relatively small product or service catalog and is not using Adobe Commerce. | Enables product deep links and product cards in concierge responses. |

>[!IMPORTANT]
>
>The source material notes that customers selling through Adobe Commerce with a large catalog should use the Commerce MCP integration instead. Details about that integration are outside the scope of this article.

## Create an AEM Sites knowledge source

Use an AEM Sites knowledge source when the customer already uses AEM Sites as a Cloud Service with Content AI enabled.

1. Select **Build Knowledge Source**.
2. Select **AEM Sites**, and then select **Continue**.
3. Enter a name and description for the knowledge source. For example, use `My main website` as the name.
4. Select an existing Content AI index from the list. The list is populated from the AEM Sites as a Cloud Service instance.
5. Select **Save**.

This native integration makes updated AEM Sites content available to Brand Concierge automatically. A separate crawl or refresh step is not required.

## Create a Website Links knowledge source

Use a Website Links knowledge source for a crawlable website. This option works for websites built on any platform and is the recommended option for most first-time users.

1. Select **Build Knowledge Source**.
2. Select **Website Links**, and then select **Continue**.
3. Enter a name for the knowledge source.
4. Add the content sources using one of the following methods:

   - **Sitemap URL:** Add one URL that lists the site pages. All pages listed in the sitemap are crawled.
   - **Individual URLs:** Add specific page URLs one at a time. Only the added pages are crawled.
   - **CSV upload:** Download the sample file, add the URLs, and upload the completed CSV file.

5. (Optional) Schedule a refresh frequency, such as weekly on a specified day and time, to keep the knowledge source current as the website changes.
6. Select **Add** or **Create**.

The system crawls the specified URLs and scrapes their content to build the knowledge source.

>[!TIP]
>
>A sitemap is typically available at `yourwebsite.com/sitemap.xml`. If the website does not provide a sitemap, add individual page URLs instead.

## Create a Product Catalog knowledge source

Use a Product Catalog knowledge source for customers with a smaller set of products or services—approximately fewer than 100—that are not using Adobe Commerce.

When a concierge response references a product, the product catalog can provide a deep link to the product page and enable a product card. A product card can include an image, title, description, and one or two buttons.

1. Select **Build Knowledge Source**.
2. Select **Product Catalog**, and then select **Continue**.
3. Enter a name for the knowledge source. For example, use `My product catalog — US region` as the name.
4. Select a schema. The schema defines which product fields are displayed, such as the image, title, description, and buttons, and where the buttons link.
5. Download the sample spreadsheet for the selected schema.
6. Add the product data to the spreadsheet, and then upload it.
7. Select **Save**.

Different button requirements require different schemas.

## Monitor knowledge source status

Each knowledge source displays a processing status.

| Status | Meaning |
| --- | --- |
| In progress | The knowledge source is currently being processed. |
| Success | The knowledge source is fully processed and ready to use. |
| Scheduled | The knowledge source will be processed at a future scheduled time. |
| Partial success | Some pages were processed successfully, and others failed. |

The knowledge source details page provides information such as:

- The creator
- The creation date
- The number of links or pages provided
- The number of links or pages that succeeded or failed
- The last refresh time
- The URLs considered for processing

## Troubleshoot processing failures

If a knowledge source has failed or partially succeeded pages, use the issue report to identify the URLs that could not be processed.

1. Open the knowledge source details page.
2. Select **Fix Issues** to download a file containing broken or unscrapable URLs and their error details.
3. Correct the invalid URLs or remove them from the source list.
4. Upload the corrected URL list again, if applicable.
5. Request reprocessing so that the corrected content is added to the knowledge source.

## Scope and open questions

This article documents the three knowledge source types described in the source material. The source material also identifies the following areas as needing more information:

- Whether additional knowledge source types are supported or planned
- Detailed guidance for creating schemas for product catalogs
- Whether a file-upload knowledge source, such as PDF or document upload, is available

Confirm the current product interface and implementation guidance before documenting or using any additional knowledge source type.
