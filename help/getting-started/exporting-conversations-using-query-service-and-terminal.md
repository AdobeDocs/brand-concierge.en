---
title: Exporting conversations using query service and terminal
description: Learn how to export Brand Concierge conversations to CSV using Experience Platform Query Service and Terminal, with guidance on credentials and personal data.
topic: Development
role: Developer
level: Experienced
doc-type: Tutorial
duration: 260
last-substantial-update: 2026-10-15
jira: KT-22874
---
# Exporting conversations using query service and terminal

Learn how to save and export Adobe Brand Concierge conversations using Adobe Experience Platform Query Service and Terminal. This video shows how to find dataset table names, configure the PostgreSQL command-line client, and export conversation data for a date range to a CSV file.

## Who is this video for?

* Developers who need to export Brand Concierge conversation data using command-line tools

## Video content

* Find conversation datasets in Experience Platform and copy their table names
* Install the PostgreSQL client with Homebrew and configure its command-line path
* Copy the PSQL connection command from the Query Service Credentials tab
* Select a dataset and date range, then export query results to a local CSV file
* Check the exported results and refresh expired credentials when needed

>[!VIDEO](https://video.tv.adobe.com/v/3504643)

>[!IMPORTANT]
>
> The PSQL connection command contains a live password. Do not share it or paste it into chats, AI agents, or email. If authentication fails after the password expires, copy a fresh command from the Query Service Credentials tab.

>[!NOTE]
>
> Exported conversations may contain personally identifiable information (PII). Follow your organization's data-handling policy when storing CSV files.

For documentation, see [Brand Concierge help](../documentation/overview.md).

## Related tutorials

* [Exporting conversations using Adobe CX Enterprise Coworker](exporting-conversations-using-adobe-cx-enterprise-coworker.md)
