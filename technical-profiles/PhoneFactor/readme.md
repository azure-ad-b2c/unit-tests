# Phone-factor technical profile

This folder contains unit tests for the Phone-factor technical profile. For more information, check out the [Define a phone factor technical profile in an Azure Active Directory B2C custom policy](https://docs.microsoft.com/azure/active-directory-b2c/phone-factor-technical-profile) article.

## Trigger the phone factor

The unit test asks to provide an email address and then run through the phone-factor technical profile.

The following screenshot shows the [Azure AD B2C audit logs](https://docs.microsoft.com/azure/active-directory-b2c/view-audit-logs) with the Phone-factor entries. The entries where the **target** starts with `31ee61cf-521f` the test run with a user that has a registered phone number. The second user where the **target** starts with `9344bed3-8676` without registered phone number.

![Azure AD B2C Audit log](./media/audit-logs.png)

The unit test defines the following components:

- *ExperimentalSetupTechnicalProfile* - Self-asserted technical profile where you provide the email address.
- *ExperimentalTechnicalProfile* - The unit test

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_PhoneFactor/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../../media/policy.png) [Policy](TP_PhoneFactor.xml) &nbsp; ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/phone-factor-technical-profile)

