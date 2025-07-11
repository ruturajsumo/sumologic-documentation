---
title: Rapid 7 InsightVM
description: ''
---
import useBaseUrl from '@docusaurus/useBaseUrl';

<img src={useBaseUrl('/img/platform-services/automation-service/app-central/logos/rapid-7-insightvm.png')} alt="rapid-7-insightvm" width="80"/>

***Version: 1.2  
Updated: Jul 07, 2023***

Utilize and interact with Rapid7 Vulnerability management tool.

## Actions

* **Get Assets** (*Enrichment*) - Returns all assets for which you have access.
* **Post Asset Search** (*Enrichment*) - Returns all assets for which you have access that match the given search criteria.
* **Post Asset Groups** (*Enrichment*) - Creates a new asset group.
* **Get Asset Groups** (*Enrichment*) - Returns all asset groups.
* **Get Scans** (*Enrichment*) - Returns all scans.
* **List Vulnerabilities** (*Enrichment*) - Returns all vulnerabilities that can be assessed during a scan.
* **Get Vulnerability** (*Enrichment*) - Returns the details for a vulnerability.
* **Get Sites** (*Enrichment*) - Retrieves a paged resource of accessible sites.
* **Get Report Template** (*Enrichment)* - Returns the details of a report template.
* **Delete Asset Groups** (*Containment*) - Deletes the asset group.
* **Delete Site** (*Containment*) - Deletes a site.
* **Get Assets Vulnerability** (*Enrichment*) - Returns the details for a vulnerability of a specific asset.
* **Search Asset By Hostname** *(Enrichment)* - Searches an asset by a hostname.
* **Search Asset By IP** *(Enrichment)* - Searches an asset by IP address.

## Category

Vulnerability Management

## Configure Rapid7 InsightVM in Automation Service and Cloud SOAR

import IntegrationsAuth from '../../../../reuse/integrations-authentication.md';
import IntegrationCertificate from '../../../../reuse/automation-service/integration-certificate.md';
import IntegrationEngine from '../../../../reuse/automation-service/integration-engine.md';
import IntegrationLabel from '../../../../reuse/automation-service/integration-label.md';
import IntegrationProxy from '../../../../reuse/automation-service/integration-proxy.md';
import IntegrationTimeout from '../../../../reuse/automation-service/integration-timeout.md';

<IntegrationsAuth/>
* <IntegrationLabel/>
* **URL**. Enter your Rapid7 InsightVM URL, for example, `your-domain.rapid7.com`.

* **Port**. Enter your Rapid7 InsightVM [port](https://docs.rapid7.com/insightvm/insightvm-quick-start-guide/#ports).

* **Username**. Enter the username of a Rapid7 InsightVM admin user authorized to authenticate the integration.

* **Password**. Enter the password for the admin user.
* <IntegrationTimeout/>
* <IntegrationCertificate/>
* <IntegrationEngine/>
* <IntegrationProxy/>

<img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/misc/rapid7-insightvm-configuration.png')} style={{border:'1px solid gray'}} alt="Rapid7 InsightVM configuration" width="400"/>

For information about Rapid7 InsightVM, see [Rapid7 InsightVM documentation](https://docs.rapid7.com/insightvm/).

## Change Log

* October 27, 2021 - First upload
* October 28, 2022 - Added new action: Search Asset By Hostname added
* February 17, 2023 (v1.1)
	+ New Action: Search Asset By IP
* July 7, 2023 (v1.2) - Removed leading/trailing spaces
