---
title: Nozomi Networks
description: ''
---
import useBaseUrl from '@docusaurus/useBaseUrl';

<img src={useBaseUrl('/img/platform-services/automation-service/app-central/logos/nozomi-networks.png')} alt="nozomi-networks" width="100"/>

***Version: 1.2  
Updated: Jul 19, 2023***

Utilize Nozomi Networks to gain visibility across OT, IoT, and IT environments.

## Actions

* **Captured URL Info** (*Enrichment*) - Gather URL information.
* **Get Assets** (*Enrichment*) - Gather a list of all assets.
* **Query** (*Enrichment*) - Issue a query.
* **Create Node CSV** (*Containment*) - Create a new node (CSV).
* **Create Node JSON** (*Containment*) - Create a new node (JSON).
* **Execute CLI Command** (*Containment*) - Execute a CLI command.

## Configure Nozomi Networks in Automation Service and Cloud SOAR

import IntegrationsAuth from '../../../../reuse/integrations-authentication.md';
import IntegrationCertificate from '../../../../reuse/automation-service/integration-certificate.md';
import IntegrationEngine from '../../../../reuse/automation-service/integration-engine.md';
import IntegrationLabel from '../../../../reuse/automation-service/integration-label.md';
import IntegrationProxy from '../../../../reuse/automation-service/integration-proxy.md';
import IntegrationTimeout from '../../../../reuse/automation-service/integration-timeout.md';

<IntegrationsAuth/>
* <IntegrationLabel/>
* **URL**. Enter your Nozomi Networks URL.

* **Username**. Enter the username of a Nozomi Networks admin user.

* **Password**. Enter the password for the admin user.
* <IntegrationTimeout/>
* <IntegrationCertificate/>
* <IntegrationEngine/>
* <IntegrationProxy/>

<img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/misc/nozomi-configuration.png')} style={{border:'1px solid gray'}} alt="Nozomi Networks configuration" width="400"/>

For information about Nozomi Networks, see [Nozomi Networks documentation](https://www.nozominetworks.com/guides).

## Change Log

* May 15, 2020 - First upload
* July 19, 2023 (v1.2) - Code refactoring
