---
id: integrate-aws-sso
title: Integrate Sumo with AWS Single Sign-On
description: Learn how to configure  AWS Single Sign-On for Sumo Logic.
---

import useBaseUrl from '@docusaurus/useBaseUrl';

## Availability

| Account Type | Account Level |
|:--------------|:---------------------------------------------------------------------|
| CloudFlex    | Enterprise |
| Credits      | Trial, Enterprise Operations, Enterprise Security, Enterprise Suite |

This section has instructions for configuring AWS Single Sign-On with Sumo Logic. 

:::note
AWS Single Sign-On does not currently support sending assigned group names in a SAML assertion attribute. For this reason, Sumo Logic does not support on-demand role provisioning with AWS Single Sign-On. You must assign Sumo Logic roles to each user after the user account provisioning has occurred. 
:::

## Step 1: Create a AWS Single Sign-On Application 

1. Open the AWS Management Console.
1. Go to the **AWS Single Sign-on** Service.
1. Select **Applications** from the left navigation.
1. Click **Add a New Application**. 
1. Search the AWS SSO Application Catalog for "Sumo Logic".  <br/><img src={useBaseUrl('img/security/add-new-application.png')} alt="Add New Application dialog" style={{border: '1px solid gray'}} width="600" />
1. Click on the matching Sumo Logic application.
1. Click the **Add application** button.
1. The **Configure Sumo Logic** page appears. <br/><img src={useBaseUrl('img/security/configure-sumologic.png')} alt="Configure Sumo Logic page" style={{border: '1px solid gray'}} width="600" />   
1. Click **Download Certificate** in the **AWS SSO Metadata** section of the page. You'll need the certificate later in this procedure. Keep the AWS configuration page open for now, as you'll need to access it to complete the AWS Single Sign-on configuration. 

## Step 2: Configure SAML in Sumo Logic

This section has instructions for configuring basic SAML in Sumo Logic.

1. Open a new browser window and login to your Sumo Logic account. 
1. [**Classic UI**](/docs/get-started/sumo-logic-ui-classic). In the main Sumo Logic menu, select **Administration > Security > SAML**. <br/>[**New UI**](/docs/get-started/sumo-logic-ui). In the top menu select **Administration**, and then under **Account Security Settings** select **SAML**. You can also click the **Go To...** menu at the top of the screen and select **SAML**. 
1. Click **Add Configuration**.   <br/><img src={useBaseUrl('img/security/sumo-saml-config-list.png')} alt="Add Configuration button on the Configure List page" style={{border: '1px solid gray'}} width="600" />         
1. The **Add Configuration** page appears. <br/><img src={useBaseUrl('img/security/saml-configuration-page.png')} alt="Add Configuration page" style={{border: '1px solid gray'}} width="600" />   
1. **Configuration Name**. Enter a name for the configuration, for example “AWS Single Sign-On”.
1. **Debug Mode**. Select this option if you'd like to view additional details if an error occurs when a user attempts to authenticate. For more information, see [View SAML Debug Information](view-saml-debug-information.md).
1. **Issuer**. Paste in the **AWS SSO Issuer URL** from the **AWS SSO Metadata** section of your AWS SSO configuration. 
1. **X.509 Certificate**. Open the certificate file you downloaded from AWS in a text editor. Copy all text from the file and paste it in here.  
1. **Attribute mapping**. Select **Use SAML Subject**.
1. **On-demand account provisioning**. (Optional) If you configure this feature, Sumo Logic will create a new user’s account the first time the user accesses Sumo Logic using AWS Single Sign-on. To configure on-demand provisioning, you supply the **First Name** and **Last Name** attributes that AWS Single Sign-on uses to identify users, and the Sumo roles you want to assign to the accounts created.
    * Click the **On Demand Provisioning** checkbox.  <br/><img src={useBaseUrl('img/security/on-demand-provisioning.png')} alt="On Demand Provisioning checkbox" style={{border: '1px solid gray'}} width="600" />           
    * **First Name**. Enter: `FirstName `
    * **Last Name**. Enter: `LastName `
    * **On Demand Provisioning Roles**. Specify the Sumo RBAC roles you want to assign when user accounts are first provisioned. (The roles must already exist in Sumo.) If you enter multiple roles, separate them with commas. For example: `Analyst, CollectorManager`
1. Click **Save**. 
1. To view the details of your configuration, select it the **Configuration List.**   <br/><img src={useBaseUrl('img/security/sumo-config-list.png')} alt="A configuration selected on the Configuration List page" style={{border: '1px solid gray'}} width="800" /> 
1. Keep the panel open. When you complete the AWS Single Sign-on configuration below, you will copy the **Assertion Consumer** and **Entity ID** values into AWS Single Sign-on. <br/><img src={useBaseUrl('img/security/assertion-consumer.png')} alt="AWS Single Sign-On dialog" style={{border: '1px solid gray'}} width="400" /> 

## Step 3: Complete SAML configuration in AWS Single Sign-on.

1. Return to the **Configure Sumo Logic** page in AWS Single Sign-on.
1. Paste the **Assertion Consumer** value from Sumo Logic into the **Application ACS URL** field in the **Application Metadata** section of the page.    <br/><img src={useBaseUrl('img/security/application-metadata.png')} alt="Application ACS URL in the Application Metadata section" style={{border: '1px solid gray'}} width="800" /> 
1. Paste the **Entity Id** value from Sumo Logic into the **Application SAML audience** field in the **Application Metadata** section of the page. 
1. Click **Save Changes**. 
1. On the **Assigned Users** tab of your new AWS SSO configuration, click **Assign users**.    <br/><img src={useBaseUrl('img/security/assign-users.png')} alt="Assign Users tab" style={{border: '1px solid gray'}} width="800" /> 
1. Select the individual users or groups that you want to allow to sign into Sumo Logic using AWS SSO. If you have not previously configured AWS Single Sign on you may need to first add your users and groups, as described in AWS help:
    * [Add Users](https://docs.aws.amazon.com/singlesignon/latest/userguide/addusers.html)
    * [Add Groups](https://docs.aws.amazon.com/singlesignon/latest/userguide/addgroups.html)
    * [Add Users to Groups](https://docs.aws.amazon.com/singlesignon/latest/userguide/adduserstogroups.html)
1. Click **Assign Users** to complete the addition of your users to the configuration.

This completes the setup for AWS Single Sign-On to Sumo Logic. Your users should now be able to sign in to Sumo Logic from your AWS SAML Application page by clicking the SumoLogic tile. 
