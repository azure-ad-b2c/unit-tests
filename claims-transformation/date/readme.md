# Date claims transformations unit tests

This folder contains examples for Azure AD B2C date claims transformations unit tests. For more information, see [Date claims transformations](https://docs.microsoft.com/azure/active-directory-b2c/date-transformations).

## AssertDateTimeIsGreaterThan

Asserts whether the `date1` claim is greater than the `date2` claim. An error is thrown if `date2` is later than `date1`. The transformation treats values as equal if they are within 5 minutes (30000 milliseconds) difference. It won't throw an error if the values are equal because `AssertIfEqualTo` is set to `false`.

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `date1` and `date2` claims with default values (you can change the values). Select *Continue* the run the **ExperimentalValidation** validation technical profile.
- **ExperimentalValidation** - [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile) type of [validation technical profile](https://docs.microsoft.com/azure/active-directory-b2c/validation-technical-profile). This validation technical profile invokes the **AssertDates** claims transformation, which runs the assertion.
- **AssertDates** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_AssertDateTimeIsGreaterThan/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_AssertDateTimeIsGreaterThan.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/date-transformations#assertdatetimeisgreaterthan)

## ConvertDateTimeToDateClaim

Converts the `dateTimeClaims` claim (type of dateTime), into `result` claim (type of date). After the claims transformation is completed the time part of the date will be removed.

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile first calls the **GetSystemDateTime** adn **ConvertToDate** input claims transformations. Then, renders the `dateTimeClaims` with default value, and `result` claims with the result value of this claims transformation.
- **GetSystemDateTime** claims transformation - Set default value to the `dateTimeClaims` claim using [GetCurrentDateTime](https://docs.microsoft.com/azure/active-directory-b2c/date-transformations#getcurrentdatetime) claims transformation.
- **ConvertToDate** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_ConvertDateTimeToDateClaim/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_ConvertDateTimeToDateClaim.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/date-transformations#convertdatetimetodateclaim)

## ConvertDateToDateTimeClaim

Converts the `dateClaim` claim (type of date), into `result` claim (type of dateTime). After the claims transformation is completed the 00:00:00 time will be added to the `result` claim.

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `dateClaim` claim with default value (you can change the value). Then it calls the **ConvertToDateTime** output claims transformation to convert the date to dateTime.
- **ConvertToDateTime** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_ConvertDateToDateTimeClaim/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_ConvertDateToDateTimeClaim.xml) &nbsp; ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/date-transformations#convertdatetodatetimeclaim)

## DateTimeComparison

Determines if the `dateTime1` claim plus the `timeSpanInSeconds` parameter (5 seconds) is later than the `dateTime2` claim. The `result` claim is a new Boolean claim with a value of `true` or `false`.

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `dateTime1` and `dateTime2` where you can choose the dates to compare. Then it runs the **CompareDates** output claims transformation. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **CompareDates** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_DateTimeComparison/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_DateTimeComparison.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/date-transformations#datetimecomparison)

## GetCurrentDateTime

Shows how to get the current data and time into the `result` claim.

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile first calls the **GetResult** input claims transformation. Then, shows the `result` claim with the current date time.
- **GetResult** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_GetCurrentDateTime/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_GetCurrentDateTime.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/date-transformations#getcurrentdatetime)

## IsTermsOfUseConsentRequired

Determines if the `dateTime1` easier than the `2022-01-15T00:00:00`. The `result` claim is a new Boolean claim with a value of `true` or `false`. If you select date that is later than `2022-01-15T00:00:00` the result will be `false`. Otherwise, it will be `true`.

The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `dateTime1` where you can choose a date to compare with `2022-01-15T00:00:00`. Then it runs the output claims transformation. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **CompareDates** claims transformation - the unit test. The `2022-01-15T00:00:00` date is configure in this claims transformation.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_IsTermsOfUseConsentRequired/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_IsTermsOfUseConsentRequired.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/date-transformations#istermsofuseconsentrequired)
