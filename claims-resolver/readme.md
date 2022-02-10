# Claim resolvers

This folder contains unit tests for Azure AD B2C claim resolvers. For more information, check out the [About claim resolvers in Azure Active Directory B2C custom policies](https://docs.microsoft.com/azure/active-directory-b2c/claim-resolver-overview) article.

## Context

Demonstrates how to use the contextual claim resolvers of the authorization request. The unit test defines the **ExperimentalTechnicalProfile**  [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile with the following:

- `IncludeClaimResolvingInClaimsHandling` metadata is set to `true`.  
- `InputClaim` sets the `DefaultValue` to the claim resolver, and also sets the `AlwaysUseDefaultValue` to `true`.
- `OutputClaim` renders the claims on the screen and returns them back to the next orchestration step.

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CR_Context/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../media/policy.png) [Policy](CR_Context.xml) &nbsp; ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/claim-resolver-overview#context)

## Culture

Demonstrates how to use the culture claim resolvers with information about the language used in the authorization request. The unit test defines the **ExperimentalTechnicalProfile**  [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile with the following:

- `IncludeClaimResolvingInClaimsHandling` metadata is set to `true`.  
- `InputClaim` sets the `DefaultValue` to the claim resolver, and also sets the `AlwaysUseDefaultValue` to `true`.
- `OutputClaim` renders the claims on the screen and returns them back to the next orchestration step.

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CR_Culture/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../media/policy.png) [Policy](CR_Culture.xml) &nbsp; ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/claim-resolver-overview#culture)

## Policy

Demonstrates how to use the policy claim resolvers with information about the policy used in the authorization request. The unit test defines the **ExperimentalTechnicalProfile**  [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile with the following:

- `IncludeClaimResolvingInClaimsHandling` metadata is set to `true`.  
- `InputClaim` sets the `DefaultValue` to the claim resolver, and also sets the `AlwaysUseDefaultValue` to `true`.
- `OutputClaim` renders the claims on the screen and returns them back to the next orchestration step.

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CR_Policy/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../media/policy.png) [Policy](CR_Policy.xml) &nbsp; ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/claim-resolver-overview#policy)

## OpenID Connect relying party application

Demonstrates how to use the OIDC claim resolvers with information about the OpenID Connect authorization request. The unit test defines the **ExperimentalTechnicalProfile**  [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile with the following:

- `IncludeClaimResolvingInClaimsHandling` metadata is set to `true`.  
- `InputClaim` sets the `DefaultValue` to the claim resolver, and also sets the `AlwaysUseDefaultValue` to `true`.
- `OutputClaim` renders the claims on the screen and returns them back to the next orchestration step.

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_CR_OIDC/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login&login_hint=someone@contoso.com&domain_hint=facebook.com&acr_values=mfa&max_age=1234) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../media/policy.png) [Policy](CR_OIDC.xml) &nbsp; ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/claim-resolver-overview#openid-connect)

## SAML Service provider

Demonstrates how to use the SAML claim resolvers with information about the SAML authorization request. The unit test defines the **ExperimentalTechnicalProfile**  [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile with the following:

- `IncludeClaimResolvingInClaimsHandling` metadata is set to `true`.  
- `InputClaim` sets the `DefaultValue` to the claim resolver, and also sets the `AlwaysUseDefaultValue` to `true`.
- `OutputClaim` renders the claims on the screen and returns them back to the next orchestration step.

![live demo](../media/demo.png) [Live demo](https://samltestapp2.azurewebsites.net/SP) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../media/policy.png) [Policy](CR_SAML.xml) &nbsp; ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/claim-resolver-overview#saml)

### Use the SAML Service provider live demo

Use our [SAML test application](https://samltestapp2.azurewebsites.net/SP) to test this policy. In the SAML test app provide the following information:

- **Tenant Name**: `b2clivedemo`
- **B2C Policy**: `B2C_1A_CR_SAML`
- **Issuer**: `https://b2clivedemo.onmicrosoft.com/samlapp`
