# Claims unit tests

This folder contains unit tests for Azure AD B2C claims. For more information, check out the [ClaimsSchema](https://docs.microsoft.com/azure/active-directory-b2c/claimsschema) article.

## User input types

Azure AD B2C supports various user input types, such as a textbox, password, and dropdown list that can be used when manually entering claim data for the claim type. This unit test shows the types of [UserInputType](https://docs.microsoft.com/azure/active-directory-b2c/claimsschema#userinputtype). 

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Claim_UserInputTypes_All/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../media/policy.png) [Policy](Claim_UserInputTypes_All.xml) &nbsp;  ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/claimsschema#userinputtype)


## Simple mask

The claim [Simple mask](https://docs.microsoft.com/azure/active-directory-b2c/claimsschema#mask) indicates that the text mask is applied to the leading portion of a string claim.  This unit test shows how to use the claim mask type of `Simple` with verity of formats.

Provide a phone number, then select *Continue*. The *ExperimentalTechnicalProfile* technical profile calls the *CopyPhoneNumber* claims transformations to copy the phone number you provided `inputPhoneNumber` into the `outputPhoneNumber` claims. The next page renders the `outputPhoneNumber` claims with the corresponding format.

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Claim_Mask_Simple/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../media/policy.png) [Policy](Claim_Mask_Simple.xml) &nbsp;  ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/claimsschema#mask)

## Regex mask

The claim [Regex mask](https://docs.microsoft.com/azure/active-directory-b2c/claimsschema#mask) indicates that a regular expression is applied to the string claim as whole. This unit test shows how to use the claim mask type of `Regex` with verity of formats.

Provide an email address, then select *Continue*. The *ExperimentalTechnicalProfile* technical profile calls the *CopyEmail* claims transformations to copy the email address you provided `inputEmail` into the `outputEmail` claims. The next page renders the `outputEmail` claims with the corresponding format.

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Claim_Mask_Regex/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../media/policy.png) [Policy](Claim_Mask_Regex.xml) &nbsp;  ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/claimsschema#mask)

## Regex restriction pattern

The claim [Regex restriction pattern](https://learn.microsoft.com/en-us/azure/active-directory-b2c/claimsschema#pattern) defines a regular expression that claim must match in order to be valid.

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Claim_Restriction_RegularExpression/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../media/policy.png) [Policy](Claim_Restriction_RegularExpression.xml) &nbsp;  ![documentation](../media/doc.png) [Documentation](https://learn.microsoft.com/en-us/azure/active-directory-b2c/claimsschema#pattern)

## Enumeration restriction 

The claim [Restriction enumeration](https://docs.microsoft.com/azure/active-directory-b2c/claimsschema#enumeration) defines available options for the user to select for a claim in the user interface, such as a value in a CheckboxMultiSelect, DropdownSingleSelect, or RadioSingleSelect. This unit test shows the usage of restriction enumeration in a claim definition and localization.

This unit test includes the following claims:

- *Dropdown1* a string dropdown claim. It defines the restriction enumeration options in the claim definition. The options will be presented for all languages.
- *Dropdown2* a string dropdown claim. It defines the restriction enumeration options localization section of the policy (Spanish and Hindi). For other languages the options from the claim definition will be presented. 
- *Dropdown3* a string dropdown claim. It defines the restriction enumeration options localization section of the policy (Spanish and Hindi). For other languages the dropdown list will be empty.

![live demo](../media/demo.png) [Live demo (default)](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Claim_Restriction_Enumeration/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![live demo Spanish](../media/demo.png) [Live demo (Spanish)](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Claim_Restriction_Enumeration/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login&ui_locales=es-es) &nbsp; ![live demo Hindi](../media/demo.png) [Live demo (Hindi)](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Claim_Restriction_Enumeration/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login&ui_locales=hi) &nbsp; ![live demo German](../media/demo.png) [Live demo (German)](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Claim_Restriction_Enumeration/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login&ui_locales=de-De) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../media/policy.png) [Policy](Claim_Restriction_Enumeration.xml) &nbsp;  ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/claimsschema#enumeration)