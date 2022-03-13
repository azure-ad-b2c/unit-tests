# Predicates unit tests

This folder contains unit tests for Azure AD B2C predicates. For more information, check out the [Predicates and PredicateValidations](https://docs.microsoft.com/azure/active-directory-b2c/predicates) article.

## IncludesCharacters method 

The *IncludesCharacters* method checks whether a date claim value is between a range of minimum and maximum parameters specified. To test the experience of the predicate, follow these steps:

- [Run](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Predicate_IncludesCharacters/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) the *B2C_1A_Predicate_IncludesCharacters* policy.
- In the textbox type `123`, or `abc`  and select continue. You should get an error message. The string must contain a combination of a lower case, upper case, a number and a symbol.
- Type a string that contains all the required characters, such as `Passw0rd!` and select continue. This time you should not get any error message. 

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Predicate_IncludesCharacters/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../media/policy.png) [Policy](Predicate_IsDateRange.xml) &nbsp;  ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/claimsschema#userinputtype)

## IsDateRange method 

The *IsDateRange* method checks whether a string claim value contains a character set. To test the experience of the predicate, follow these steps:

- [Run](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Predicate_IsDateRange/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) the *B2C_1A_Predicate_IsDateRange* policy.
- Select a date that is greater than today, and select continue. You should get an error message.
- Select a valid date and select continue. This time you will not get any error.  

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Predicate_IsDateRange/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../media/policy.png) [Policy](Predicate_IncludesCharacters.xml) &nbsp;  ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/claimsschema#userinputtype)

## IsLengthRange method 

The *IncludesCharacters* method checks whether the length of a string claim value is within the range of minimum and maximum parameters specified. To test the experience of the predicate, follow these steps:

- [Run](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Predicate_IsLengthRange/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) the *B2C_1A_Predicate_IsLengthRange* policy.
- In the textbox type a short value, such as `abc` and select continue. You should get an error message. 
- Add more characters to meet the predicate requirement and select continue. This time you should not get any error message. 

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Predicate_IsLengthRange/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../media/policy.png) [Policy](Predicate_IsLengthRange.xml) &nbsp;  ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/claimsschema#userinputtype)


## MatchesRegex method 

The *MatchesRegex* method whether a string claim value matches a regular expression. To test the experience of the predicate, follow these steps:

- [Run](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Predicate_MatchesRegex/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) the *B2C_1A_Predicate_MatchesRegex* policy.
- In the textbox type one or more spaces ` `, or `  ` and select continue. You should get an error message. 
- Remote the spaces and select continue. This time you should not get any error message. 

![live demo](../media/demo.png) [Live demo](https://b2clivedemo.b2clogin.com/b2clivedemo.onmicrosoft.com/B2C_1A_Predicate_MatchesRegex/oauth2/v2.0/authorize?client_id=cfaf887b-a9db-4b44-ac47-5efff4e2902c&nonce=defaultNonce&redirect_uri=https%3A%2F%2Fjwt.ms&scope=openid&response_type=id_token&prompt=login) &nbsp; ![Quick deploy](../media/deploy.png) [Quick deploy](https://b2ciefsetupapp.azurewebsites.net/)  &nbsp; ![policy](../media/policy.png) [Policy](Predicate_MatchesRegex.xml) &nbsp;  ![documentation](../media/doc.png) [Documentation](https://docs.microsoft.com/azure/active-directory-b2c/claimsschema#userinputtype)