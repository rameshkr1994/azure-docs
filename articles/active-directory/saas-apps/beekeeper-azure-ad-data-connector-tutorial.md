---
title: 'Tutorial: Azure Active Directory single sign-on (SSO) integration with Beekeeper Azure AD Data Connector | Microsoft Docs'
description: Learn how to configure single sign-on between Azure Active Directory and Beekeeper Azure AD Data Connector.
services: active-directory
documentationCenter: na
author: jeevansd
manager: mtillman
ms.reviewer: barbkess

ms.assetid: 26c8789a-1bfe-4371-94d5-febe34f0b0e4
ms.service: active-directory
ms.subservice: saas-app-tutorial
ms.workload: identity
ms.tgt_pltfrm: na
ms.topic: tutorial
ms.date: 02/04/2020
ms.author: jeedes

ms.collection: M365-identity-device-management
---

# Tutorial: Azure Active Directory single sign-on (SSO) integration with Beekeeper Azure AD Data Connector

In this tutorial, you'll learn how to integrate Beekeeper Azure AD Data Connector with Azure Active Directory (Azure AD). When you integrate Beekeeper Azure AD Data Connector with Azure AD, you can:

* Control in Azure AD who has access to Beekeeper Azure AD Data Connector.
* Enable your users to be automatically signed-in to Beekeeper Azure AD Data Connector with their Azure AD accounts.
* Manage your accounts in one central location - the Azure portal.

To learn more about SaaS app integration with Azure AD, see [What is application access and single sign-on with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-appssoaccess-whatis).

## Prerequisites

To get started, you need the following items:

* An Azure AD subscription. If you don't have a subscription, you can get a [free account](https://azure.microsoft.com/free/).
* Beekeeper Azure AD Data Connector single sign-on (SSO) enabled subscription.

## Scenario description

In this tutorial, you configure and test Azure AD SSO in a test environment.

* Beekeeper Azure AD Data Connector supports **SP and IDP** initiated SSO
* Beekeeper Azure AD Data Connector supports **Just In Time** user provisioning
* Once you configure the Beekeeper Azure AD Data Connector you can enforce session controls, which protect exfiltration and infiltration of your organization’s sensitive data in real-time. Session controls extend from Conditional Access. [Learn how to enforce session control with Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/proxy-deployment-any-app).

## Adding Beekeeper Azure AD Data Connector from the gallery

To configure the integration of Beekeeper Azure AD Data Connector into Azure AD, you need to add Beekeeper Azure AD Data Connector from the gallery to your list of managed SaaS apps.

