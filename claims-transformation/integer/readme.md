# Integer claims transformations unit tests

This folder contains unit tests for Azure AD B2C integer claims transformations. For more information, check out the [Integer claims transformations](https://docs.microsoft.com/azure/active-directory-b2c/integer-transformations) article.

## AdjustNumber

Increases or decreases the `int1` numeric claim. The result of this unit test is a `result` claim that contains the new value. This technical profile lets you choose the type of the transformation (increase or decrease). The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `int1` claim with a default value (you can change the value) and the `typeOfTransformation`. The `typeOfTransformation` allows you to choose the transformation type (increase or decrease). Select *Continue* the run the validation technical profiles.
- [Validation technical profiles](https://docs.microsoft.com/azure/active-directory-b2c/validation-technical-profile) (type of [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile)):
  - **ExperimentalValidation-Increment** - invokes the **increaseInt* claims transformation, which increases the number.
  - **ExperimentalValidation-Decrement** - invokes the **increaseInt* claims transformation, which decreases the number.
- Claims transformations:
  - **increaseInt** claims transformation - the increment unit test.
  - **increaseInt** claims transformation - the decrement unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_AdjustNumber/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_AdjustNumber.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/integer-transformations#adjustnumber)

## AssertNumber

Determines whether the `int1` numeric claim is greater, lesser, equal, or not equal to a fixed number `20`. You can configure this number in the claims transformations' `CompareToValue` input parameter. The result of this unit test is a `result` claim that contains the `false` value (since when it's true an error message will be shown). This technical profile lets you choose the type of the transformation, such as greater than or less than. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `int1` claim with a default value (you can change the value) and the `typeOfTransformation`. The `typeOfTransformation` allows you to choose the transformation type. Select *Continue* the run the validation technical profiles.
- [Validation technical profiles](https://docs.microsoft.com/azure/active-directory-b2c/validation-technical-profile) (type of [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile)):
  - **ExperimentalValidation-Equal** - invokes the **AssertNumberIsEqual* claims transformation.
  - **ExperimentalValidation-GreaterThan** - invokes the **AssertNumberIsGreaterThan* claims transformation.
  - **ExperimentalValidation-GreaterThanOrEqual** - invokes the **AssertNumberIsGreaterThanOrEqual* claims transformation.
  - **ExperimentalValidation-LessThan** - invokes the **AssertNumberIsLessThan* claims transformation.
  - **ExperimentalValidation-LessThanOrEqual** - invokes the **AssertNumberIsLessThanOrEqual* claims transformation.
  - **ExperimentalValidation-NotEqual** - invokes the **AssertNumberIsNotEqual* claims transformation.
- Claims transformations:
  - **AssertNumberIsEqual** claims transformation - the equal unit test.
  - **AssertNumberIsGreaterThan** claims transformation - the greater than unit test.
  - **AssertNumberIsGreaterThanOrEqual** claims transformation - the greater than or equal unit test.
  - **AssertNumberIsLessThan** claims transformation - the less than unit test.
  - **AssertNumberIsLessThanOrEqual** claims transformation - the less than or equal unit test.
  - **AssertNumberIsNotEqual** claims transformation - the not equal unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_AssertNumber/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_AssertNumber.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/integer-transformations#assertnumber)


## ConvertNumberToStringClaim

Converts the `long1` claim (long data type() into the `result` string data type. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile) technical profile. This technical profile sets the value of the `long1` claim. The output claims transformation **ConvertIntToString** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **ConvertIntToString** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_ConvertNumberToStringClaim/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_ConvertNumberToStringClaim.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/string-transformations#convertnumbertostringclaim)
