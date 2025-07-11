---
title: Zoom
description: ''
---
import useBaseUrl from '@docusaurus/useBaseUrl';

<img src={useBaseUrl('/img/platform-services/automation-service/app-central/logos/zoom.png')} alt="zoom" width="60"/>

***Version: 2.1  
Updated: Jun 22, 2023***

Monitor and respond to incidents involving Zoom video conferencing.

## Actions

* **Delete Meeting** (Containment) - Delete an existing meeting.
* **Get Meeting Invitation** *(Enrichment)* - Retrieve the meeting invite note that was sent for a specific meeting.
* **Get User** *(Enrichment)* - Retrieve user's information on a Zoom account.
* **Get User Settings** *(Enrichment)* - Retrieve a user's settings.
* **List Meetings** *(Enrichment)* - Retrieve a user's (meeting host) scheduled meetings.
* **List Users** *(Enrichment)* - List the account's users.
* **Update Meeting** *(Containment)* - Update details of a meeting.
* **Update User** *(Containment)* - Update a user's Zoom profile information.
* **Update User Settings** *(Containment)* - Update a user's settings.

## Zoom configuration

The Zoom API uses OAuth 2.0 to authenticate and authorize users to make requests. To set up access credentials and request scopes for your app, create a Server-to-Server OAuth app. This will enable you to securely integrate with Zoom APIs and get your account owner access token without user interaction.

**Create a Server-to-Server OAuth app**

Follow these steps to [create a Server-to-Server OAuth app](https://developers.zoom.us/docs/internal-apps/create/):

1. Sign in to [Zoom Marketplace](https://marketplace.zoom.us/). From the Develop menu, choose Build App.
1. Choose the Server-to-Server OAuth app type.<br/><img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/zoom/zoom-2.png')} style={{border:'1px solid gray'}} alt="zoom" width="600" />
1. Add a name for your app.<br/><img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/zoom/zoom-3.png')} style={{border:'1px solid gray'}} alt="zoom" width="400" />
1. App credentials - View your Account ID, Client ID, and Client Secret.<br/><img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/zoom/zoom-4.png')} style={{border:'1px solid gray'}} alt="zoom" width="600" />
1. Information - Add information about your app, such as a short description and developer contact information (name and email address is required for activation).
1. Define the API methods this app is allowed to call - Add Scopes.<br/><img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/zoom/zoom-5.png')} style={{border:'1px solid gray'}} alt="zoom" width="600" />
1. Choose the appropriate scopes according to the scope required by each Zoom action:   
	* Delete Meeting - meeting:write:admin, meeting:write
	* Get Meeting Invitation - meeting:read:admin, meeting:read
	* Get User - user:read:admin, user:read, user\_info:read
	* Get User Settings - user:read:admin, user:read
	* List Meetings - meeting:read:admin, meeting:read
	* List Users - user:read:admin
	* Update Meeting - meeting:write:admin, meeting:write
	* Update User - user:write:admin, user:write
	* Update User Settings - user:write:admin, user:write
1. Activate your app. If you see errors that prevent activation, please address them. You will not be able to generate an access token to make API calls unless your app is activated. If your app is deactivated, existing tokens will no longer work. You can also choose to Deactivate your app in this section.<br/><img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/zoom/zoom-6.png')} style={{border:'1px solid gray'}} alt="zoom" width="600" />
1. The optional parameter timezone in the actions Update Meeting and Update User can be chosen form the table Timezones in the following [Abbreviation Lists](https://marketplace.zoom.us/docs/api-reference/other-references/abbreviation-lists/#timezones).

## Configure Zoom in Automation Service and Cloud SOAR

import IntegrationsAuth from '../../../../reuse/integrations-authentication.md';
import IntegrationCertificate from '../../../../reuse/automation-service/integration-certificate.md';
import IntegrationEngine from '../../../../reuse/automation-service/integration-engine.md';
import IntegrationLabel from '../../../../reuse/automation-service/integration-label.md';
import IntegrationProxy from '../../../../reuse/automation-service/integration-proxy.md';
import IntegrationTimeout from '../../../../reuse/automation-service/integration-timeout.md';

<IntegrationsAuth/>
* <IntegrationLabel/>
* **OAuth Token URL**. Enter the the Zoom OAuth Token URL. The default is `https://zoom.us/`.

* **API URL**. Enter the Zoom API URL. The default is `https://api.zoom.us/`.

* **Client ID**. Enter the Zoom client ID for the application you [created earlier](#zoom-configuration).

* **Client Secret**. Enter the Zoom client secret for the application you [created earlier](#zoom-configuration).

* **Account ID**. Enter the account ID for the application you [created earlier](#zoom-configuration).
* <IntegrationTimeout/>
* <IntegrationCertificate/>
* <IntegrationEngine/>
* <IntegrationProxy/>

<img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/misc/zoom-configuration.png')} style={{border:'1px solid gray'}} alt="Zoom configuration" width="400"/>

For information about Zoom, see [Zoom documentation](https://developers.zoom.us/docs/).

## Category

Messaging

## Change Log

* May 15, 2020 - First upload
* September 30, 2022
	+ Modified authentication method to OAuth 2.0
	+ Modified Actions:
		- Delete Meeting
		- Get Meeting Invitation
		- Get User
		- Get User Settings
		- List Meetings
		- List Users
		- Update Meeting
		- Update User
		- Update User Settings
* June 22, 2023 (v1.1) - Updated the integration with Environmental Variables
