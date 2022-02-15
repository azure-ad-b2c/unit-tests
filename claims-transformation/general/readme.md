# General claims transformations unit tests

This folder contains unit tests for Azure AD B2C general claims transformations. For more information, check out the [General claims transformations](https://docs.microsoft.com/azure/active-directory-b2c/general-transformations) article.

## CopyClaim

Copy value of `int1` into `int1Result`, and `string1` into `string1Result`. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `int1` and `string1` claims with default values (you can change the values). The output claims transformation **CopyString** and **CopyInt** run the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `int1Result` and `string1Result` of this unit test.
- **CopyString** and **CopyInt** claims transformations - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_CopyClaim/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_CopyClaim.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/general-transformations#copyclaim)

## DoesClaimExist

- **ExperimentalTechnicalProfile** - [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile) technical profile. This technical profile renders initiates the `int1`, `long1` and `string1` claims with default values. The output claims transformations run the unit test for each type of the claim. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `string1Result`, `int1Result` , `boolean1Result` , `long1Result` , `date1Result` , and `stringCollection1Result` of this unit test.
- Claims transformations: 
  - **CheckString** - the string unit test.
  - **CheckInt** - the int unit test.
  - **CheckBoolean** - the Boolean unit test.
  - **CheckLong** - the long unit test.
  - **CheckDate** - the date unit test.
  - **CheckStringCollection** - the string collection unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_DoesClaimExist/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_DoesClaimExist.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/general-transformations#doesclaimexist)

## Hash

Hashes the provided plain text `stringToHash` claim using the `salt` and a secret that is stored as policy key `B2C_1A_12345Secret`. The secret of this policy key is `12345`. The hashing algorithm used is SHA-256.. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `stringToHash` and `salt` claims with default values (you can change the values). The output claims transformation **GenerateHash** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **GenerateHash** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_Hash/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_Hash.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/general-transformations#hash)