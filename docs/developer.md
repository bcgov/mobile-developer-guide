# Mobile app development guide

Use this guide when building a mobile app for the Province of B.C. to make sure you're following our best practices.


## Digital Code of Practice

All mobile apps developed for the Province of B.C. must adhere to the [Digital Code of Practice](https://digital.gov.bc.ca/policies-standards/dcop/) (DCoP). The DCoP emphasizes a user focus, accessibility, security and efficiency. Adhering to it will help you achieve digital excellence and improve the citizen experience. 


### Work in the open

To achieve the [work in the open](https://digital.gov.bc.ca/policies-standards/dcop/open/) practice, host your mobile app's code in the [bcgov GitHub organization](https://github.com/bcgov). Learn how to do this in the [Working in the BCGov GitHub organization](https://docs.developer.gov.bc.ca/start-working-in-bcgov-github-organization/) documentation.


We recognize there are situations where it may not be possible to share your code publicly and other code hosting options are available. The [BC Government organizations in GitHub](https://docs.developer.gov.bc.ca/bc-government-organizations-in-github/) documentation provides information on alternative locations.

Still not sure what option is best for your project? [Contact the Developer Experience team](contact.md).

### Take an ecosystem approach

[Take an ecosystem approach](https://digital.gov.bc.ca/policies-standards/dcop/ecosystem/) when building your mobile app. Research whether an existing project provides features like your new mobile app. You may be able to reuse existing components. [Connect with the community](contact.md) to learn what other mobile apps are doing.


#### Mobile app frameworks
Choose a hybrid framework over building a native app. Hybrid frameworks enable code reuse across platforms, saving time and effort. Using a single codebase that deploys to both iOS and Android eliminates the need to build separate apps. This reduces development time and accelerates time-to-market. You're free to choose the framework that is best suited to your project.

If you must use native code, then we recommend Swift for iOS and Kotlin for Android. Are you supporting a legacy application that uses an older language (such as Objective-C)? If so, you may be able to write new features in a more modern language.

### Design with people and embed inclusion
 The [design with people and embed inclusion](https://digital.gov.bc.ca/policies-standards/dcop/design/) practice describes the techniques you can use so your mobile app meets the needs of the people who use it.

When possible, you should use the [Design System](https://developer.gov.bc.ca/Design-System/About-the-Design-System). The Design System guidance on colour palettes and fonts is applicable to mobile apps.

Note: The Province of B.C. uses the [BC Sans](https://www2.gov.bc.ca/gov/content/governments/services-for-government/policies-procedures/bc-visual-identity/bc-sans) font for digital service delivery. Don't use fonts that need a license like Myriad Pro. 

Both Android and Apple provide design guidance for their platforms. Use their documentation to ensure your app meets their guidelines:

* [Apple's Human Interface Guidelines documentation](https://developer.apple.com/design/human-interface-guidelines/)
* [Design for Android documentation](https://developer.android.com/design/ui)

### Continuously learn and improve
Use automated build and testing tools to achieve the [continuously learn and improve](https://digital.gov.bc.ca/policies-standards/dcop/learn/) practice. Automated build systems allow for consistent and repeatable builds. This eliminates the reliance on a developer's computer to publish the app to the app stores. Code scanning tools and unit tests make it easier for developers to maintain code.

#### Build system 
We recommend you use a CI/CD pipeline to build your app. Have the pipeline code sign your app. The [Apple Code Signing](apple_app_signing.md) and [Google Code Signing](google_app_signing.md) pages give guidance on how to set it up.

The [bc-wallet-mobile](https://github.com/bcgov/bc-wallet-mobile/blob/main/.github/workflows/main.yaml) project is a good example of a project that uses GitHub Actions as its CI/CD.

#### Code review 
[SonarCloud](https://sonarcloud.io/projects) is an automatic code review tool. Use it to detect bugs, vulnerabilities and code smells in your code. Review the [Steps to start using SonarCloud](https://github.com/BCDevOps/sonarqube#sonarcloud) documentation to enable it in your project.

When possible, have another developer on your team review your code. 

Are you the only developer on your team? Ask in the [#devops-mobile-development](https://chat.developer.gov.bc.ca/channel/devops-mobile-development) RocketChat channel for another developer to review your code.

#### Linters
We recommend you use a linter in your project. A linter analyzes source code and identify potential issues, errors or violations of coding standards. If you don't have a linter, ask in the [#devops-mobile-development](https://chat.developer.gov.bc.ca/channel/devops-mobile-development). GitHub also maintains a [collection of linters](https://github.com/collections/clean-code-linters) for you to explore.


#### Testing your mobile application 

##### Unit testing
Developers should write automated unit tests for their code. There are many benefits, including:

* Early bug detection
* Improved code quality
* Regression prevention
* Facilitates refactoring
* Supports collaboration
* Continuous integration and deployment 

##### Beta testing
Beta testing is when a pre-release version of the mobile app is made available to a limited group of users. The purpose is to gather feedback and make improvements before releasing it to the public.

Both Apple and Google provide beta testing mechanisms. Use their documentation for guidance on how to set up a beta test. 

* [Apple Test Flight documentation ](https://testflight.apple.com)
* [Google open, closed, or internal test documentation](https://support.google.com/googleplay/android-developer/answer/9845334?_ga=2.169255906.2142663607.1689618205-739144597.1687798630&_gac=1.113072630.1689622677.Cj0KCQjwzdOlBhCNARIsAPMwjbyTBfVF_kq-S5EIOdSu5Nk7skdlUlcE1ZScROR1wINBW54EBuk1k5AaAsxzEALw_wcB)

### Take care of information and data

Be familiar with Android and iOS security practices to [take care of information and data](https://digital.gov.bc.ca/policies-standards/dcop/data/). [Hybrid apps](developer.md#mobile-app-frameworks) should consult the framework's documentation for additional security considerations.

* [Apple security documentation](https://developer.apple.com/documentation/security)
* [Android security documentation](https://developer.android.com/training/articles/security-tips)



## Accessing the developer accounts
Your Product Owner will invite you to the Apple and Google developer programs. You'll have access to the apps you're developing in both App Store Connect and Play Console.

### Apple Developer Program

You'll be granted the [developer role](app_management.md#developer-role) for your app. This will give you access to the development certificate, identifier and profiles. Use Xcode's "automatically manage signing" feature for debug builds. 

### Google Play Program

You'll be assigned to the [release group](app_management.md#release-permission-group) for your app. 


## Community

Visit the [contact us](contact.md) page for details on how to connect with the community.
