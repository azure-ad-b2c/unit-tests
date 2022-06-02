# Azure AD MFA technical profile

This folder contains unit tests for the Azure AD MFA technical profile. For more information, check out the [Define an Azure AD MFA technical profile in an Azure AD B2C custom policy](https://docs.microsoft.com/azure/active-directory-b2c/multi-factor-auth-technical-profile) article.

## Trigger the Azure MFA technical profile

The unit test asks to provide an email address and then run through the phone-factor technical profile.

The following screenshot shows the [Azure AD B2C audit logs](https://docs.microsoft.com/azure/active-directory-b2c/view-audit-logs) with the Phone-factor entries.

![Azure AD B2C Audit log](./media/audit-logs.png)

The unit test defines the following components:

- *ExperimentalSetupTechnicalProfile* - Self-asserted technical profile where you provide the email address.
- *ExperimentalTechnicalProfile* - The unit test

![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../../media/policy.png) [Policy](TP_AadSspr.xml) &nbsp; ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/multi-factor-auth-technical-profile)

