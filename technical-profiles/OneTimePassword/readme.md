# One-time password technical profile

This folder contains unit tests for the One-time password technical profile. For more information, check out the [Define an One-time password technical profile in an Azure AD B2C custom policy](https://docs.microsoft.com/azure/active-directory-b2c/one-time-password-technical-profile) article.

## Generate an OTP

The unit test generates and presents an OTP. 

To test this policy:

1. Run the [B2C_1A_TP_OneTimePassword](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_OneTimePassword/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) policy.
1. Type an email address. This can be a fake one. Then select **Send verification code**.
1. Type any value and select **Verify**, then select **Continue**. 
1. The OTP code should be presented for you.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_OneTimePassword/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp;  ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../../media/policy.png) [Policy](TP_OneTimePassword.xml) &nbsp; ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/one-time-password-technical-profile)


## Number of code generation attempts

The unit test checks the limits the number of code generation attempts metadata. The `NumCodeGenerationAttempts` metadata is per identifier. For example, if the identifier is the user's email address, you can send up to 3 email. But, it the user types another email, there will be other 3 attempts. 

To test this policy:

1. Run the [B2C_1A_TP_OneTimePassword_NumCodeGenerationAttempts](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_OneTimePassword_NumCodeGenerationAttempts/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) policy.
1. Type an email address. This can be a fake one. Then select **Send verification code**.
1. Select **Send new code** three times and an error message will return. 
1. Repeat the steps above with another email. This time you get another three attempts.

The unit test defines the following components:

- *ExperimentalSetupTechnicalProfile* - Self-asserted technical profile where you provide the email address.
- *ExperimentalTechnicalProfile-GenerateCode* - Generates code, but doesn't send it.
- *ExperimentalTechnicalProfile-VerifyCode* - Validates the code. Since this policy doesn't send the code, you can check any value to test the maximum number of attempts. 

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_OneTimePassword_NumCodeGenerationAttempts/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp;  ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../../media/policy.png) [Policy](TP_OneTimePassword_NumCodeGenerationAttempts.xml) &nbsp; ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/one-time-password-technical-profile)

