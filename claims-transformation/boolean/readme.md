# Boolean claims transformations unit tests

This folder contains unit tests for Azure AD B2C Boolean claims transformations. For more information, check out the [Boolean claims transformations](https://docs.microsoft.com/azure/active-directory-b2c/boolean-transformations) article.

## AndClaims

Computes an **And** operation of `boolean1` and `boolean2` claims, and sets the `result` claim with result of the operation. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `boolean1` and `boolean2` claims with default values (you can change the values). The output claims transformation **AndBooleanClaims** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **AndBooleanClaims** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_AndClaims/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_AndClaims.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/boolean-transformations#andclaims)

## AssertBooleanClaimIsEqualToValue

Asserts that `boolean1` claim is equal to **false**, and throws an exception if it's **true**. The result of this unit test is a `result` claim that is set manually to true. Note, you can change the comparison to **false**, by changing the *AssertBoolean1IsTrue* claims transformation's *valueToCompareTo* input parameter. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `boolean1` claim with a default value (you can change the value). Select *Continue* the run the validation technical profiles.
- **ExperimentalValidation-Ordinal** - [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile) type of [validation technical profile](https://docs.microsoft.com/azure/active-directory-b2c/validation-technical-profile). This validation technical profile invokes the **AssertBoolean1IsTrue-Ordinal** claims transformation, which runs the assertion.
- **AssertBoolean1IsTrue** claims transformation - the unit test. 

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_AssertBooleanClaimIsEqualToValue/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_AssertBooleanClaimIsEqualToValue.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/boolean-transformations#assertbooleanclaimisequaltovalue)

## CompareBooleanClaimToValue

Checks that `boolean1` claim is equal to **false**, and return the result of the compression. Note, you can change the comparison to **false**, by changing the *CheckBoolean1IsTrue* claims transformation's *valueToCompareTo* input parameter.  The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `boolean1` claim with a default value (you can change the value). The output claims transformation **CheckBoolean1IsTrue** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **CheckBoolean1IsTrue** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CompareBooleanClaimToValue/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_CompareBooleanClaimToValue.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/boolean-transformations#comparebooleanclaimtovalue)

## NotClaims

Computes the **Not** operation of the `boolean1` claim and sets the `result` claim with result of the operation. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `boolean1` claim with a default value (you can change the value). The output claims transformation **NotBooleanClaim** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **NotBooleanClaim** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_NotClaims/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_NotClaims.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/boolean-transformations#notclaims)

## OrClaims

Computes an **Or** operation of `boolean1` and `boolean2` claims, and sets the `result` claim with result of the operation. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `boolean1` and `boolean2` claims with default values (you can change the values). The output claims transformation **OrBooleanClaims** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **OrBooleanClaims** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_OrClaims/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_OrClaims.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/boolean-transformations#orclaims)

