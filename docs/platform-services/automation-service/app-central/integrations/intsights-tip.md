---
title: Intsights TIP
description: ''
---
import useBaseUrl from '@docusaurus/useBaseUrl';

<img src={useBaseUrl('/img/platform-services/automation-service/app-central/logos/intsights-tip.png')} alt="intsights-tip" width="100"/>

***Version: 1.1  
Updated: Jul 11, 2023***

Intsight Threat Intelligence Platform.

## Actions

* **Add IOC** (*Containment*) - Add iocs to existing file type source.
* **Alert Add Note** (*Containment*) - Add a note to the alert.
* **Close Alert** (*Containment*) - Close alert.
* **Get IOC** (*Enrichment*) - Get Ioc details by value.
* **Remove Source** (*Containment*) - Delete Iocs source (only documents are allowed).
* **Add Source** (*Containment*) - Add Iocs document source.
* **Alert Blocklist Status** (*Enrichment*) - Get alert's blocklist status.
* **Get Alert List Daemon** (*Daemon*) - Get list of alerts ids by query.
* **List Sources** (*Enrichment*) - Get ID, name and confidence level of each Ioc source, grouped by source type.

## Configure Intsights TIP in Automation Service and Cloud SOAR

import IntegrationsAuth from '../../../../reuse/integrations-authentication.md';
import IntegrationCertificate from '../../../../reuse/automation-service/integration-certificate.md';
import IntegrationEngine from '../../../../reuse/automation-service/integration-engine.md';
import IntegrationLabel from '../../../../reuse/automation-service/integration-label.md';
import IntegrationProxy from '../../../../reuse/automation-service/integration-proxy.md';
import IntegrationTimeout from '../../../../reuse/automation-service/integration-timeout.md';

<IntegrationsAuth/>
* <IntegrationLabel/>
* **URL**. Enter your Intsights URL.

* **Account ID**. Enter your Intsights [account ID](https://docs.rapid7.com/threat-command/subscription-settings/).

* **API Key**. Enter your Intsights [API key](https://docs.rapid7.com/insight/managing-platform-api-keys/).
* <IntegrationTimeout/>
* <IntegrationCertificate/>
* <IntegrationEngine/>
* <IntegrationProxy/>

<img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/misc/intsights-configuration.png')} style={{border:'1px solid gray'}} alt="Intsights TIP configuration" width="400"/>

For information about Rapid7 Threat Command ([formerly Intsights TIP](https://www.msspalert.com/news/rapid7-acquires-intsights-cyber)), see [Rapid7 Threat Command documentation](https://docs.rapid7.com/).

## Change Log

* January 15, 2020 - First upload
* July 11, 2023 (v1.1) - Updated the integration with Environmental Variables
