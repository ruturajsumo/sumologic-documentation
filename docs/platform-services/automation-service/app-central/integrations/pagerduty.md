---
title: PagerDuty
description: ''
---
import useBaseUrl from '@docusaurus/useBaseUrl';

<img src={useBaseUrl('/img/platform-services/automation-service/app-central/logos/pagerduty.png')} alt="pagerduty" width="100"/>

***Version: 1.6  
Updated: Aug 24, 2023***

Utilize PagerDuty to notify responders during the incident response process.

## Actions

* **Add Note To Incident** (*Notification*) - Add a comment to the specified incident.
* **Create New Incident** (*Notification*)- Create a new incident.
* **Create Responder Request** (*Notification*) - Create a new responder request.
* **Get Alert Details** (*Enrichment*) - Get the alert details for the specified incident alert.
* **Get Incident Details** (*Enrichment*) - Get details for the specified incident.
* **List Escalation Policies** (*Enrichment*) - List the escalation policies matching the query, or list all escalation policies.
* **List Incidents from PagerDuty** (*Enrichment*) - List the incidents matching the specified queries.
* **List Incident Alerts** (*Enrichment*) - List the alerts for the specified incident.
* **List Priorities** (*Enrichment*) - List the available priorities.
* **List Services** (*Enrichment*) - List the services matching the optional query, or list all services.
* **List Users** (*Enrichment*) - List the users matching the optional query, or list all users.
* **Create Incident Status** (*Notification*) - Update the specified incident with a new status.
* **Update Incident** (*Notification*) - Update an incident with the specified parameters.
* **Delete User** (*Notification*) - Delete user.

## Configure PagerDuty in Automation Service and Cloud SOAR

import IntegrationsAuth from '../../../../reuse/integrations-authentication.md';
import IntegrationCertificate from '../../../../reuse/automation-service/integration-certificate.md';
import IntegrationEngine from '../../../../reuse/automation-service/integration-engine.md';
import IntegrationLabel from '../../../../reuse/automation-service/integration-label.md';
import IntegrationProxy from '../../../../reuse/automation-service/integration-proxy.md';
import IntegrationTimeout from '../../../../reuse/automation-service/integration-timeout.md';

<IntegrationsAuth/>
* <IntegrationLabel/>
* **API URL**. Enter your PagerDuty [API](https://developer.pagerduty.com/docs/rest-api-overview) URL, for example, `api.pagerduty.com`

* **Token**. Enter https://developer.pagerduty.com/docs/user-oauth-token-via-code-granthttps://developer.pagerduty.com/docs/oauth-functionality).
* <IntegrationTimeout/>
* <IntegrationCertificate/>
* <IntegrationEngine/>
* <IntegrationProxy/>

<img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/misc/pagerduty-configuration.png')} style={{border:'1px solid gray'}} alt="PagerDuty configuration" width="400"/>

For information about PagerDuty, see [PagerDuty documentation](https://developer.pagerduty.com/docs/introduction).

## Change Log

* January 22, 2019 - First upload
* January 13, 2023 - Integration refactored
* February 16, 2023 - Type of actions changed
* March 3, 2023 (v1.3)
	+ Updated integration Fields Label
* August 23, 2023 (v1.6) - Changed Delete User action type to Notification
