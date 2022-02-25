# OAuth2 custom error technical profile

This folder contains unit tests for Azure AD B2C OAuth2 custom error technical profile. For more information, check out the [Define an OAuth2 custom error technical profile](https://docs.microsoft.com/azure/active-directory-b2c/oauth2-error-technical-profile) article.

## Call the custom error message from a user journey

The unit test returns error to the <https://jwt.ms> web app from a [user journey](https://docs.microsoft.com/azure/active-directory-b2c/userjourneys). To test the user experience, provide an error code and error message. Selected *Continue* to return the error message.

The unit test defines the following components:

- *ExperimentalSetupTechnicalProfile* - Self-asserted technical profile where you provide the error code and message.
- *ExperimentalTechnicalProfile* - The unit test

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_None_OAuth2Error/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../../media/policy.png) [Policy](TP_OAuth2_OAuth2Error.xml) &nbsp; ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/oauth2-error-technical-profile)

## Call the custom error message from transfer sub journey

The unit test returns error to the <https://jwt.ms> web app from a [sub journey](https://docs.microsoft.com/azure/active-directory-b2c/subjourneys) (type of transfer). To test the user experience, provide an error code and error message. Selected *Continue* to return the error message. Note, the type of the sub journey must be `transfer`.

The unit test defines the following components:

- *ExperimentalSetupTechnicalProfile* - Self-asserted technical profile where you provide the error code and message.
- *ExperimentalSubJourney* - The transfer sub journey. It calls the ExperimentalTechnicalProfile technical profile.
- *ExperimentalTechnicalProfile* - The unit test

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_None_OAuth2Error_TransferSubJourney/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../../media/policy.png) [Policy](TP_OAuth2_OAuth2Error_TransferSubJourney.xml) &nbsp; ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/oauth2-error-technical-profile)