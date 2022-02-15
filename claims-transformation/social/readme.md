# Social claims transformations unit tests

This folder contains unit tests for Azure AD B2C Social claims transformations. For more information, check out the [Integer claims transformations](https://docs.microsoft.com/azure/active-directory-b2c/social-transformations) article.

## AddItemToAlternativeSecurityIdCollection

Adds the `alternativeSecurityId1` and `alternativeSecurityId1` claims to the `result` claim. To run this unit test, we first create two alternative security IDs using the *CreateFirstAlternativeSecurityId*, and *CreateSecondAlternativeSecurityId* claims transformation. Then we add the `alternativeSecurityId1` and `alternativeSecurityId1` claims to the `result` collection using the **AddFirstAlternativeSecurityId** and **AddSecondAlternativeSecurityId** claims transformation. The result of this unit test is the `result` claim that contains the two alternative security IDs.

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `issuerUserId1`, `identityProvider1`, `issuerUserId2`, `identityProvider2` claims with default values (you can change the values). The output claims transformation first call the *CreateFirstAlternativeSecurityId*, and *CreateSecondAlternativeSecurityId* claims transformation. Then it calls the **AddFirstAlternativeSecurityId** and the **AddSecondAlternativeSecurityId** claims transformation. The last two ones are the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **AddFirstAlternativeSecurityId** and **AddSecondAlternativeSecurityId** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_AddItemToAlternativeSecurityIdCollection/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_AddItemToAlternativeSecurityIdCollection.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/social-transformations#additemtoalternativesecurityidcollection)

## CreateAlternativeSecurityId

Creates alternativeSecurityId claim type `result` from `issuerUserId1`  and `identityProvider1`. The result of this unit test is the `result` claim that contains the alternative security IDs in a JSON format. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `issuerUserId1`, `identityProvider1` claims with default values (you can change the values). The output claims transformation first call the *CreateFirstAlternativeSecurityId*, and *CreateSecondAlternativeSecurityId* unit tests. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **CreateFirstAlternativeSecurityId** and **CreateSecondAlternativeSecurityId** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_CreateAlternativeSecurityId/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_CreateAlternativeSecurityId.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/social-transformations#createalternativesecurityid)


## GetIdentityProvidersFromAlternativeSecurityIdCollectionTransformation

Returns list of issuers from the `alternativeSecurityIdCollection` claim into the `result` (stringCollection claim). To run this unit test we first:

1. Create the `alternativeSecurityId1` and `alternativeSecurityId2`, from user IDs and identity providers name.
1. Add the `alternativeSecurityId1` and `alternativeSecurityId2` to the `AlternativeSecurityIds` claim.
1. Returns list of issuers from the `alternativeSecurityIdCollection` claim into the `result`.

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `issuerUserId1`, `identityProvider1`, `issuerUserId2`, `identityProvider2` claims with default values (you can change the values). The output claims transformation first call the *CreateFirstAlternativeSecurityId*,  *CreateSecondAlternativeSecurityId*, *AddFirstAlternativeSecurityId* and *AddSecondAlternativeSecurityId* claims transformation. Then it calls the unit test *ExtractIdentityProviders* claims transformation. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **ExtractIdentityProviders** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_AGetIdentityProvidersFromAlternativeSecurityIdCollectionTransformation/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_GetIdentityProvidersFromAlternativeSecurityIdCollectionTransformation.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/social-transformations#getidentityprovidersfromalternativesecurityidcollectiontransformation)

## RemoveAlternativeSecurityIdByIdentityProvider

Removes the `identityProvider1` from an alternativeSecurityIdCollection claim. To run this unit test we first:

1. Create the `alternativeSecurityId1` and `alternativeSecurityId2`, from user IDs and identity providers name.
1. Add the `alternativeSecurityId1` and `alternativeSecurityId2` to the `result` claim.
Removes the `identityProvider1` from an `result` claim.

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `issuerUserId1`, `identityProvider1`, `issuerUserId2`, `identityProvider2` claims with default values (you can change the values). The output claims transformation first call the *CreateFirstAlternativeSecurityId*,  *CreateSecondAlternativeSecurityId*, *AddFirstAlternativeSecurityId* and *AddSecondAlternativeSecurityId* claims transformation. Then it calls the unit test *RemoveAlternativeSecurityIdByIdentityProvider* claims transformation. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **RemoveAlternativeSecurityIdByIdentityProvider** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_RemoveAlternativeSecurityIdByIdentityProvider/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_RemoveAlternativeSecurityIdByIdentityProvider.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/social-transformations#removealternativesecurityidbyidentityprovider)