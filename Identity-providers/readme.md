# Identity providers

This folder contains unit tests for Azure AD B2C identity providers. For more information, check out the [Add an identity provider to your Azure Active Directory B2C tenant](https://docs.microsoft.com/azure/active-directory-b2c/add-identity-provider) article.

## Azure Active Directory

Demonstrates how to federate with Azure AD multi-tenant app.

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_IDP_AAD_Multi/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../media/policy.png) [Policy](Azure-AD/IDP_AAD_Multi.xml) &nbsp; ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/identity-provider-azure-ad-multi-tenant?pivots=b2c-custom-policy)

## Azure Active Directory with access token

Demonstrates how to federate with Azure AD multi-tenant app, and get the access token. With the access token you can call MS Graph API. To use the access token to call MS Graph API, grant the Azure AD multi-tenant app permission, such as `User.Read`. Then, in the *AADCommon-OpenIdConnect* technical profile add the required permission to the *scope* metadata. For example, `https://graph.microsoft.com/User.Read`.

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_IDP_AAD_Multi_AccessToken/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../media/policy.png) [Policy](Azure-AD/IDP_AAD_Multi_AccessToken.xml) &nbsp; ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/idp-pass-through-user-flow?pivots=b2c-custom-policy)

## Facebook

Demonstrates how to federate with Facebook identity provider. 

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_IDP_Facebook/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../media/policy.png) [Policy](Facebook/IDP_Facebook.xml) &nbsp; ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/identity-provider-facebook?pivots=b2c-custom-policy)

## Facebook with access token

Demonstrates how to federate with Facebook identity provider, and get the access token. With the access token you can call Graph API.

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_IDP_Facebook_AccessToken/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../media/policy.png) [Policy](Facebook/IDP_Facebook_AccessToken.xml) &nbsp; ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/idp-pass-through-user-flow?pivots=b2c-custom-policy)

## GitHub

Demonstrates how to federate with GitHub identity provider. 

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_IDP_GitHub/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../media/policy.png) [Policy](GitHub/IDP_GitHub.xml) &nbsp; ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/identity-provider-google?pivots=b2c-custom-policy)

## GitHub with access token

Demonstrates how to federate with GitHub identity provider, and get the access token. With the access token you can call Graph API.

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_IDP_GitHub_AccessToken/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../media/policy.png) [Policy](GitHub/IDP_GitHub_AccessToken.xml) &nbsp; ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/idp-pass-through-user-flow?pivots=b2c-custom-policy)

## Google

Demonstrates how to federate with Google identity provider. 

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_IDP_Google/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../media/policy.png) [Policy](Google/IDP_Google.xml) &nbsp; ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/identity-provider-google?pivots=b2c-custom-policy)

## Google with access token

Demonstrates how to federate with Google identity provider, and get the access token. With the access token you can call Graph API.

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_IDP_Google_AccessToken/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../media/policy.png) [Policy](Google/IDP_Google_AccessToken.xml) &nbsp; ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/idp-pass-through-user-flow?pivots=b2c-custom-policy)

## Mobile ID

Demonstrates how to federate with Mobile ID identity provider.

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_IDP_MobileID/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../media/policy.png) [Policy](MobileID/IDP_MobileId.xml) &nbsp; ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/add-identity-provider)
