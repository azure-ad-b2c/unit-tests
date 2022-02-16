# Self-asserted technical profile

This folder contains unit tests for Azure AD B2C Self-asserted technical profile. For more information, check out the [Define a self-asserted technical profile](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) article.

## Forgot password link location

Demonstrates the forgot password link [setting.forgotPasswordLinkLocation](https://review.docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile?branch=pr-en-us-188474#metadata) metadata options. The unit test defines the following components:

- *WelcomeTechnicalProfile* - welcome page where you can choose between the options.
- *BlockPageTechnicalProfile* - sign-up block message (we don't want to allow users to sign-in in this unit test)
- **ExperimentalTechnicalProfile-[option]** is the unit test.
- The user journey checks the value of the *scenario* claim (selected on the first page), and redirects to the corresponding *ExperimentalTechnicalProfile-[option]* unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_SA_metadata_setting_forgotPasswordLinkLocation/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../../media/policy.png) [Policy](TP_SA_metadata_setting_forgotPasswordLinkLocation.xml) &nbsp; ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile#metadata)

