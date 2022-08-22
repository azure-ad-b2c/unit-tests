# RESTful technical profile

This folder contains unit tests for the RESTful technical profile. For more information, check out the [Define an RESTful technical profile in an Azure AD B2C custom policy](https://docs.microsoft.com/azure/active-directory-b2c/restful-technical-profile) article.

## Send claims in query string

This unit test that demonstrates how to send a claim in a query string parameter of the REST api HTTP request. It uses the `<Item Key="SendClaimsIn">QueryString</Item>` metadata. The unit test invokes the <https://api.genderize.io/> API. For more information, check out the <https://genderize.io/> documentation.

To test this policy:

1. Run the [B2C_1A_TP_Restful_SendClaimsIn_QueryString](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_Restful_SendClaimsIn_QueryString/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) policy.
1. Type a name, or except the default one 'Jessica', and select **Continue**.
1. The next orchestration step calls the REST API, sending the givenName as a _name_ query string parameter to the API
1. The next orchestration step renders the result of the API, which includes the _gender_ and the _count_ of the provided name (the probability indicates the certainty of the assigned gender).


The unit test defines the following components:

- *ExperimentalSetupTechnicalProfile* - Self-asserted technical profile where you provide the name to be checked.
- *ExperimentalTechnicalProfile-GenderiseAPI* - The unit test.
- *ResultTechnicalProfile* - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_Restful_SendClaimsIn_QueryString/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp;  ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../../media/policy.png) [Policy](TP_Restful_SendClaimsIn_QueryString) &nbsp; ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/restful-technical-profile)

