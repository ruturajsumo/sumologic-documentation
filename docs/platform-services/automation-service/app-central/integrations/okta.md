---
title: Okta
description: ''
---

import useBaseUrl from '@docusaurus/useBaseUrl';

<img src={useBaseUrl('/img/platform-services/automation-service/app-central/logos/okta.png')} alt="okta" width="50"/>

***Version: 1.4  
Updated: April 24, 2024***

Interact with Okta users, groups, and system logging information.

## Actions

* **Activate Network Zone** _(Containment)_ - Activates a network zone.
* **Activate User** _(Containment)_ - Activates a user account.
* **Add User To Group** _(Containment)_ - Adds a user to a specific group.
* **Create Group** _(Containment)_ - Creates a new group.
* **Create Network Zone** _(Containment)_ - Creates a new network zone.
* **Create User** _(Containment)_ - Creates a new user account.
* **Deactivate Network Zone** _(Containment)_ - Deactivates a network zone.
* **Deactivate User** _(Containment)_ - Deactivates a user’s account.
* **Delete Network Zone** _(Containment)_ - Deletes network zone.
* **Get Group** _(Enrichment)_ - Gets details on a specific group.
* **Get Network Zone** _(Enrichment)_ - Retrieves a network zone.
* **Get User** _(Enrichment)_ - Gets details on a specific user.
* **List Group Members** _(Enrichment)_ - Lists all members of a specific group.
* **List Groups** _(Enrichment)_ - Lists all available groups.
* **List Network Zones** _(Enrichment)_ - Lists all network zones.
* **List Users** _(Enrichment)_ - Lists all available users.
* **Remove User From Group** _(Containment)_ - Removes a user from a specific group.
* **Suspend User** _(Containment)_ - Suspends a user’s account.
* **System Logs** _(Enrichment)_ - Pulls system logs.
* **Unlock User** _(Containment)_ - Unlocks a user’s account.
* **Unsuspend User** _(Containment)_ - Unsuspends a user’s account.
* **Update Network Zone** _(Containment)_ - Updates a network zone.
* **Update User** _(Containment)_ - Updates a user’s account.

## Configure Okta in Automation Service and Cloud SOAR

import IntegrationsAuth from '../../../../reuse/integrations-authentication.md';
import IntegrationCertificate from '../../../../reuse/automation-service/integration-certificate.md';
import IntegrationEngine from '../../../../reuse/automation-service/integration-engine.md';
import IntegrationLabel from '../../../../reuse/automation-service/integration-label.md';
import IntegrationProxy from '../../../../reuse/automation-service/integration-proxy.md';
import IntegrationTimeout from '../../../../reuse/automation-service/integration-timeout.md';

<IntegrationsAuth/>
* <IntegrationLabel/>
* **Domain**. Enter your [Okta domain](https://developer.okta.com/docs/guides/find-your-domain/main/).

* **Token**. Enter an [Okta token](https://support.okta.com/help/s/article/How-to-create-an-API-token?language=en_US).

* **API Version**. Enter your [Okta API version](https://developer.okta.com/docs/api/#api-versions).
* <IntegrationTimeout/>
* <IntegrationCertificate/>
* <IntegrationEngine/>
* <IntegrationProxy/>

<img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/misc/okta-configuration.png')} style={{border:'1px solid gray'}} alt="Okta configuration" width="400"/>

For information about Okta, see [Okta documentation](https://help.okta.com/en-us/content/index.htm).

## Change Log

* March 20, 2020 - First upload
* July 18, 2022
    + New logo
    + Added missing incident Artifacts
* June 21, 2023 (v1.2) - Updated the integration with Environmental Variables
* July 18, 2023 (v1.3) - Code refactoring
* April 24, 2024 (v1.4) - New actions
    * Activate Network Zone
    * Create Network Zone
    * Deactivate Network Zone
    * Delete Network Zone
    * Get Network Zone
    * List Network Zones
    * Update Network Zone
