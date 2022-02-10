# String claims transformations unit tests

This folder contains unit tests for Azure AD B2C string claims transformations. For more information, check out the [String claims transformations](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations) article.

## AssertStringClaimsAreEqual

Asserts whether the `string1` claim is identical to the `string2` claim. An error is thrown if the `string1` and `string2` aren't identical. It allows you to select the type of the conversion *Ordinal* (case sensitive), or *ordinalIgnoreCase* (ignore case).

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `string1` and `string2` claims with default values (you can change the values). Select the type of the conversion *Ordinal* (case sensitive), or *ordinalIgnoreCase* (ignore case). Select *Continue* the run the validation technical profiles.
- **ExperimentalValidation-Ordinal** - [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile) type of [validation technical profile](https://docs.microsoft.com/azure/active-directory-b2c/validation-technical-profile). This validation technical profile invokes the **AssertStringsAreEqual-Ordinal** claims transformation, which runs the assertion with case sensitive configuration.
- **ExperimentalValidation-OrdinalIgnoreCase** - [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile) type of [validation technical profile](https://docs.microsoft.com/azure/active-directory-b2c/validation-technical-profile). This validation technical profile invokes the **AssertStringsAreEqual-OrdinalIgnoreCase** claims transformation, which runs the assertion with case insensitive configuration.
- **AssertStringsAreEqual-Ordinal** claims transformation - the case sensitive unit test.
- **AssertStringsAreEqual-OrdinalIgnoreCase** claims transformation - the case insensitive unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_AssertStringClaimsAreEqual/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_AssertStringClaimsAreEqual.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations#assertstringclaimsareequal)

## BuildUri

Combines the user's unique identifier `uriLabel` claim, and a secret key `secretKey` claims. The result of this unit test is a `result` claim that contains a time based on time password (TOTP) URI. Some of the parameters can't be changed via the user interface. To change these values, edit the **CreateUriString** claims transformation input parameters `scheme`, `host` and `query.issuer`. 

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `uriLabel` and `secretKey` claims with default values (you can change the values). The output claims transformation **CreateUriString** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **CreateUriString** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_BuildUri/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_BuildUri.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations#builduri)

## ChangeCase

Changes the case of `inputValue` claim to lower or upper case into the `result` claim. It allows you to select the type of the change to upper or lower case. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `inputValue` claim with default value (you can change the values). Select the type of the conversion *lower*, or *upper*. Then, select *Continue* to run the validation technical profiles.
- **ExperimentalValidation-ToLower** - [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile) type of [validation technical profile](https://docs.microsoft.com/azure/active-directory-b2c/validation-technical-profile). This validation technical profile invokes the **ChangeInputValueToLower** claims transformation, which changes the string to lower case.
- **ExperimentalValidation-ToUpper** - [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile) type of [validation technical profile](https://docs.microsoft.com/azure/active-directory-b2c/validation-technical-profile). This validation technical profile invokes the **ChangeInputValueToUpper** claims transformation, which changes the string to upper case.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **ChangeInputValueToLower** claims transformation - to lower case unit test.
- **ChangeInputValueToUpper** claims transformation - to upper case unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_ChangeCase/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_ChangeCase.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations#changecase)

## CompareClaims

Determines whether `string1` claim is equal to `string2` claim. It allows you to select the type of the comparison *equal*, or *not equal*. You can specify whether the comparison should ignore the case of the strings being compared, by editing the claims transformation `ignoreCase` input parameter. The result is a new boolean claim `result` with a value of true or false.

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `string1` and `string2` claims with default values (you can change the values). Select the type of the comparison *equal*, or *not equal*. Then, select *Continue* to run the validation technical profiles.
- **ExperimentalValidation-Equal** - [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile) type of [validation technical profile](https://docs.microsoft.com/azure/active-directory-b2c/validation-technical-profile). This validation technical profile invokes the **CheckStrings-Equal** claims transformation, which checks if the claims are equal.
- **ExperimentalValidation-NotEqual** - [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile) type of [validation technical profile](https://docs.microsoft.com/azure/active-directory-b2c/validation-technical-profile). This validation technical profile invokes the **CheckStrings-NotEqual** claims transformation, which checks if the claims are not equal.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **CheckStrings-Equal** claims transformation - strings equal unit test.
- **CheckStrings-NotEqual** claims transformation - strings not equal unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_CompareClaims/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_CompareClaims.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations#compareclaims)

## CompareClaimToValue

Determines whether `string1` claim is equal to a predefined string `ABC`. It allows you to select the type of the comparison *equal*, or *not equal*. You can specify whether the comparison should ignore the case of the strings being compared, by editing the claims transformation `ignoreCase` input parameter. Also you can change the predefined string `ABC` to any string, by changing the `compareTo` input parameter. The result is a new boolean claim `result` with a value of true or false.

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `string1` and `string2` claims with default values (you can change the values). Select the type of the comparison *equal*, or *not equal*. Then, select *Continue* to run the validation technical profiles.
- **ExperimentalValidation-Equal** - [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile) type of [validation technical profile](https://docs.microsoft.com/azure/active-directory-b2c/validation-technical-profile). This validation technical profile invokes the **CheckStrings-Equal** claims transformation, which checks if the claims are equal.
- **ExperimentalValidation-NotEqual** - [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile) type of [validation technical profile](https://docs.microsoft.com/azure/active-directory-b2c/validation-technical-profile). This validation technical profile invokes the **CheckStrings-NotEqual** claims transformation, which checks if the claims are not equal.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **CheckStrings-Equal** claims transformation - strings equal unit test.
- **CheckStrings-NotEqual** claims transformation - strings not equal unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_CompareClaimToValue/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_CompareClaimToValue.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations#compareclaimtovalue)

## CopyClaimIfPredicateMatch

Tries to copy the `string1` claim value to `result` claim. It will copy the value only if the `string1` is in international phone number format, as configured in the **internationalOrNationalPhoneNumber** predicate. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `string1` claim with default values (you can change the values). The output claims transformation **SetResultIfPredicateMatch** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **CreateUriString** claims transformation - the unit test.
- **internationalOrNationalPhoneNumber** [predicate](https://docs.microsoft.com/azure/active-directory-b2c/predicates) that checks whether the user's input is in international phone number format.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_CopyClaimIfPredicateMatch/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_CopyClaimIfPredicateMatch.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations#copyclaimifpredicatematch)