---
id: integrate-google-iam-service
title: Integrate Sumo Logic with Google Apps (G Suite) IAM
description: Using SAML, you can use your Google Apps credentials to log into Sumo Logic via SSO.
---

import useBaseUrl from '@docusaurus/useBaseUrl';

## Availability

| Account Type | Account Level                                                                   |
|:--------------|:---------------------------------------------------------------------------------|
| Cloud Flex   | Trial, Enterprise                                                               |
| Credits      | Trial, Essentials, Enterprise Operations, Enterprise Security, Enterprise Suite |

This page has instructions for integrating Sumo Logic SAML with Google Apps IAM. This allows Sumo users to use  Google Apps credentials to log into Sumo Logic using Single Sign-On (SSO).

For more information, refer to [the Google Support documentation](https://support.google.com/a/answer/6087519?hl=en).

## Before you start

For key information about SAML in Sumo, see the [Limitations](set-up-saml.md) section of the "Set Up SAML for Single Sign-On" page.

### Configure SSO for a Custom App

1. Log into the Google Admin Console.  
1. Select **Apps > SAML Apps**.
1. Select a new SAML app to be configured, or click the **+** at the bottom of the page.
1. On the **Enable SSO for SAML Application** page, select **Setup my own Custom App** at the bottom of the page. <br/><img src={useBaseUrl('img/security/ga_saml_enable_sso.png')} alt="Enable SSO for SAML Application page" style={{border: '1px solid gray'}} width="500" />
1. The **Google IdP Information** page appears. Make note of the following URLs, as you will supply them when you configure SAML in Sumo:

   * **SSO URL**. You'll enter this URL as the **Authn Request URL** when you perform the steps in [Configure Sumo Logic SAML](#configure-sumo-logic-saml) below.
   * **Entity ID**. You'll enter this URL as the **Issuer** in Sumo Logic when you perform the steps in [Configure Sumo Logic SAML](#configure-sumo-logic-saml) below. <br/><img src={useBaseUrl('img/security/ga_saml_sso.png')} alt="Google IdP Information page" style={{border: '1px solid gray'}} width="500" />
1. Click **Download** for the Certificate.
1. Click **Next**.
1. In **Basic Information for your Custom App** page, enter the following: <br/><img src={useBaseUrl('img/security/ga_saml_basic.png')} alt="Basic Information for your Custom App page" style={{border: '1px solid gray'}} width="500" />
    * **Application Name.** Enter Sumo Logic.
    * **Description.** Sumo Logic is the industry's leading, secure cloud-based log monitoring, management and analytics /img/security that leverages big data for real-time IT insights.
    * **Upload Logo.** Use `sumologic.png`.
1. Click **Next**.

### Configure Sumo Logic SAML

1. [**Classic UI**](/docs/get-started/sumo-logic-ui-classic). In the main Sumo Logic menu, select **Administration > Security > SAML**. <br/>[**New UI**](/docs/get-started/sumo-logic-ui). In the top menu select **Administration**, and then under **Account Security Settings** select **SAML**. You can also click the **Go To...** menu at the top of the screen and select **SAML**. 
1. Click **+ Add Configuration** to create a new configuration. <br/><img src={useBaseUrl('img/security/add-config-icon.png')} alt="Add Configuration button on the Configuration List page" style={{border: '1px solid gray'}} width="600" />
1. The **Add Configuration** page appears. <br/><img src={useBaseUrl('img/security/saml-configuration-page.png')} alt="Add Configuration page" style={{border: '1px solid gray'}} width="600" />
1. **Configuration Name.** Google Apps Auth (or, you can enter any name you like).
1. **Debug Mode.** Not required. Activating this setting now is useful for troubleshooting later. Select this option if you'd like to view additional details if an error occurs when a user attempts to authenticate. For more information, see [View SAML Debug Information](view-saml-debug-information.md).
1. **Issuer.** Enter the **Entity ID** from the **Google IdP Information** dialog.
1. **X.509 Certificate.** Open the certificate file that you downloaded from the **Google IdP Information** dialog in a text editor. Copy and paste the contents into this field.
1. **Attribute Mapping**. Select **Use SAML attribute** and type the email attribute name in the text box. 
1. **SP Initiated Login Configuration**. (Optional) This step has instructions for setting up SP-initiated login. When SP initiated login has been enabled, your SAML configuration will appear as an additional authentication option within your subdomain-enabled account login page. SP initiated login requires a custom Sumo Logic subdomain. If a custom subdomain has not yet been configured for your org, following the instructions in the [Change account subdomain](/docs/manage/manage-subscription/create-and-manage-orgs/manage-org-settings) section of the *Manage Organization* topic.
   1. **Authn Request URL.** Enter the **SSO URL** from the **Google IdP Information** dialog.
   1. **Disable Requested Authn Context**. (Optional) If you check this option, Sumo will not include the RequestedAuthnContext element of the SAML AuthnRequests it sends to your Idp. This option is useful if your IdP does not support the RequestedAuthnContext element.
   1. **Sign Authn Request.** (Optional) If you select this option, Sumo will send signed Authn requests to your IdP. When you click this option, a Sumo-provided X-509 certificate is displayed. You can configure your IDP with this certificate, to verify the signature of the Authn requests sent by Sumo. 
1. **Roles Attribute.** When you click this option, the **Roles** **Attribute** field appears. Enter the SAML Attribute Name that is sent by the IdP as part of the assertion. For details, see [Set Up SAML for Single Sign-On](set-up-saml.md).
1. **On-Demand provisioning.** Select this option and specify the following attributes to have Sumo Logic automatically create accounts when a user first logs on. For more information, see [Set Up SAML for Single Sign-On](set-up-saml.md).
   1. **First Name Attribute.** FirstName
   1. **Last Name Attribute.** LastName
   1. **On Demand Provisioning Roles**. Specify the Sumo RBAC roles you want to assign when user accounts are provisioned. (The roles must already exist.)
1. **Logout Page**. Select this option and enter a URL if you'd like to point all users to the URL after logging out of Sumo Logic. For more information, see [Set Up SAML for Single Sign-On.](set-up-saml.md)
1. Click **Add** to save the configuration.
1. To view the details of your configuration, select it the **Configuration List**. The right side of the page displays the **Assertion Consumer**. You'll need to provide it when you complete the Google SAML configuration. <br/><img src={useBaseUrl('img/security/config.png')} alt="Assertion Consumer for a configuration" style={{border: '1px solid gray'}} width="800" />

### Complete the Google SAML App Configuration

1. Go back to the **Google Auth Configuration – Provider Details** dialog, and enter the following information: <br/><img src={useBaseUrl('img/security/ga_saml_service_provider.png')} alt="Service Provider Details page" style={{border: '1px solid gray'}} width="600" />
    * **ACS URL.** This is the **Assertion Consumer** from Sumo Logic
    * **Entity ID.** Enter your Sumo Logic [Service Endpoint URL](/docs/api/about-apis/getting-started#sumo-logic-endpoints-by-deployment-and-firewall-security): <br/>`https://service.<deployment>.sumologic.com`
    * **Name ID.** Basic Information – Primary Email
    * **Name ID Format.** EMAIL
1. Click **Next**.
1. In the **Attribute Mapping** dialog, make the following selections: <br/><img src={useBaseUrl('img/security/ga_saml_attribute_mapping.png')} alt="Attribute Mapping page" style={{border: '1px solid gray'}} width="600" />
    * **FirstName.** Select **Basic Information** and **First Name**.
    * **LastName.** Select **Basic Information** and **Last Name**.
    * **Email.** Select **Basic Information** and **Primary Email**.
1. Click **Finish**.
1. The **Settings for Sumo Logic** page is displayed, and you should see the success message **Setting up SSO for Sumo Logic**. Click **OK**. <br/><img src={useBaseUrl('img/security/ga_saml_message.png')} alt="Setting up SSO for Sumo Logic dialog" style={{border: '1px solid gray'}} width="500" />
1. To enable the Sumo Logic App for everyone, from the menu, select **On for everyone**. <br/><img src={useBaseUrl('img/security/ga_saml_on.png')} alt="On for everyone selected on dropdown menu" style={{border: '1px solid gray'}} width="500" />
1. After a short delay, the new Sumo Logic SAML App will be displayed in your Google Apps login menu. In some cases, it may take up to 10 minutes for the new app to appear. <br/><img src={useBaseUrl('img/security/ga_saml_google_menu.png')} alt="Sumo Logic app in the Google apps menu" style={{border: '1px solid gray'}} width="500" />

## Create multiple SAML configurations

import Saml from '../../../reuse/saml.md';

<Saml/>
