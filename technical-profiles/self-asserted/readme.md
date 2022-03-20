# Self-asserted technical profile

This folder contains unit tests for Azure AD B2C Self-asserted technical profile. For more information, check out the [Define a self-asserted technical profile](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) article.

## Allow generation off claims with Null values

The [AllowGenerationOfClaimsWithNullValues](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile#metadata) metadata defines whether to allow to generate a claim with null value. For example, in a case user doesn't select a checkbox. 

To run the unit test, follow these steps:

1. Run the [B2C_1A_TP_SA_metadata_AllowGenerationOfClaimsWithNullValues](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_SA_metadata_AllowGenerationOfClaimsWithNullValues/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) policy.
1. On the first page select the **Allow** scenario, and then select *Continue*.
1. Remove the string1 prefilled value (123), leave the claims empty and select *Continue*. The next page will show you that all of the claims **exist**. Since we allow null values, Azure AD B2C creates the claims with empty string. As for the string1, although it was set with a prefilled value, Azure AD B2C replaces the prefilled value with null. 
1. Run the [B2C_1A_TP_SA_metadata_AllowGenerationOfClaimsWithNullValues](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_SA_metadata_AllowGenerationOfClaimsWithNullValues/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) policy again. This time, select the **Don't allow** scenario.
1. Remove the string1 prefilled value (123), leave the claims empty and select *Continue*. The next page will show you that string2 and string3 **don't exist**. Since we don't allow null values, Azure AD B2C won't set the claims (they don't exists in the claims bag). As for the string1, since you deleted the prefilled value (123) and the *AllowGenerationOfClaimsWithNullValues* metadata is set to false, the prefilled value is still in used, and thus the string1 **exists**.

Notes:

- To allow users to remove values. For example, allow them to change the city claim to empty string, always set the *AllowGenerationOfClaimsWithNullValues* metadata to *true*.
- The JWT token return by this policy doesn't include claims with empty values. If the string1 or string2 are empty or null, they won't be included in the ID token.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_SA_metadata_AllowGenerationOfClaimsWithNullValues/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../../media/policy.png) [Policy](TP_SA_metadata_AllowGenerationOfClaimsWithNullValues.xml) &nbsp; ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile#metadata)

## Enable remember me (KMSI)

