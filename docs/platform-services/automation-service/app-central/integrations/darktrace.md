---
title: Darktrace
description: ''
---

import useBaseUrl from '@docusaurus/useBaseUrl';

<img src={useBaseUrl('/img/platform-services/automation-service/app-central/logos/darktrace.png')} alt="darktrace" width="100"/>

***Version: 1.7  
Updated: Jan 10, 2025***

Perform threat intelligence evidence gathering with Darktrace.

## Actions

* **Add To Watch List** *(Containment)* - Adds external domains, hostnames, or IP addresses to Darktrace's internal watch list.
* **Darktrace Breach Daemon** *(Daemon)* - Automatically gather Breaches from Darktrace.
* **Darktrace Incident Events Daemon** *(Daemon)* - Automatically gather Incident Events from Darktrace (provides access to AI Analyst events - a group of anomalies or network activity investigated by Cyber AI Analysts).
* **Get IOC** *(Enrichment)* - Get IOC details by value.
* **Get Model** *(Enrichment)* - Returns a specific model that currently exist on the Threat Visualizer.
* **Get Watch List** *(Enrichment)* - Retrieves a list of indicators from a watch list.
* **List Models** *(Enrichment)* - Returns a list of all models that currently exist on the Threat Visualizer.
* **List Tags** *(Enrichment)* - List all available tags.
* **Remove From Watch List** *(Containment)* - Removes an external domain, hostname, or IP address from Darktrace's internal watch list.
* **Search Breach** *(Enrichment)* - Query breaches from Darktrace.
* **Search Devices** *(Enrichment)* - Search capacity to interrogate the list of devices has seen on the network.

## Configure Darktrace in Automation Service and Cloud SOAR

import IntegrationsAuth from '../../../../reuse/integrations-authentication.md';
import IntegrationCertificate from '../../../../reuse/automation-service/integration-certificate.md';
import IntegrationEngine from '../../../../reuse/automation-service/integration-engine.md';
import IntegrationLabel from '../../../../reuse/automation-service/integration-label.md';
import IntegrationProxy from '../../../../reuse/automation-service/integration-proxy.md';
import IntegrationTimeout from '../../../../reuse/automation-service/integration-timeout.md';

<IntegrationsAuth/>
* <IntegrationLabel/>
* **URL**. Enter your Darktrace server URL.

* **Public Key**. Enter a Darktrace public key.

* **Private Key**. Enter the private key corresponding to the public key.
* <IntegrationCertificate/>
* <IntegrationTimeout/>
* **Darktrace Minutes**. Enter your Darktrace minutes setting, for example, `10`.

* <IntegrationEngine/>
* <IntegrationProxy/>

<img src={useBaseUrl('/img/platform-services/automation-service/app-central/integrations/misc/darktrace-configuration.png')} style={{border:'1px solid gray'}} alt="Darktrace configuration" width="400"/>

For information about Darktrace, see the [Darktrace website](https://www.darktrace.com/).

## Change Log

* January 15, 2021 - First upload
* February 11, 2021 - Updated Actions:
    + Get IOC
    + List Models
    + Get Models
    + Search Device
    + List Tags
* June 07, 2022 - New Actions:
    + Search Breach
    + Darktrace Breach Daemon
* February 17, 2023 (v1.2)
    + New Daemon: Darktrace Incident Events Daemon
* July 12, 2023 (v1.3) - Updated the integration with Environmental Variables
* January 29, 2024 (v1.4)
    + Updated resource: Resolved bug related to integration resource
* February 28, 2024 (v1.5) - Updated code for compatibility with Python 3.12
* March 4, 2024 (v1.5) - Updated code for compatibility with Python 3.12
* January 10, 2025 (v1.7) - Fixed timedelta related error in all actions
