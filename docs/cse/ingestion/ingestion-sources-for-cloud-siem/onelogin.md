---
id: onelogin
title: OneLogin - Cloud SIEM
sidebar_label: OneLogin
description: Learn how to collect OneLogin log messages and send them to Sumo Logic to be ingested by Cloud SIEM.
---

import useBaseUrl from '@docusaurus/useBaseUrl';

This section has instructions for collecting OneLogin log messages and sending them to Sumo Logic to be ingested by Cloud SIEM.

## Step 1: Configure collection

In this step, you configure an HTTP Source to collect OneLogin log messages. You can configure the source on an existing Hosted Collector or create a new collector. If you’re going to use an existing collector, jump to [Configure an HTTP Source](#configure-an-http-source) below. Otherwise, create a new collector as described in [Configure a hosted collector](#configure-a-hosted-collector) below, and then create the HTTP Source on the collector.

### Configure a Hosted Collector

1. [**Classic UI**](/docs/get-started/sumo-logic-ui-classic). In the main Sumo Logic menu, select **Manage Data > Collection > Collection**. <br/>[**New UI**](/docs/get-started/sumo-logic-ui). In the top menu select **Configuration**, and then under **Data Collection** select **Collection**. You can also click the **Go To...** menu at the top of the screen and select **Collection**. 
1. Click **Add Collector**.
1. Click **Hosted Collector.**
1. The **Add Hosted Collector** popup appears.<br/><img src={useBaseUrl('img/cse/add-hosted-collector.png')} alt="Add hosted collector" style={{border: '1px solid gray'}} width="500"/>  
1. **Name**. Provide a Name for the Collector.
1. **Description**. (Optional)
1. **Category**. Enter a string to tag the output collected from the source. The string that you supply will be saved in a metadata field called `_sourceCategory`. 
1. **Fields**. 
    1. If you are planning that all the sources you add to this collector will forward log messages to Cloud SIEM, click the **+Add Field** link, and add a field whose name is `_siemForward` and value is *true*. This will cause the collector to forward all of the logs collected by all of the sources on the collector to Cloud SIEM.
    1. If all sources in this collector will be OneLogin sources, add an additional field with key `_parser` and value */Parsers/System/OneLogin/OneLogin SSO JSON*.
    :::note
    It’s also possible to configure individual sources to forward to Cloud SIEM, as described in the following section.
    :::

### Configure an HTTP Source

1. [**Classic UI**](/docs/get-started/sumo-logic-ui-classic).
 In the main Sumo Logic menu, select **Manage Data > Collection > Collection**. <br/>[**New UI**](/docs/get-started/sumo-logic-ui). In the top menu select **Configuration**, and then under **Data Collection** select **Collection**. You can also click the **Go To...** menu at the top of the screen and select **Collection**. 
1. Navigate to the Hosted Collector where you want to create the source.
1. On the **Collectors** page, click **Add Source** next to a Hosted Collector.
1. Select **HTTP Logs & Metrics**. 
1. The page refreshes.<br/><img src={useBaseUrl('img/cse/http-source.png')} alt="HTTP source" style={{border: '1px solid gray'}} width="600"/> 
1. **Name**. Enter a name for the source. 
1. **Description**. (Optional) 
1. **Source Host.** (Optional) Enter a string to tag the messages collected from the source. The string that you supply will be saved in a metadata field called `_sourceHost.`
1. **Source Category**. Enter a string to tag the output collected from the source. The string that you supply will be saved in a metadata field called `_sourceCategory`.
1. **Fields.** If you are not parsing all sources in the hosted collector with the same parser, click the **+Add Field** link, and add a field whose name is `_parser` with value */Parsers/System/OneLogin/OneLogin SSO JSON*.
1. **Advanced Options for Logs**. For information about the optional advance options you can configure, see [HTTP Logs and Metrics Source](/docs/send-data/hosted-collectors/http-source/logs-metrics/).
1. Click **Save**.
1. Make a note of the **HTTP Source URL** that is displayed. You’ll supply it in [Step 2](#step-2-configure-onelogin) below.

## Step 2: Configure OneLogin

In this step you configure OneLogin to send log messages to the Sumo Logic platform. For instructions, see [Stream Real-Time OneLogin Event Data to SIEM (Webhooks)](https://onelogin.service-now.com/support?id=kb_article&sys_id=60de41ecdb1928d0ca1c400e0b961905&kb_category=00b6ad30db185340d5505eea4b9619ae) in
the OneLogin knowledge base. You must use the SIEM (NDJSON) format. Use the **Sumo Logic HTTP Source URL** as the **Listener URL**, and a custom header is not needed.

## Step 3: Verify ingestion

In this step, you verify that your logs are successfully making it into Cloud SIEM. 

1. [**Classic UI**](/docs/get-started/sumo-logic-ui-classic). In the top menu select **Configuration**, and then under **Incoming Data** select **Log Mappings**. <br/>[**New UI**](/docs/get-started/sumo-logic-ui). In the top menu select **Configuration**, and then under **Cloud SIEM Integrations** select **Log Mappings**. You can also click the **Go To...** menu at the top of the screen and select **Log Mappings**.  
1. On the **Log Mappings** tab search for "OneLogin" and check the **Records** columns. 
1. For a more granular look at the incoming records, you can also search the Sumo Logic platform for OneLogin security records. <br/><img src={useBaseUrl('img/cse/onelogin-search.png')} alt="OneLogin search" style={{border: '1px solid gray'}} width="400"/>