For a sign-in page (type of [unifiedssd and unifiedssd content definitions](https://docs.microsoft.com/azure/active-directory-b2c/contentdefinitions#datauri)), the [setting.enableRememberMe](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile#metadata) metadata controls whether the [keep me sign-in (KMSI)](https://docs.microsoft.com/azure/active-directory-b2c/session-behavior?pivots=b2c-custom-policy#enable-keep-me-signed-in-kmsi) is enabled or not.

To test the user experience, select one of the options (True, or False), then select continue. In the next page, if you selected *True*, the keep me sign-in will appear on the screen.

The unit test defines the following components:

- *WelcomeTechnicalProfile* - welcome page where you can choose between the enable KMSI options.
- *BlockPageTechnicalProfile* - sign-up block message (we don't want to allow users to sign-in in this unit test)
- **ExperimentalTechnicalProfile-[option]** is the unit test. This technical profile includes the *SelfAsserted-LocalAccountSignin-Email* from the base policy of the starter pack, and configures the *setting.showSignupLink* metadata.
- The user journey checks the value of the *scenario* claim (selected on the first page), and directs to the corresponding *ExperimentalTechnicalProfile-[option]* unit test. Note, extra orchestration steps are required since this sample uses the *CombinedSignInAndSignUp* type of orchestration steps that must be followed by *ClaimsExchange* type of orchestration step.
- The relaying party's **SingleSignOn** element is set to `KeepAliveInDays="30"`.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_SA_metadata_setting_enableRememberMe/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../../media/policy.png) [Policy](TP_SA_metadata_setting_enableRememberMe.xml) &nbsp; ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile#metadata)

## Forgot password link location

Demonstrates the forgot password link [setting.forgotPasswordLinkLocation](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile#metadata) metadata options. The unit test defines the following components:

- *WelcomeTechnicalProfile* - welcome page where you can choose between the options.
- *BlockPageTechnicalProfile* - sign-up block message (we don't want to allow users to sign-in in this unit test)
- **ExperimentalTechnicalProfile-[option]** is the unit test. This technical profile includes the *SelfAsserted-LocalAccountSignin-Email* from the base policy of the starter pack, and configures the *setting.forgotPasswordLinkLocation* metadata.
- The user journey checks the value of the *scenario* claim (selected on the first page), and directs to the corresponding *ExperimentalTechnicalProfile-[option]* unit test. Note, extra orchestration steps are required since this sample uses the *CombinedSignInAndSignUp* type of orchestration steps that must be followed by *ClaimsExchange* type of orchestration step.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_SA_metadata_setting_forgotPasswordLinkLocation/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../../media/policy.png) [Policy](TP_SA_metadata_setting_forgotPasswordLinkLocation.xml) &nbsp; ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile#metadata)

## Input verification delay time in milliseconds

Demonstrates the effect of [setting.inputVerificationDelayTimeInMilliseconds](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile#metadata) metadata on the user experience. To test the user experience, select on of the options (default, 100, or 6000), then select continue. In the next page, provide an incorrect password, such as 1111. Compare the time Azure AD B2C renders the error message.

 The unit test defines the following components:

- *WelcomeTechnicalProfile* - welcome page where you can choose between the input verification delay time in milliseconds options.
- **ExperimentalTechnicalProfile-[option]** is the unit test. In this technical profile you can find the *setting.inputVerificationDelayTimeInMilliseconds* metadata.
- The user journey checks the value of the *scenario* claim (selected on the first page), and directs you to the corresponding *ExperimentalTechnicalProfile-[option]* unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_SA_metadata_setting_inputVerificationDelayTimeInMilliseconds/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../../media/policy.png) [Policy](TP_SA_metadata_setting_inputVerificationDelayTimeInMilliseconds.xml) &nbsp; ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile#metadata)

## Operating mode

For a sign-in page (type of [unifiedssd content definition](https://docs.microsoft.com/azure/active-directory-b2c/contentdefinitions#datauri)), the [setting.operatingMode](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile#metadata) metadata controls the appearance and behavior of the username field, such as input validation and error messages.

To test the user experience, select one of the options (Email, or Username), then select continue. In the next page, compare the text appears in the username field. If you choose Email, user must type a valid username, otherwise and error will be thrown.

The unit test defines the following components:

- *WelcomeTechnicalProfile* - welcome page where you can choose between the sign-in (operation mode) options.
- *BlockPageTechnicalProfile* - sign-up block message (we don't want to allow users to sign-in in this unit test)
- **ExperimentalTechnicalProfile-[option]** is the unit test. This technical profile includes the *SelfAsserted-LocalAccountSignin-Email* from the base policy of the starter pack, and configures the *setting.operatingMode* metadata.
- The user journey checks the value of the *scenario* claim (selected on the first page), and directs to the corresponding *ExperimentalTechnicalProfile-[option]* unit test. Note, extra orchestration steps are required since this sample uses the *CombinedSignInAndSignUp* type of orchestration steps that must be followed by *ClaimsExchange* type of orchestration step.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_SA_metadata_setting_operatingMode/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../../media/policy.png) [Policy](TP_SA_metadata_setting_operatingMode.xml) &nbsp; ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile#metadata)

## Retry limit

Demonstrates how to control the number of times a user can try to provide the data that is checked against a [validation technical profile](https://docs.microsoft.com/azure/active-directory-b2c/validation-technical-profile). This example asks the user to provide two texts and compares them. If they aren't identical, an error message will be return. User can retry until reach the value of the [setting.retryLimit](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile#metadata) metadata.

To test the user experience, select one of the retry limit options (default, 2, or 15), then select continue. In the next page, provide a nonidentical value, such as ABC and 123. Select *Continue* button. When you get an error message, try again and again, until you reach the limitation and will be redirect to the <https://jwt.ms> app with error message.

 The unit test defines the following components:

- *WelcomeTechnicalProfile* - welcome page where you can choose between the retry limit options.
- **ExperimentalTechnicalProfile-[option]** is the unit test. In this technical profile you can find the *setting.retryLimit* metadata.
- The user journey checks the value of the *scenario* claim (selected on the first page), and directs you to the corresponding *ExperimentalTechnicalProfile-[option]* unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_SA_metadata_setting_retryLimit/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../../media/policy.png) [Policy](TP_SA_metadata_setting_retryLimit.xml) &nbsp; ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile#metadata)

## Show the cancel button

For a [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile Azure AD B2C renders the *Continue* and *Cancel* buttons. This sample demonstrates how to show or hide the cancel button using the [setting.showCancelButton](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile#metadata) metadata.

To test this user experience, select one of show the cancel button options (default, True, or False) and select continue. In the next page, if you selected *False*, the cancel button won't be rendered.

 The unit test defines the following components:

- *WelcomeTechnicalProfile* - welcome page where you can choose between the show cancel button options.
- **ExperimentalTechnicalProfile-[option]** is the unit test. In this technical profile, you can find the *setting.showCancelButton* metadata.
- The user journey checks the value of the *scenario* claim (selected on the first page), and directs you to the corresponding *ExperimentalTechnicalProfile-[option]* unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_SA_metadata_setting_showCancelButton/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../../media/policy.png) [Policy](TP_SA_metadata_setting_showCancelButton.xml) &nbsp; ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile#metadata)

## Show the continue button

For a [self-asserted](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile) technical profile, Azure AD B2C renders the *Continue* and *Cancel* buttons. This sample demonstrates how to show or hide the continue button using the [setting.showContinueButton](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile#metadata) metadata.

To test this user experience, select one of show the continue button options (default, True, or False) and select continue. In the next page, if you selected *False*, the continue button won't be rendered.

 The unit test defines the following components:

- *WelcomeTechnicalProfile* - welcome page where you can choose between the show continue button options.
- **ExperimentalTechnicalProfile-[option]** is the unit test. In this technical profile, you can find the *setting.showContinueButton* metadata.
- The user journey checks the value of the *scenario* claim (selected on the first page), and directs you to the corresponding *ExperimentalTechnicalProfile-[option]* unit test.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_SA_metadata_setting_showContinueButton/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../../media/policy.png) [Policy](TP_SA_metadata_setting_showContinueButton.xml) &nbsp; ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile#metadata)

## Show sign-up link

For a sign-in page (type of [unifiedssd and unifiedssd content definitions](https://docs.microsoft.com/azure/active-directory-b2c/contentdefinitions#datauri)), the [setting.showSignupLink](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile#metadata) metadata controls whether the sign-up link is rendered on the unified sign-up or sign-in page.

To test the user experience, select one of the options (True, or False), then select continue. In the next page, if you selected *False*, the sign-up link won't appear on the screen.

The unit test defines the following components:

- *WelcomeTechnicalProfile* - welcome page where you can choose between the show sign-up link options.
- *BlockPageTechnicalProfile* - sign-up block message (we don't want to allow users to sign-in in this unit test)
- **ExperimentalTechnicalProfile-[option]** is the unit test. This technical profile includes the *SelfAsserted-LocalAccountSignin-Email* from the base policy of the starter pack, and configures the *setting.showSignupLink* metadata.
- The user journey checks the value of the *scenario* claim (selected on the first page), and directs to the corresponding *ExperimentalTechnicalProfile-[option]* unit test. Note, extra orchestration steps are required since this sample uses the *CombinedSignInAndSignUp* type of orchestration steps that must be followed by *ClaimsExchange* type of orchestration step.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_SA_metadata_setting_showSignupLink/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../../media/policy.png) [Policy](TP_SA_metadata_setting_showSignupLink.xml) &nbsp; ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/self-asserted-technical-profile#metadata)

## Pass the login_hint to the sign-up page

During a sign-in user journey, a relying party application may target a specific user. When targeting a user, an application can specify, in the authorization request, the `login_hint` query parameter with the user sign-in name. Azure AD B2C automatically populates the sign-in name, while the user only needs to provide the password. For more information, check out the [Set up direct sign-in using Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/direct-signin?pivots=b2c-custom-policy) article.

This unit test shows how to pass the *login_hint* query string parameter to the sign-**up** page. The type of the *email* claim must be set to *readonly* and the *LocalAccountSignUpWithLogonEmail* technical profile sets the input claim default value to the *{OIDC:LoginHint}* [claim resolver](https://docs.microsoft.com/azure/active-directory-b2c/claim-resolver-overview).

To test this user experience, the [authorization request](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_SA_InputClaims_PrepopulateSignInName/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login&login_hint=emily@contoso.com) contains the `login_hint=emily@contoso.com` parameter. When you [run](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_SA_InputClaims_PrepopulateSignInName/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login&login_hint=emily@contoso.com) the policy, the email *emily@contoso.com* will be rendered on the sign-up or sign-in page. Select *Sign-up now* and you will see the same email on the top of the sign-up page. The email is read only, complete the email verification process.

![live demo](../../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_TP_SA_InputClaims_PrepopulateSignInName/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login&login_hint=emily@contoso.com) &nbsp; ![Quick deploy](../../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../../media/policy.png) [Policy](TP_SA_InputClaims_PrepopulateSignInName.xml) &nbsp; ![documentation](../../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/direct-signin?pivots=b2c-custom-policy)