1. Sign in to the [Azure portal](https://portal.azure.com) using either a work or school account, or a personal Microsoft account.
1. On the left navigation pane, select the **Azure Active Directory** service.
1. Navigate to **Enterprise Applications** and then select **All Applications**.
1. To add new application, select **New application**.
1. In the **Add from the gallery** section, type **Beekeeper Azure AD Data Connector** in the search box.
1. Select **Beekeeper Azure AD Data Connector** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.


## Configure and test Azure AD single sign-on for Beekeeper Azure AD Data Connector

Configure and test Azure AD SSO with Beekeeper Azure AD Data Connector using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between an Azure AD user and the related user in Beekeeper Azure AD Data Connector.

To configure and test Azure AD SSO with Beekeeper Azure AD Data Connector, complete the following building blocks:

1. **[Configure Azure AD SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    * **[Create an Azure AD test user](#create-an-azure-ad-test-user)** - to test Azure AD single sign-on with B.Simon.
    * **[Assign the Azure AD test user](#assign-the-azure-ad-test-user)** - to enable B.Simon to use Azure AD single sign-on.
1. **[Configure Beekeeper Azure AD Data Connector SSO](#configure-beekeeper-azure-ad-data-connector-sso)** - to configure the single sign-on settings on application side.
    * **[Create Beekeeper Azure AD Data Connector test user](#create-beekeeper-azure-ad-data-connector-test-user)** - to have a counterpart of B.Simon in Beekeeper Azure AD Data Connector that is linked to the Azure AD representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

## Configure Azure AD SSO

Follow these steps to enable Azure AD SSO in the Azure portal.

1. In the [Azure portal](https://portal.azure.com/), on the **Beekeeper Azure AD Data Connector** application integration page, find the **Manage** section and select **single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, click the edit/pen icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, if you have **Service Provider metadata file** and wish to configure in **IDP** initiated mode, perform the following steps:

	a. Click **Upload metadata file**.

    ![Upload metadata file](common/upload-metadata.png)

	b. Click on **folder logo** to select the metadata file and click **Upload**.

	![choose metadata file](common/browse-upload-metadata.png)

	c. After the metadata file is successfully uploaded, the **Identifier** and **Reply URL** values get auto populated in Basic SAML Configuration section.

	![image](common/idp-intiated.png)

	> [!Note]
	> If the **Identifier** and **Reply URL** values do not get auto polulated, then fill in the values manually according to your requirement.

1. Click **Set additional URLs** and perform the following step if you wish to configure the application in **SP** initiated mode:

	In the **Sign-on URL** text box, type a URL using the following pattern:
    `https://<your_company>.beekeeper.io/login`

	> [!NOTE]
    > The Sign-on URL value is not real. Update this value with the actual Sign-on URL. Contact [Beekeeper Azure AD Data Connector Client support team](mailto:support@beekeeper.io) to get this value. You can also refer to the patterns shown in the **Basic SAML Configuration** section in the Azure portal.

1. Beekeeper Azure AD Data Connector application expects the SAML assertions in a specific format, which requires you to add custom attribute mappings to your SAML token attributes configuration. The following screenshot shows the list of default attributes.

	![image](common/default-attributes.png)

1. In addition to above, Beekeeper Azure AD Data Connector application expects few more attributes to be passed back in SAML response which are shown below. These attributes are also pre populated but you can review them as per your requirements.

	| Name | Source Attribute|
	| ------------ | --------- |
	| firstname | user.givenname |
	| lastname | user.surname |
	| email | user.mail |
	| username | user.principalname |
    | position | user.jobtitle |

1. On the **Set up single sign-on with SAML** page, in the **SAML Signing Certificate** section,  find **Federation Metadata XML** and select **Download** to download the certificate and save it on your computer.

	![The Certificate download link](common/metadataxml.png)

1. On the **Set up Beekeeper Azure AD Data Connector** section, copy the appropriate URL(s) based on your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

### Create an Azure AD test user

In this section, you'll create a test user in the Azure portal called B.Simon.

1. From the left pane in the Azure portal, select **Azure Active Directory**, select **Users**, and then select **All users**.
1. Select **New user** at the top of the screen.
1. In the **User** properties, follow these steps:
   1. In the **Name** field, enter `B.Simon`.  
   1. In the **User name** field, enter the username@companydomain.extension. For example, `B.Simon@contoso.com`.
   1. Select the **Show password** check box, and then write down the value that's displayed in the **Password** box.
   1. Click **Create**.

### Assign the Azure AD test user

In this section, you'll enable B.Simon to use Azure single sign-on by granting access to Beekeeper Azure AD Data Connector.

1. In the Azure portal, select **Enterprise Applications**, and then select **All applications**.
1. In the applications list, select **Beekeeper Azure AD Data Connector**.
1. In the app's overview page, find the **Manage** section and select **Users and groups**.

   ![The "Users and groups" link](common/users-groups-blade.png)

1. Select **Add user**, then select **Users and groups** in the **Add Assignment** dialog.

	![The Add User link](common/add-assign-user.png)

1. In the **Users and groups** dialog, select **B.Simon** from the Users list, then click the **Select** button at the bottom of the screen.
1. If you're expecting any role value in the SAML assertion, in the **Select Role** dialog, select the appropriate role for the user from the list and then click the **Select** button at the bottom of the screen.
1. In the **Add Assignment** dialog, click the **Assign** button.

## Configure Beekeeper Azure AD Data Connector SSO

To configure single sign-on on **Beekeeper Azure AD Data Connector** side, you need to send the downloaded **Federation Metadata XML** and appropriate copied URLs from Azure portal to [Beekeeper Azure AD Data Connector support team](mailto:support@beekeeper.io). They set this setting to have the SAML SSO connection set properly on both sides.

### Create Beekeeper Azure AD Data Connector test user

In this section, a user called Britta Simon is created in Beekeeper Azure AD Data Connector. Beekeeper Azure AD Data Connector supports just-in-time user provisioning, which is enabled by default. There is no action item for you in this section. If a user doesn't already exist in Beekeeper Azure AD Data Connector, a new one is created after authentication.

## Test SSO 

In this section, you test your Azure AD single sign-on configuration using the Access Panel.

When you click the Beekeeper Azure AD Data Connector tile in the Access Panel, you should be automatically signed in to the Beekeeper Azure AD Data Connector for which you set up SSO. For more information about the Access Panel, see [Introduction to the Access Panel](https://docs.microsoft.com/azure/active-directory/active-directory-saas-access-panel-introduction).

## Additional resources

- [ List of Tutorials on How to Integrate SaaS Apps with Azure Active Directory ](https://docs.microsoft.com/azure/active-directory/active-directory-saas-tutorial-list)

- [What is application access and single sign-on with Azure Active Directory? ](https://docs.microsoft.com/azure/active-directory/active-directory-appssoaccess-whatis)

- [What is conditional access in Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)

- [Try Beekeeper Azure AD Data Connector with Azure AD](https://aad.portal.azure.com/)

- [What is session control in Microsoft Cloud App Security?](https://docs.microsoft.com/cloud-app-security/proxy-intro-aad)
