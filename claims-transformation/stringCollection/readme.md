# StringCollection claims transformations unit tests

This folder contains unit tests for Azure AD B2C string collection claims transformations. For more information, check out the [StringCollection claims transformations](https://docs.microsoft.com/azure/active-directory-b2c/stringcollection-transformations) article.

## AddItemToStringCollection

Adds the `string1` and `string2` claims to a new unique values stringCollection claim. If the `string1` and `string2` claims contain the same value, only one claim will be added.  The result of this unit test is a `result` string collection claim that contains the `string1` and `string2` claims. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `string1` and `string2` claims with  default values (you can change the value). The output claims transformation **AddString1** and **AddString2** run the unit test. Select *Continue* to get an ID token with the string collection.
- **AddString1** and **AddString2** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_AddItemToStringCollection/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_AddItemToStringCollection.xml) &nbsp; ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/stringcollection-transformations#additemtostringcollection)

## AddParameterToStringCollection

Adds two predefined strings to a new unique values stringCollection claim. If both strings contain the same value, only one string will be added.  The result of this unit test is a `result` string collection claim that contains both predefined strings. You can find the predefined strings in the **AddString1** and **AddString2** claims transformations' `item` input parameters. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile) technical profile. This technical profile includes output claims transformation **AddString1** and **AddString2** that runs the unit test. Select *Continue* to get an ID token with the string collection.
- **AddString1** and **AddString2** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_AddParameterToStringCollection/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_AddParameterToStringCollection.xml) &nbsp; ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/stringcollection-transformations#addparametertostringcollection)

## GetSingleItemFromStringCollection

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `string1` and `string2` claims with  default values (you can change the values). The output claims transformation **AddString1** and **AddString2** first adds the  `string1` and `string2` claims to the `stringCollection1` string collection claim. Then it runs the unit test **GetFirstElement** claims transformation. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **GetFirstElement** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_GetSingleItemFromStringCollection/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_GetSingleItemFromStringCollection.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/stringcollection-transformations#getsingleitemfromstringcollection)

## StringCollectionContains

Checks if the `groups` string collection claim contains a predefined string. We first populate the `groups` string collection claim with two values *Contributors*, and *READERS* using the **AddString1** and **AddString2** claims transformation. Then we run the unit test **IsReader** claims transformation. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile) technical profile. This technical profile includes output claims transformation **AddString1** and **AddString2** and **IsReader**. The last one runs the unit test. Select *Continue* to get an ID token with the string collection.
- **IsReader** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_StringCollectionContains/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_StringCollectionContains.xml) &nbsp; ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/stringcollection-transformations#stringcollectioncontains)

## StringCollectionContainsClaim

Checks if the `stringCollection1` string collection claim contains the value of `stringToSearch` claim. We first populate the `stringCollection1` string collection claim with the `string1` and `string` claims using the **AddString1** and **AddString2** claims transformation. Then we run the unit test **SearchTheStringCollection** claims transformation. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. The output claims transformation **AddString1** and **AddString2** first adds the  `string1` and `string2` claims to the `stringCollection1` string collection claim. Then, it runs the unit test **GetFirstElement** claims transformation. Select *Continue* to run the next orchestration step that shows the result.
- **SearchTheStringCollection** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **SearchTheStringCollection** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_StringCollectionContainsClaim/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_StringCollectionContainsClaim.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations#stringcollectioncontainsclaim)

