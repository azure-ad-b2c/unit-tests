# login-NonInteractive technical profile

This folder contains unit tests for Azure AD B2C login-NonInteractive technical profile. For more information, check out the [Local and social accounts sign-up or sign-in user journey overview](https://github.com/Azure-Samples/active-directory-b2c-custom-policy-starterpack/tree/main/SocialAndLocalAccounts) article.

## Force password reset

As an administrator, you can reset a user's password if the user forgets their password. Or you would like to force them to reset the password. When an administrator resets a user's password, the value of the `forceChangePasswordNextLogin` claim is true. The unit test reads and renders this claim.

### Run the unit test

To check out the user experience of this policy, follow these steps:

1. If you don't have an account, [create a local account](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_signup_signin/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https://jwt.ms&scope=openid&response_type=id_token&prompt=login) with your email address.

1. [Run](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_LNI_PasswordExpiration/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) the *B2C_1A_TP_LNI_PasswordExpiration* policy to check the value of the *forceChangePasswordNextLogin* claim. At this point it should be false. 

1. At this step you need to simulate a force password reset flow. Since you don't have access to the live demo tenant. We've prepared a helper policy that changes the value of the *forceChangePasswordNextLogin* to true. [Run](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Demo_Helper_SignUp_SignIn_ForcePasswordReset/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) the helper policy. Sign-up or sign-in and provide a new password. This policy  will simulate an admin changing the password for the user. Sign-in with the same account from step 1, and provide a new password. After you run this step, that account will be force to reset the password.

1. [Run](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_LNI_PasswordExpiration/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) the *B2C_1A_TP_LNI_PasswordExpiration* policy again. It will check the value of the *forceChangePasswordNextLogin* claim. This time it should be true.

### Building blocks

The unit test defines the following components:

- Claims:
  - *continueOnPasswordExpiration* - input claims of the login-NonInteractive technical profile. It instructs Azure AD B2C to continue upon password expiration.
  - *forceChangePasswordNextLogin* - output claims of the login-NonInteractive technical profile. It indicates whether the user needs to reset the password.

- Technical profiles:
  -*login-NonInteractive* - The technical profile that validates the credentials. It customizes the one in the [base policy](https://github.com/Azure-Samples/active-directory-b2c-custom-policy-starterpack/blob/main/SocialAndLocalAccounts/TrustFrameworkBase.xml), adding the input and output claims.
  - *SelfAsserted-LocalAccountSignIn-Email* - The technical profile that renders the sign-up and sign-in page. It customizes the one in the [base policy](https://github.com/Azure-Samples/active-directory-b2c-custom-policy-starterpack/blob/main/SocialAndLocalAccounts/TrustFrameworkBase.xml), adding a call to the *AAD-UserReadUsingSignInName* technical profile to get the user attributes.
  - *AAD-UserReadUsingSignInName*  - If the forceChangePasswordNextLogin claim is true, other claims don't return. So, it gets the user objectId by the sign-in name.
  - *ResultTechnicalProfile* - Shows the result of this unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_LNI_PasswordExpiration/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../../media/policy.png) [Policy](TP_LNI_PasswordExpiration.xml) &nbsp; ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/force-password-reset?pivots=b2c-custom-policy)
