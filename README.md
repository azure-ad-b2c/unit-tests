# Azure Active Directory B2C features unit tests

In this repo, you will find samples for several of Azure AD B2C custom policy features.

## Getting started

- See our [Custom Policy overview](https://docs.microsoft.com/en-us/azure/active-directory-b2c/custom-policy-overview).

- See our [Azure AD B2C Wiki articles](https://azure-ad-b2c.github.io/azureadb2ccommunity.io/docs/custom-policy-concepts/) to help walkthrough the custom policy components.

- See our [Custom Policy Schema reference](https://docs.microsoft.com/en-us/azure/active-directory-b2c/trustframeworkpolicy).

## Prerequisites
- You will require to [create an Azure AD B2C directory](https://docs.microsoft.com/en-us/azure/active-directory-b2c/tutorial-create-tenant).

- You can automate the prerequisites (where applicable) by using our using automated tool called [Deploy AAD B2C Custom Policies](https://aka.ms/iefsetup) if you already have an Azure AD B2C tenant.

## Sample scenarios

Samples are available for the following categories:

- [Claims](claims)
- [Claims resolvers](claims-resolver)
- Claims transformations
  - [Boolean](claims-transformation/boolean/)
  - [Date](claims-transformation/date/)
  - [General](claims-transformation/general/)
  - [Integer](claims-transformation/integer/)
  - [JSON](claims-transformation/json/)
  - [Phone number](claims-transformation/phoneNumber/)
  - [Social accounts](claims-transformation/social/)
  - [String](claims-transformation/string/)
  - [String collection](claims-transformation/stringCollection/)
- Technical profiles:
  - [Login-NonInteractive](technical-profiles/login-NonInteractive/)
  - [OAuth2 error](technical-profiles/oauth2-error/)
  - [Self-asserted](technical-profiles/self-asserted/)
- [Identity providers](Identity-providers)
- [Session and logout](./session)

## Community Help and Support

Use [Stack Overflow](https://stackoverflow.com/questions/tagged/azure-ad-b2c) to get support from the community. Ask your questions on Stack Overflow first and browse existing issues to see if someone has asked your question before. Make sure that your questions or comments are tagged with [azure-ad-b2c].
If you find a bug in the sample, please raise the issue on [GitHub Issues](https://github.com/azure-ad-b2c/samples/issues).
To provide product feedback, visit the Azure Active Directory B2C [Feedback page](https://feedback.azure.com/d365community/forum/22920db1-ad25-ec11-b6e6-000d3a4f0789#).
