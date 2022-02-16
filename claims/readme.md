# Claims unit tests

This folder contains unit tests for Azure AD B2C claims. For more information, check out the [ClaimsSchema](https://docs.microsoft.com/azure/active-directory-b2c/claimsschema) article.

## User input types

Azure AD B2C supports a variety of user input types, such as a textbox, password, and dropdown list that can be used when manually entering claim data for the claim type. This unit test shows the types of [UserInputType](https://docs.microsoft.com/azure/active-directory-b2c/claimsschema#userinputtype). 

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Claim_UserInputTypes_All/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../media/policy.png) [Policy](CT_AndClaims.xml) &nbsp;  ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/claimsschema#userinputtype)

