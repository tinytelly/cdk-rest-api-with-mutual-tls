# cdk rest api with mutual tls
AWS CDK Implementation of a [REST Api with MTLS](https://docs.aws.amazon.com/apigateway/latest/developerguide/rest-api-mutual-tls.html)

### Steps used to create this repo from scratch.
1) create a public repo in github
2) create a [devcontainer in github](https://docs.github.com/en/codespaces/setting-up-your-project-for-codespaces/adding-a-dev-container-configuration/introduction-to-dev-containers#using-a-predefined-dev-container-configuration) to do your work on that contains the features of pnpm, turbo, aws cdk and projen, once created [rebuild the codespace container](https://docs.github.com/en/codespaces/setting-up-your-project-for-codespaces/adding-a-dev-container-configuration/introduction-to-dev-containers#applying-configuration-changes-to-a-codespace)

### TODO
1) use projen to create stack for API
2) create github workflow to build on commits.
