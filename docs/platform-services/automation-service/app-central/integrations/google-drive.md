---
title: Google Drive
description: ''
---
import useBaseUrl from '@docusaurus/useBaseUrl';

<img src={useBaseUrl('/img/platform-services/automation-service/app-central/logos/google.png')} alt="google" width="80"/>

***Version: 1.1  
Updated: Mar 5, 2025***

Google Drive is Google's cloud-based storage and file-sharing service, enabling users to store, sync, and collaborate on files from any device.

## Actions

* **Create Permission** *(Containment)* - Creates a permission for a file or shared drive.
* **Delete Permission** *(Containment)* - Deletes a permission.
* **Get File** *(Enrichment)* - Gets a file's metadata or content by ID.
* **List Files** *(Enrichment)* - Lists the user's files.
* **List Permissions** *(Enrichment)* - Lists a file's or shared drive's permissions.

## Google Drive configuration

To [create service account credentials](https://developers.google.com/workspace/guides/create-credentials) in Google Workspace and generate the JSON file needed to configure the Google Drive integration, follow these steps:

1. Log in to the [Google Cloud](https://console.cloud.google.com) portal.
2. Select a Google Cloud project (or create a new one).
3. Go to the **API&Services** > **Credentials** page.
4. Click **CREATE CREDENTIALS** and select **Service Account**.<br/><img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/google-drive/google-drive-1.png')} style={{border:'1px solid gray'}} alt="google-drive" width="800"/>
5. Enter a Service account name to display in the Google Cloud console. The Google Cloud console generates a service account ID based on this name.
6. Optional: Enter a description of the service account.
7. Skip two optional grant permissions steps and click **Done** to complete the service account creation.<br/><img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/google-drive/google-drive-2.png')} style={{border:'1px solid gray'}} alt="google-drive" width="800"/>
8. Click on the generated service account to open the details.<br/><img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/google-drive/google-drive-3.png')} style={{border:'1px solid gray'}} alt="google-drive" width="800"/>
9. Under the **KEYS** tab, Click **ADD KEY** and choose **Create new key**.<br/><img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/google-drive/google-drive-4.png')} style={{border:'1px solid gray'}} alt="google-drive" width="800"/>
10. Click on **CREATE** (make sure **JSON** is selected).<br/><img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/google-drive/google-drive-5.png')} style={{border:'1px solid gray'}} alt="google-drive" width="400"/>
11. The JSON file is downloaded. Make sure you save it in a safe place
12. Enable the Admin SDK API for the project at [https://console.cloud.google.com/flows/enableapi?apiid=admin.googleapis.com](https://console.cloud.google.com/flows/enableapi?apiid=admin.googleapis.com).
13. Go to [https://admin.google.com/ac/owl/domainwidedelegation](https://admin.google.com/ac/owl/domainwidedelegation) to open the Domain-Wide delegation settings in the Google Admin portal
14. Click on Add new. <br/><img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/google-drive/google-drive-6.png')} style={{border:'1px solid gray'}} alt="google-drive" width="800"/>
15. In the Client ID field, provide the client ID from the JSON file.<br/><img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/google-drive/google-drive-7.png')} style={{border:'1px solid gray'}} alt="google-drive" width="500"/><br/><img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/google-drive/google-drive-8.png')} style={{border:'1px solid gray'}} alt="google-drive" width="600"/>
16. In the OAuth scopes (comma-delimited) field, provide the following scopes:
	'https://www.googleapis.com/auth/drive'
17. Click Authorize.<br/><img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/google-drive/google-drive-9.png')} style={{border:'1px solid gray'}} alt="google-drive" width="800"/>

## Configure Google Drive in Automation Service and Cloud SOAR

import IntegrationsAuth from '../../../../reuse/integrations-authentication.md';
import IntegrationCertificate from '../../../../reuse/automation-service/integration-certificate.md';
import IntegrationEngine from '../../../../reuse/automation-service/integration-engine.md';
import IntegrationLabel from '../../../../reuse/automation-service/integration-label.md';
import IntegrationProxy from '../../../../reuse/automation-service/integration-proxy.md';
import IntegrationTimeout from '../../../../reuse/automation-service/integration-timeout.md';

<IntegrationsAuth/>
* <IntegrationLabel/>
* **User Service Account JSON**. Provide the content of the JSON file generated [above](#google-drive-configuration). Open the file and copy-paste the whole content in the field.

* **User Email**. Enter the email address of an admin user.
* <IntegrationEngine/>
* <IntegrationProxy/>

<img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/misc/google-drive-configuration.png')} style={{border:'1px solid gray'}} alt="Google Drive configuration" width="400"/>

For information about  Google Drive, see [Google Drive API documentation](https://developers.google.com/workspace/drive/api/guides/about-sdk).

## Change Log

* October 13, 2023 (v1.0) - First upload
* March 05, 2025 (v1.1) - Updated List Permissions and Delete Permission actions.
