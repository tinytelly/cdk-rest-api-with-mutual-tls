# cdk rest api with mutual tls
AWS CDK Implementation of a [REST Api with MTLS](https://docs.aws.amazon.com/apigateway/latest/developerguide/rest-api-mutual-tls.html)

### Steps used to create this repo from scratch (for education purposes)
1) create a public repo in github

2) create a [devcontainer in github](https://docs.github.com/en/codespaces/setting-up-your-project-for-codespaces/adding-a-dev-container-configuration/introduction-to-dev-containers#using-a-predefined-dev-container-configuration) which creates a github codespace to perform your work on.  The codespace will support [pnpm](https://pnpm.io/), [turbo](https://turbo.build/), [aws cdk](https://aws.amazon.com/cdk/) and [projen](https://github.com/projen/projen). Once created [rebuild the codespace container](https://docs.github.com/en/codespaces/setting-up-your-project-for-codespaces/adding-a-dev-container-configuration/introduction-to-dev-containers#applying-configuration-changes-to-a-codespace)

3) create a aws cdk stack using projen
```bash
    cd ../
    mkdir api-stack
    cd api-stack/
    npx projen new awscdk-app-ts --github=false
    ## add to .projenrc.ts these lines
        import { javascript, awscdk } from 'projen';
        ...
        packageManager: javascript.NodePackageManager.PNPM,
        ...
        project.package.setScript('build', 'npx projen && npx projen build');
        
    npx projen
    rm yarn.lock
    rm -Rf node_modules/
    rm -Rf ./git
    rm pnpm-lock.yaml
    cd ..
    mv api-stack cdk-rest-api-with-mutual-tls
```

4) [add turbo](https://turbo.build/repo/docs/getting-started/add-to-project) to the stack via [api-stack/turbo.json](api-stack/turbo.json)

5) run a build 
```bash
    cd api-stack
    turbo build
```

### TODO
1) create github workflow to build on commits.
