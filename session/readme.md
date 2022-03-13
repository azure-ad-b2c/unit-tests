# Session 

This folder contains unit tests for Azure AD B2C session settings. For more information, check out the [Configure session behavior in Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/session-behavior?pivots=b2c-custom-policy) article.

## Enable Keep me signed in (KMSI)

You can enable the KMSI feature for users of your web and native applications who have local accounts in your Azure AD B2C directory. When you enable the feature, users can opt to stay signed in so the session remains active after they close the browser.

To test the experience of the KMSI, follow these steps:

1. If you don't have an account, [create a local account](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_signup_signin/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https://jwt.ms&scope=openid&response_type=id_token&prompt=login) with your email address.
1. Sign-**in** with the [B2C_1A_Session_KeepAliveInDays](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Session_KeepAliveInDays/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token) policy. Note, the link to the *B2C_1A_Session_KeepAliveInDays* policy starts a new session (using the `prompt=login` query string parameter). Select KMSI and complete the sign-in flow.
1. Close and reopen the browser sign-**in** again with the [B2C_1A_Session_KeepAliveInDays](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Session_KeepAliveInDays/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) policy. Note, the link to the *B2C_1A_Session_KeepAliveInDays* policy doesn't start a new session. This time you will not be prompted to reenter your credentials. 

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Session_KeepAliveInDays/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../media/policy.png) [Policy](Session_KeepAliveInDays.xml) &nbsp; ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/session-behavior?pivots=b2c-custom-policy#enable-keep-me-signed-in-kmsi)

## Enforce ID token hint on logout

After logout, the user is redirected to the URI specified in the *post_logout_redirect_uri* parameter, regardless of the reply URLs that have been specified for the application. However, if a valid id_token_hint is passed and the Require ID Token in logout requests is turned on, Azure AD B2C verifies that the value of *post_logout_redirect_uri* matches one of the application's configured redirect URIs before performing the redirect. If no matching reply URL was configured for the application, an error message is displayed and the user is not redirected.

To test the experience of the enforce ID token hint on logout feature, follow these steps:

1. Sign-up or sign-in with the [B2C_1A_Session_EnforceIdTokenHintOnLogout](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Session_KeepAliveInDays/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) policy. Copy the ID token from the <https://jwt.ms> app, you will need it later.
1. Try to logout with the [B2C_1A_Session_EnforceIdTokenHintOnLogout](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Session_KeepAliveInDays/oauth2/v2.0/logout?post_logout_redirect_uri=https%3A%2F%2Fjwt.ms%2F) policy without providing the ID token hint. You should see error message similar to the following: *AADB2C90272: The id_token_hint parameter has not been specified in the request. Please provide token and try again.*.
1. Add the ID token hint to the following URL:

    ```http
    https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Session_KeepAliveInDays/oauth2/v2.0/logout?post_logout_redirect_uri=https%3A%2F%2Fjwt.ms%2F&id_token_hint=
    ```

    For example:
    
    ```http
    https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Session_KeepAliveInDays/oauth2/v2.0/logout?post_logout_redirect_uri=https%3A%2F%2Fjwt.ms%2F&id_token_hint=eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIs...
    ```

1. Copy and run the URL into your browser. This time you should be logout without any problem.

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Session_EnforceIdTokenHintOnLogout/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/) &nbsp; ![policy](../media/policy.png) [Policy](Session_EnforceIdTokenHintOnLogout.xml) &nbsp; ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/session-behavior?pivots=b2c-custom-policy#secure-your-logout-redirect)