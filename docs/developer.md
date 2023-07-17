# Mobile app development guide

Use this guide when building a mobile app for the Province of B.C. to make sure you're following our best practices.


## Digital Code of Practice

All apps developed for the Province of B.C. must adhere to the [Digital Code of Practice](https://digital.gov.bc.ca/policies-standards/dcop/) (DCoP). The DCoP emphasizes a user focus, accessibility, security and efficiency. Adhering to it will help you achieve digital excellence and improve the citizen experience.

## Code location

[Work in the open](https://digital.gov.bc.ca/policies-standards/dcop/open/) is one of the principles of the DCoP. To achieve this with your project, we encourage teams to host their app's code in the [bcgov GitHub organization](https://github.com/bcgov). Learn how to do this in the [Working in the BCGov GitHub organization](https://docs.developer.gov.bc.ca/start-working-in-bcgov-github-organization/) documentation.


We recognize there are situations where it may not be possible to share your code publicly and other code hosting options are available. The [BC Government organizations in GitHub](https://docs.developer.gov.bc.ca/bc-government-organizations-in-github/) documentation provides information on alternative locations.

Still not sure what option is best for your project? [Contact the Developer Experience team] (contact.md).

## App framework
Choose a hybrid framework over building a native app. Hybrid frameworks enable code reuse across platforms, saving time and effort. Using a single codebase that deploys to both iOS and Android eliminates the need to build separate apps. This reduces development time and accelerates time-to-market. You are free to choose the framework that is best suited to your project.

If you must use native code, then we recommend Swift for iOS and Kotlin for Android. Are you supporting a legacy application that uses an older language (e.g., Objective-C)? If so, you may be able to write new features in a more modern language.


## Design considerations 
[Design with people and embed inclusion](https://digital.gov.bc.ca/policies-standards/dcop/design/) is one of the principles of the [Digital Code of Practice](https://digital.gov.bc.ca/policies-standards/dcop/). Design your app to be inclusive and accessible to the people who use it.

When possible, you should use the [Design System](https://developer.gov.bc.ca/Design-System/About-the-Design-System). The Design System guidance on colour pallets and fonts is applicable to mobile apps.

Note: The Province of B.C. uses the [BC Sans](https://www2.gov.bc.ca/gov/content/governments/services-for-government/policies-procedures/bc-visual-identity/bc-sans) font for digital service delivery. Don't use fonts that need a license like Myriad Pro. 


## Build system 
We recommend you use a CI/CD pipeline to build your app. Have the pipeline code sign your app. The [Apple Code Signing](apple_app_signing.md) and [Google Code Signing](google_app_signing.md) pages give guidance on how to set it up.

See the [bc-wallet-mobile](https://github.com/bcgov/bc-wallet-mobile/blob/main/.github/workflows/main.yaml) project as an example of a project that uses GitHub Actions as its CI/CD.

## Code review 
[SonarCloud](https://sonarcloud.io/projects) is an automatic code review tool. Use it to detect bugs, vulnerabilities and code smells in your code. Review the [Steps to start using SonarCloud](https://github.com/BCDevOps/sonarqube#sonarcloud) documentation to enable it in your project.

When possible, have another developer on your team review your code. 

Are you the only developer on your team? Ask in the [#devops-mobile-development](https://chat.developer.gov.bc.ca/channel/devops-mobile-development) RocketChat channel for another developer to review your code.

## Testing your mobile application 
It's preferred for developers to write automated tests for code. 

There are many benefits to using automated tests, but in our Enterprise environment the quick win is maintainability. You can refactor your code and be confident you're not breaking anything. That also means that if needed, a new developer can take over your application with a safety net in place. 

## Linters
We recommend you use a linter in your project. A linter analyzes source code and identify potential issues, errors, or violations of coding standards. Check if your department has an existing linter you can use. If not, GitHub maintains a [collection of linters](https://github.com/collections/clean-code-linters) for you to explore.


## Accessing the developer accounts
Your Product Owner will invite you to the Apple and Google developer programs. You'll have access to the apps you are developing in both App Store Connect and Play Console.

### Apple Developer Program

You'll be granted the [developer role](app_management.md#developer-role) for your app. This will give you access to the development certificate, identifier and profiles. Use Xcode's "automatically manage signing" feature for debug builds. 

### Google Play Program

You'll be assigned to the [release group](app_management.md#release-permission-group) for your app. 


## Community

Visit the [contact us](contact.md) page for details on how to connect with the community.