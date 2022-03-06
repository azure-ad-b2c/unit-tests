# Claims unit tests

This folder contains unit tests for Azure AD B2C claims. For more information, check out the [ClaimsSchema](https://docs.microsoft.com/azure/active-directory-b2c/claimsschema) article.

## User input types

Azure AD B2C supports a variety of user input types, such as a textbox, password, and dropdown list that can be used when manually entering claim data for the claim type. This unit test shows the types of [UserInputType](https://docs.microsoft.com/azure/active-directory-b2c/claimsschema#userinputtype). 

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Claim_UserInputTypes_All/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../media/policy.png) [Policy](Claim_UserInputTypes_All.xml) &nbsp;  ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/claimsschema#userinputtype)


## Simple mask

The claim [Simple mask](https://docs.microsoft.com/azure/active-directory-b2c/claimsschema#mask) indicates that the text mask is applied to the leading portion of a string claim.  This unit test shows how to use the claim mask type of `Simple` with verity of formats.

Provide a phone number, then select *Continue*. The *ExperimentalTechnicalProfile* technical profiles calls the *CopyPhoneNumber* claims transformations to copy the phone number you provided `inputPhoneNumber` into the `outputPhoneNumber` claims. The next page renders the `outputPhoneNumber` claims with the corresponding format.

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Claim_Mask_Simple/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../media/policy.png) [Policy](Claim_Mask_Simple.xml) &nbsp;  ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/claimsschema#mask)

## Regex mask

The claim [Regex mask](https://docs.microsoft.com/azure/active-directory-b2c/claimsschema#mask) indicates that a regular expression is applied to the string claim as whole. This unit test shows how to use the claim mask type of `Regex` with verity of formats.

Provide a email address, then select *Continue*. The *ExperimentalTechnicalProfile* technical profiles calls the *CopyEmail* claims transformations to copy the email address you provided `inputEmail` into the `outputEmail` claims. The next page renders the `outputEmail` claims with the corresponding format.

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Claim_Mask_Regex/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../media/policy.png) [Policy](Claim_Mask_Regex.xml) &nbsp;  ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/claimsschema#mask)