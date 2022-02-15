# Phone number claims transformations unit tests

This folder contains unit tests for Azure AD B2C phoneNumber claims transformations. For more information, check out the [Integer claims transformations](https://docs.microsoft.com/azure/active-directory-b2c/phone-number-claims-transformations) article.

## ConvertPhoneNumberClaimToString

Converts the `inputPhoneNumber` (phoneNumber data type) into the `result` (string data type).  The result of this unit test is the `result` claim that contains the same phone number. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `inputPhoneNumber` claim with a default value (you can change the value). The output claims transformation **PhoneNumberToString** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **PhoneNumberToString** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_ConvertPhoneNumberClaimToString/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_ConvertPhoneNumberClaimToString.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/phone-number-claims-transformations#convertphonenumberclaimtostring)

## ConvertStringToPhoneNumberClaim

Validates the format of a phone number, a combination of `inputCountryCode` and `inputPhoneNumber` claims. If valid, change it to a standard format used by Azure AD B2C. If the provided phone number isn't in a valid format, an error message is returned. The result of this unit test is the `result` claim that contains the phone number in string format.

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `inputCountryCode` and `inputPhoneNumber` claims with default values (you can change the values). Select *Continue* the run the **ExperimentalValidation** validation technical profile.
- **ExperimentalValidation** - [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile) type of [validation technical profile](https://docs.microsoft.com/azure/active-directory-b2c/validation-technical-profile). This validation technical profile invokes the **ConvertStringToPhoneNumberWithCountryCode** claims transformation, which runs the unit test.
- **ConvertStringToPhoneNumberWithCountryCode** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_ConvertStringToPhoneNumberClaim/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_ConvertStringToPhoneNumberClaim.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/phone-number-claims-transformations#convertstringtophonenumberclaim)

## ConvertStringToPhoneNumberClaim without country code claim

Validates the format of a phone number  `inputPhoneNumber` claims (that contains the phone number and the country code). If valid, change it to a standard format used by Azure AD B2C. If the provided phone number isn't in a valid format, an error message is returned. The result of this unit test is the `result` claim that contains the phone number in string format.

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `inputCountryCode` claim with a default value (you can change the value). Select *Continue* the run the **ExperimentalValidation** validation technical profile.
- **ExperimentalValidation** - [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile) type of [validation technical profile](https://docs.microsoft.com/azure/active-directory-b2c/validation-technical-profile). This validation technical profile invokes the **ConvertStringToPhoneNumberWithoutCountryCode** claims transformation, which runs the unit test.
- **ConvertStringToPhoneNumberWithoutCountryCode** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_ConvertStringToPhoneNumberClaim_WithoutCountryCodeClaim/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_ConvertStringToPhoneNumberClaimWithoutCountryCodeClaim.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/phone-number-claims-transformations#convertstringtophonenumberclaim)

## GetNationalNumberAndCountryCodeFromPhoneNumberString

Extracts the country/region code and the national number from the input `phoneNumber`. It throws an exception if the supplied phone number isn't valid. The result of this unit test is the `resultNationalNumber` and `resultCountryCode` claims that contain the phone number (local) and the country code. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `phoneNumber` claim with a  default value (you can change the value). Select the type of the country code *ISO3166*, or *CallingCode*. Then, select *Continue* to run the validation technical profiles.
- [Validation technical profile](https://docs.microsoft.com/azure/active-directory-b2c/validation-technical-profile) (type of [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile)):
  - **ExperimentalValidation-ISO3166** -  This validation technical profile invokes the **GetNationalNumberAndCountryCodeISO3166Format** claims transformation, which gets the country code in ISO3166 format.
    - **ExperimentalValidation-CallingCode** -  This validation technical profile invokes the **GetNationalNumberAndCountryCodeCallingCodeFormat** claims transformation, which gets the country code in CallingCode format.
- Claims transformations:
  - **GetNationalNumberAndCountryCodeISO3166Format** claims transformation - the unit test.
  - **GetNationalNumberAndCountryCodeCallingCodeFormat** claims transformation - the unit test.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_GetNationalNumberAndCountryCodeFromPhoneNumberString/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_GetNationalNumberAndCountryCodeFromPhoneNumberString.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/phone-number-claims-transformations#getnationalnumberandcountrycodefromphonenumberstring)