---
title: Trend Micro Deep Security
description: ''
---
import useBaseUrl from '@docusaurus/useBaseUrl';

<img src={useBaseUrl('/img/platform-services/automation-service/app-central/logos/trend-micro-deep-security.png')} alt="trend-micro-deep-security" width="80"/>

***Version: 1.2  
Updated: Jun 22, 2023***

Utilize Trend Micro Deep Security to interact with IP lists, firewall and intrusion rules, and gather enrichment data during incident investigations.

## Actions

* **List Systems** (*Enrichment*) - List all available systems.
* **List IP Lists** (*Enrichment*) - List all IP lists.
* **List Policies** (*Enrichment*) - List all available policies.
* **List Firewall Rules** (*Enrichment*) - List all firewall rules.
* **List Intrusion Rules** (*Enrichment*) - List all intrusion rules.
* **Get System Info** (*Enrichment*) - Gather system information for a specific system.
* **Get IP List** (*Enrichment*) - Get a specific IP list.
* **Get Policy** (*Enrichment*) - Get a specific policy.
* **Get Firewall Rule** (*Enrichment*) - Get a specific firewall rule.
* **Get Intrusion Rule** (*Enrichment*) - Get a specific intrusion rule.
* **Create IP List** (*Containment*) - Create a new IP list.
* **Create Policy** (*Containment*) - Create a new policy.
* **Add Firewall Rules To Policy** (*Containment*) - Add a firewall rule to an existing policy.
* **Create Intrusion Rule** (*Containment*) - Create a new intrusion rule.
* **Add Intrusion Rules To Policy** (*Containment*) - Add an intrusion rule to an existing policy.
* **Search Systems By Hostname** (*Enrichment*) - Search systems by hostname.
* **Search Systems By IP** (*Enrichment*) - Search systems by IP Address.

## Configure Trend Micro Deep Security in Automation Service and Cloud SOAR

import IntegrationsAuth from '../../../../reuse/integrations-authentication.md';
import IntegrationCertificate from '../../../../reuse/automation-service/integration-certificate.md';
import IntegrationEngine from '../../../../reuse/automation-service/integration-engine.md';
import IntegrationLabel from '../../../../reuse/automation-service/integration-label.md';
import IntegrationProxy from '../../../../reuse/automation-service/integration-proxy.md';
import IntegrationTimeout from '../../../../reuse/automation-service/integration-timeout.md';

<IntegrationsAuth/>
* <IntegrationLabel/>
* **API URL**. Enter your [Trend Micro  Deep Security API URL](https://automation.deepsecurity.trendmicro.com/article/12_0/use-the-previous-rest-api/#basic-api-access).

* **API Key**. Enter your Trend Micro Deep Security [API key](https://docs.trendmicro.com/en-us/documentation/article/deep-security-20-lts-api-key).

* **API Version**. Enter your Trend Micro Deep Security [API version](https://automation.deepsecurity.trendmicro.com/article/20_0/first-steps-for-deep-security-developers/#api-versions).
* <IntegrationTimeout/>
* <IntegrationCertificate/>
* <IntegrationEngine/>
* <IntegrationProxy/>

<img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/misc/trend-micro-deep-security-configuration.png')} style={{border:'1px solid gray'}} alt="Trend Micro Deep Security configuration" width="400"/>

For information about Trend Micro Deep Security, see [Trend Micro Deep Security documentation](https://docs.trendmicro.com/en-us/documentation/deep-security/).

## Change Log

* March 6, 2020 - First upload
* October 27, 2022 - Action **Search Systems By Hostname** added.
* February 17, 2023 (v1.1)
	+ New Action: Search Systems By IP
* June 22, 2023 (v1.1) - Removed unnecessary empty lines
