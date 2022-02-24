# String claims transformations unit tests

This folder contains unit tests for Azure AD B2C string claims transformations. For more information, check out the [String claims transformations](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations) article.

## AssertStringClaimsAreEqual

Asserts whether the `string1` claim is identical to the `string2` claim. An error is thrown if the `string1` and `string2` aren't identical. It allows you to select the type of the conversion *Ordinal* (case sensitive), or *ordinalIgnoreCase* (ignore case).

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `string1` and `string2` claims with default values (you can change the values). Select the type of the conversion *Ordinal* (case sensitive), or *ordinalIgnoreCase* (ignore case). Select *Continue* the run the validation technical profiles.
- **ExperimentalValidation-[option]** - [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile) type of [validation technical profile](https://docs.microsoft.com/azure/active-directory-b2c/validation-technical-profile). This validation technical profile invokes the **AssertStringsAreEqual-[option]** claims transformation, which runs the assertion with the corresponding case sensitive/insensitive configuration.
- **AssertStringsAreEqual-[option]** claims transformations - the unit tests.

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
- **ExperimentalValidation-[option]** - [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile) type of [validation technical profile](https://docs.microsoft.com/azure/active-directory-b2c/validation-technical-profile). This validation technical profile invokes the corresponding **ChangeInputValueTo[option]** claims transformation, which changes the string to lower or upper case.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **ChangeInputValueTo[option]** claims transformations - the unit tests.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_ChangeCase/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_ChangeCase.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations#changecase)

## CompareClaims

Determines whether `string1` claim is equal to `string2` claim. It allows you to select the type of the comparison *equal*, or *not equal*. You can specify whether the comparison should ignore the case of the strings being compared, by editing the claims transformation `ignoreCase` input parameter. The result is a new boolean claim `result` with a value of true or false.

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `string1` and `string2` claims with default values (you can change the values). Select the type of the comparison *equal*, or *not equal*. Then, select *Continue* to run the validation technical profiles.
- **ExperimentalValidation-[option]** - [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile) type of [validation technical profile](https://docs.microsoft.com/azure/active-directory-b2c/validation-technical-profile). This validation technical profile invokes the **CheckStrings-[option]** claims transformation, which checks if the claims are equal or not.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **CheckStrings-[option]** claims transformations - the unit tests.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_CompareClaims/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_CompareClaims.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations#compareclaims)

## CompareClaimToValue

Determines whether `string1` claim is equal to a predefined string `ABC`. It allows you to select the type of the comparison *equal*, or *not equal*. You can specify whether the comparison should ignore the case of the strings being compared, by editing the claims transformation `ignoreCase` input parameter. Also you can change the predefined string `ABC` to any string, by changing the `compareTo` input parameter. The result is a new boolean claim `result` with a value of true or false.

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `string1` and `string2` claims with default values (you can change the values). Select the type of the comparison *equal*, or *not equal*. Then, select *Continue* to run the validation technical profiles.
- **ExperimentalValidation-[option]** - [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile) type of [validation technical profile](https://docs.microsoft.com/azure/active-directory-b2c/validation-technical-profile). This validation technical profile invokes the corresponding **CheckStrings-[option]** claims transformation, which checks if the claims are equal or not.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **CheckStrings-[option]** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_CompareClaimToValue/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_CompareClaimToValue.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations#compareclaimtovalue)

## CopyClaimIfPredicateMatch

Tries to copy the `string1` claim value to `result` claim. It will copy the value only if the `string1` is in international phone number format, as configured in the **internationalOrNationalPhoneNumber** predicate. 

When you provide a valid phone number, the claim will be copy to the result. When you select *Continue*, you'll see the exact same value on the result page. But if you provide any string, such as email address, the result claim will be empty. 

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `string1` claim with default values (you can change the values). The output claims transformation **SetResultIfPredicateMatch** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **CreateUriString** claims transformation - the unit test.
- **internationalOrNationalPhoneNumber** [predicate](https://docs.microsoft.com/azure/active-directory-b2c/predicates) that checks whether the user's input is in international phone number format.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_CopyClaimIfPredicateMatch/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_CopyClaimIfPredicateMatch.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations#copyclaimifpredicatematch)

## CreateOtpSecret

Creates a TOTP string claim. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. The input claims transformation **SetResultIfPredicateMatch** of this technical profile runs the **CreateOtpSecret**. 
- **CreateOtpSecret** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_CreateOtpSecret/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_CreateOtpSecret.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations#createotpsecret)

## CreateRandomString

Creates a random string using the random number or GUID generator. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile lets you choose the type of the transformation. Then, select *Continue* to run the validation technical profiles.
- [Validation technical profiles](https://docs.microsoft.com/azure/active-directory-b2c/validation-technical-profile) (type of [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile)):
  - **ExperimentalValidation-Integer** - invokes the **CreateIntegerRandomValue** claims transformation, which creates an integer random value.
  - **ExperimentalValidation-IntegerWithFormat** - invokes the **CreateIntegerWithFormatRandomValue** claims transformation, which creates an integer random value. The return value is formatted `ID_{the random value}`.
  - **ExperimentalValidation-IntegerWithFormatWithBase64** - invokes the **CreateIntegerWithFormatRandomValue** claims transformation, which creates an integer random value. The return value is formatted `ID_{the random value}` then converted into base64.
  - **ExperimentalValidation-GUID** - invokes the **CreateGUIDRandomValue** claims transformation, which creates a GUID random value.
  - **ExperimentalValidation-GUIDWithFormat** - invokes the **CreateGUIDWithFormatRandomValue** claims transformation, which creates a GUID random value. The return value is formatted `ID_{the random value}`.
  - **ExperimentalValidation-GUIDWithFormatWithBase64** - invokes the **CreateGUIDWithFormatRandomValue** claims transformation, which creates a GUID random value. The return value is formatted `ID_{the random value}` then converted into base64.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- Claims transformations:
  - **CreateIntegerRandomValue** - creates an integer random value unit test.
  - **CreateIntegerWithFormatRandomValue** - creates an integer random value with format  unit test.
  - **CreateIntegerWithFormatWithBase64RandomValue** - creates an integer random value with format, and base64  unit test.
  - **CreateGUIDRandomValue** - creates a GUID random value unit test.
  - **CreateGUIDWithFormatRandomValue** - creates a GUID random value with format  unit test.
  - **CreateGUIDWithFormatWithBase64RandomValue** - creates a GUID random value with format, and base64  unit test.
  
![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_CreateRandomString/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_CreateRandomString.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations#createrandomstring)

## CreateStringClaim

Sets the value of the `result` claim to `Contoso terms of service...`. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile calls the **SetStringClaimValue** input claims transformation. Then renders the `result` output claim to the screen.
- **SetStringClaimValue** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_CreateStringClaim/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_CreateStringClaim.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations#createstringclaim)

## FormatLocalizedString

Formats the `string1`, `string2` and `string3` claims according to a provided localized format string. The result of this unit test is a `result` claim that contains new formatted string. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `string1`, `string2` and `string3` claims with default values (you can change the values). The output claims transformation **SetResponseMessage** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **SetResponseMessage** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_FormatLocalizedString/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_FormatLocalizedString.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations#formatlocalizedstring)

## FormatStringClaim

Formats the `string1` claim according to the provided format string. The result of this unit test is a `result` claim that contains new formatted string. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `string1` claim with a default value (you can change the value). The output claims transformation **FormatString1** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **FormatString1** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_FormatStringClaim/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_FormatStringClaim.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations#formatstringclaim)

## FormatStringMultipleClaims

Formats the `string1` and `string2` claims according to the provided format string. The result of this unit test is a `result` claim that contains new formatted string. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `string1` and `string2` claim with a default value (you can change the value). The output claims transformation **FormatString1AndString2** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **FormatString1AndString2** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_FormatStringMultipleClaims/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_FormatStringMultipleClaims.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations#formatstringmultipleclaims)


## GetLocalizedStringsTransformation

Copies localized strings into the `string1`, `string2`, `string3`, and `string4` claims. The result of this unit test is a `result` claim that contains the corresponding values from the `LocalizedString` element. 

The unit test policy supports the English (en) and Spanish (es) languages. Check the policy with the browser's default language and explicitly provide the `ui_locales` query string parameter with other languages. For example, [default language](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_GetLocalizedStringsTransformation/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=logi), [Spanish](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_GetLocalizedStringsTransformation/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=logi&ui_locales=de). Other languages that are not configured in this policy, such as [German](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_GetLocalizedStringsTransformation/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=logi&ui_locales=de) will return empty values. To avoid such a case (empty values), make sure you include of all the required languages in your policy.

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile calls the **GetLocalizedStringsForEmail** input claims transformation. Then renders the `result` output claim to the screen.
- **GetLocalizedStringsForEmail** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_GetLocalizedStringsTransformation/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_GetLocalizedStringsTransformation.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations#getlocalizedstringstransformation)

## GetMappedValueFromLocalizedCollection

Looks up a localized string of the `result` claim and sets the value to the `result` claim. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `code` claim with a default value (you can change the value). The code that you provide is used to search for the corresponding `Item` localization element's `Text`. The output claims transformation **GetValueByCode** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **GetValueByCode** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_GetMappedValueFromLocalizedCollection/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_GetMappedValueFromLocalizedCollection.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations#getmappedvaluefromlocalizedcollection)

## LookupValue

Looks up a value from a list of values in the **GetValueById** claims transformation input parameters collections. The lookup is done based on the value of the `idToLookup`. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `idToLookup` claim with a default value (you can change the value). The idToLookup that you provide is used to search for the corresponding `Id` input parameter. Note, if you select the *fabrikam.com* value, an empty string will be return. Since there isn't such ID in the claims transformation. The output claims transformation **GetValueById** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **GetValueById** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_LookupValue/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_LookupValue.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations#lookupvalue)

## NullClaim

Cleans the value of the `string1` claim. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `string1` claim with a default value (you can change the value). The output claims transformation **NullString** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `string1` with empty string.
- **GetValueById** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_NullClaim/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_NullClaim.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/nullclaim)

## ParseDomain

Gets the domain portion of the `string1` email. The result of this unit test is a `result` claim that contains the domain part of the `string1` claim. If the provide email address isn't valid an empty string return. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `string1` claim with a default value (you can change the value). The output claims transformation **GetDomainName** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **GetDomainName** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_ParseDomain/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_ParseDomain.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/parsedomain)

## SetClaimIfBooleansMatch

Checks that the `boolean1` claim is true, or false. If true, sets the `result` output claim with the value present in outputClaimIfMatched input parameter of the **SetClaimIfBooleansClaimIsTrue** claims transformation.

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `boolean1` claim with a default value (you can change the value). The output claims transformation **SetClaimIfBooleansClaimIsTrue** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **SetClaimIfBooleansClaimIsTrue** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_SetClaimIfBooleansMatch/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_SetClaimIfBooleansMatch.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/setclaimifbooleansmatch)

## SetClaimsIfRegexMatch

Checks that the `string1` claim is matched to the **CheckIfStringsAreEqual** claims transformation's `matchTo` input parameter (a phone number format). If match, sets the:

- `resultValue` output claims with the value present in `outputClaimIfMatched` input parameter.
- `resultMatch` output claim with true or false based on the result of comparison.

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `string1` claim with a default value (you can change the value). The output claims transformation **SetIfString1RegexMatch** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `resultValue`, `resultCode`, and `resultMatch` claims.
- **SetIfString1RegexMatch** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_SetClaimsIfRegexMatch/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_SetClaimsIfRegexMatch.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/setclaimsifregexmatch)

## SetClaimsIfRegexMatch with Groups

Checks that the `string1` claim is matched to the **CheckIfStringsAreEqual** claims transformation's `matchTo` input parameter (email format). This mode of the claims transformation also should extract the Regex group values. If match, sets the:

- `resultValue` output claims with the value present in `outputClaimIfMatched` input parameter.
- `resultGroup1` output claims with the Regex group as configured in the `matchTo` input parameter.
- `resultMatch` output claim with true or false based on the result of comparison.

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `string1` claim with a default value (you can change the value). The output claims transformation **SetIfString1RegexMatch** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `resultValue`, `resultCode`, and `resultMatch` claims.
- **SetIfString1RegexMatch** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_SetClaimsIfRegexMatch_WithGrouping/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_SetClaimsIfRegexMatch_WithGrouping.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/setclaimsifregexmatch)


## SetClaimsIfStringsAreEqual

Checks that the `string1` claim is matched to the **CheckIfStringsAreEqual** claims transformation's `matchTo` input parameter. If match, sets the:

- `resultValue` output claims with the value present in `stringMatchMsg` input parameters.
- `resultCode` output claims with the value present in `stringMatchMsgCode` input parameters
- `resultMatch` output claim with true or false based on the result of comparison.

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `string1` claim with a default value (you can change the value). The output claims transformation **CheckIfStringsAreEqual** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `resultValue`, `resultCode`, and `resultMatch` claims.
- **CheckIfStringsAreEqual** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_SetClaimsIfStringsAreEqual/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_SetClaimsIfStringsAreEqual.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/setclaimsifstringsareequal)

## SetClaimsIfStringsMatch

Checks that the `string1` claim is matched to the **CheckIfStringMatch** claims transformation's `matchTo` input parameter. If match, sets the `result` output claims with the value present in `outputClaimIfMatched` input parameter, along with compare result `resultMatch` claim, which is to be set as true or false based on the result of comparison.

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `string1` claim with a default value (you can change the value). The output claims transformation **CheckIfStringMatch** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile.This technical profile shows the `result` of this unit test.
- **CheckIfStringMatch** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_SetClaimsIfStringsMatch/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_SetClaimsIfStringsMatch.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/setclaimsifstringsmatch)

## StringContains

Determines whether a specified substring occurs within the `string1` claim. The result is the `result` claim with a value of true or false. true if the value parameter occurs within this string, otherwise, false. You can whether to ignore case or not.

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `string1` claim with a default value (you can change the value). Select whether to ignore case (case insensitive), nor (case sensitive). Select *Continue* the run the validation technical profiles.
- [Validation technical profiles](https://docs.microsoft.com/azure/active-directory-b2c/validation-technical-profile) (type of [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile)):
  - **ExperimentalValidation-IgnoreCase** - invokes the **CheckIsString1Contains-IgnoreCase** claims transformation, which searches the substring with case insensitive configuration.
  - **ExperimentalValidation-RespectCase** - invokes the **CheckIsString1Contains-RespectCase** claims transformation, which searches the substring with case sensitive configuration.
- Claims transformations:
  - **CheckIsString1Contains-IgnoreCase** claims transformation - the case insensitive unit test.
  - **CheckIsString1Contains-RespectCase** claims transformation - the case sensitive unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_StringContains/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_StringContains.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations#stringcontains)

## StringJoin

Concatenates the elements of the `groups` string collection claim, using the specified separator between each element or member. The result is the `result` claim which a comma delimiter string of the `groups` string collection.

To test the functionality of the StringJoin claims transformation, we first collect the `string1` and `string2` claims. Then We add these claims to the `groups` string collection using the **AddString1** and **AddString2** claims transformation. After the claims are added to the string collection, the unit test converts them back to the `result` string claim type.

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `string1` and `string2` claims with  default values (you can change the values). The technical profile runs the following claims transformations:
  1. **AddString1** adds the `string1` to the `groups` claim.
  1. **AddString2** adds the `string2` to the `groups` claim.
  1. **ConvertStringCollectionToCommaDelimiterString** runs the unit test.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **ConvertStringCollectionToCommaDelimiterString** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_StringJoin/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_StringJoin.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/parsedomain)

## StringReplace

Searches the `string1` claim type string for a specified value (`-`) as specified in the **NormalizePhoneNumber** claims transformation's `oldValue` input parameter, and replaces with the value of the `newValue` input parameter (empty string). The result of this unit test is a `result` claim that contains the new string (after the replacement). The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `string1` claim with a default value (you can change the value). The output claims transformation **NormalizePhoneNumber** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **NormalizePhoneNumber** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_StringReplace/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_StringReplace.xml) &nbsp; ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations#stringreplace)

## StringSplit

Splits the `string1` claim into the `result` string collection of substrings. It splits the string using the comma delimiter (`-`) as configure in the **ConvertStringToStringCollection** claims transformation's `delimiter` input claim. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `string1` claim with a default value (you can change the value). The output claims transformation **ConvertStringToStringCollection** runs the unit test. Select *Continue* to get an ID token with the string collection.
- **ConvertStringToStringCollection** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_StringSplit/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_StringSplit.xml) &nbsp; ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations#stringsplit)

## StringSubstring

Extracts parts of the `string1` claim type, beginning at the character at the specified position, and returns the specified number of characters. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `string1` claim with a default value (you can change the value). The output claims transformation **GetCodePrefix** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **GetCodePrefix** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_StringSubstring/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_StringSubstring.xml) &nbsp; ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations#stringsubstring)