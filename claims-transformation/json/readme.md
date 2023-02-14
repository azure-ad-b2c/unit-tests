# JSON claims transformations unit tests

This folder contains unit tests for Azure AD B2C JSON claims transformations. For more information, check out the [Integer claims transformations](https://docs.microsoft.com/azure/active-directory-b2c/json-transformations) article.

## CreateJsonArray

Create a JSON single element array from the `string1` claim value. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `string1` claim with a default value (you can change the value). The output claims transformation **CreateJsonPayload** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **CreateJsonPayload** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_CreateJsonArray/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_CreateJsonArray.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/json-transformations#createjsonarray)

## GenerateJson

Use the `boolean1`, `dateTime1`, `int1`, `long1` and `string1` claims and constants values to generate a JSON string. The path string following dot notation is used to indicate where to insert the data into a JSON string. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `boolean1`, `dateTime1`, `int1`, `long1` and `string1` claims claim with default values (you can change the values). Note, the `long1` claim is initiated with a value but not presented. The output claims transformation **GenerateJsonPayload** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **GenerateJsonPayload** claims transformation - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_GenerateJson/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_GenerateJson.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/json-transformations#generatejson)

## GetClaimFromJson

Gets the displayName (`resultDisplayName` claim), email (`resultEmail` claim), givenName (`resultGivenName` claim) and surname (`resultSurname` claim) from a JSON data. The results of this unit test are the `resultDisplayName`, `resultEmail`, `resultGivenName`, and `resultSurname` claims that contain extracted values. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `inputJson` claim with default JSON (you can change the JSON). Note, if the JSON isn't valid, or an element not found, the policy won't continue to the next step. The output claims transformations run the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **GetDisplayNameClaimFromJson**, **GetEmailClaimFromJson**, **GetGivenNameClaimFromJson**, **GetSurnameClaimFromJson** claims transformations - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_GetClaimFromJson/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_GetClaimFromJson.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/json-transformations#getclaimfromjson)

## GetClaimsFromJsonArray

Get the `displayName` (string), `membershipID` (int), `active` (boolean), and `birthDate` (dateTime) from the `inputJson` Json data. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `inputJson` claim with default JSON (you can change the JSON). Note, if the JSON isn't valid, or an element not found, the policy won't continue to the next step. Select *Continue* the run the validation technical profiles.
- [Validation technical profiles](https://docs.microsoft.com/azure/active-directory-b2c/validation-technical-profile) (type of [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile)):
  - **ExperimentalValidation-DontIncludeEmptyClaims** - invokes the **GetClaimsFromJsonDontIncludeEmptyClaims* claims transformation, which doesn't include empty claims.
  - **ExperimentalValidation-IncludeEmptyClaims** - invokes the **GetClaimsFromJsonIncludeEmptyClaims* claims transformation, which includes empty claims.
- Claims transformations:
  - **GetClaimsFromJsonDontIncludeEmptyClaims** claims transformation - the increment unit test.
  - **GetClaimsFromJsonIncludeEmptyClaims** claims transformation - the decrement unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_GetClaimsFromJsonArray/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_GetClaimsFromJsonArray.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/json-transformations#getclaimsfromjsonarray)


## GetClaimsFromJsonArrayV2

Get the `displayName` (string), `membershipID` (int), `active` (boolean), and `birthDate` (dateTime) from the `inputJson` a string collection JSON elements. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `inputJson1`, `inputJson2`, `inputJson3`, and `inputJson4`, claims with default JSON (you can change the JSON). Note, if the JSON aren't valid, or an element not found, the policy won't continue to the next step. Select *Continue* the run the validation technical profiles. 
- Claims transformations:
  - **AddJsonToStringCollection1** adds the `inputJson1` into the `inputJsonStringCollection` string collection.
  - **AddJsonToStringCollection2** adds the `inputJson2` into the `inputJsonStringCollection` string collection.
  - **AddJsonToStringCollection3** adds the `inputJson3` into the `inputJsonStringCollection` string collection.
  - **AddJsonToStringCollection4** adds the `inputJson4` into the `inputJsonStringCollection` string collection.
  - **GetClaimsFromJson** - the decrement unit test. It reads the values from the `inputJsonStringCollection` claims 

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_GetClaimsFromJsonArrayV2/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_GetClaimsFromJsonArrayV2.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/json-transformations#getclaimsfromjsonarrayv2)



## GetNumericClaimFromJson

Gets the **id** element from a JSON data. The result of this unit test is the `result` claim that contains extracted values. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `inputJson` claim with default JSON (you can change the JSON). Note, if the JSON isn't valid, or an element not found, the policy won't continue to the next step. The output claims transformations run the unit test. The output claims transformation **GetIdFromJson** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **GetIdFromJson** claims transformations - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_GetNumericClaimFromJson/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_GetNumericClaimFromJson.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/json-transformations#getnumericclaimfromjson)

## GetSingleItemFromJson

Gets the first element key (`resultKey` claim) and value (`resultValue` claim) from a JSON data. Note, you can change the name of the key and value to something else, by changing the claims transformation's output claims `TransformationClaimType` attribute. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `inputJson` claim with default JSON (you can change the JSON). Note, if the JSON isn't valid, or an element not found, the policy won't continue to the next step. The output claims transformations run the unit test. The output claims transformation **GetKeyValueFromJson** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **GetKeyValueFromJson** claims transformations - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_GetSingleItemFromJson/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_GetSingleItemFromJson.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/json-transformations#getsingleitemfromjson)

## GetSingleValueFromJsonArray

Gets the first element from a JSON data array (`inputJson` claim). The result of this unit test is a `result` claim that contains the first element. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile renders the `inputJson` claim with default JSON (you can change the JSON). Note, if the JSON isn't valid, or an element not found, the policy won't continue to the next step. The output claims transformations run the unit test. The output claims transformation **GetFirstItemFromJson** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **GetFirstItemFromJson** claims transformations - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_GetSingleValueFromJsonArray/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_GetSingleValueFromJsonArray.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/json-transformations#getsinglevaluefromjsonarray)


## XmlStringToJsonString

Converts the XML data (`inputXML` claim) to JSON format.  The result of this unit test is a `result` claim that contains the JSON. The unit test defines the following elements:

- **ExperimentalTechnicalProfile** - [claims transformation](https://docs.microsoft.com/azure/active-directory-b2c/claims-transformation-technical-profile) technical profile. This technical profile sets the `inputXML` claim with default XML (you can change the XML). Note, if the XML isn't valid, or an element not found, the policy won't continue to the next step. The output claims transformations run the unit test. The output claims transformation **ConvertXmlToJson** runs the unit test. Select *Continue* to run the next orchestration step that shows the result.
- **ResultTechnicalProfile** - [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile. This technical profile shows the `result` of this unit test.
- **ConvertXmlToJson** claims transformations - the unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CT_XmlStringToJsonString/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../../media/policy.png) [Policy](CT_XmlStringToJsonString.xml) &nbsp;  ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/json-transformations#xmlstringtojsonstring)
