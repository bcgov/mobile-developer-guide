# Publish your app

## Distribution methods

See the [Mobile App Distribution Methods](distribution_methods.md)  page for an overview of app distribution.

## CI/CD

Let the [Developer Experience](contact.md) team know your app will use a CI/CD pipeline to upload your app. We will give you access to the necessary API keys.

See the [bc-wallet-mobile](https://github.com/bcgov/bc-wallet-mobile/) project as an example of an app using GitHub Actions to upload to both app stores.

## App Store Connect

Let us know if you plan to:

1. upload the build, or,
1. upload the build and ship it to TestFlight

The answer to the above will determine which API Key to use.

The bcgov GitHub organization stores the [App Store Connect API](https://developer.apple.com/documentation/appstoreconnectapi) keys as secrets. Send the [Developer Experience](contact.md) team your repo name and we will give it access to those secrets.

You can use [codemagic-cli-tools](https://docs.codemagic.io/knowledge-codemagic/codemagic-cli-tools/) to upload your app. See the [bc-wallet-mobile](https://github.com/bcgov/bc-wallet-mobile/) project as an example.

## Play Console
See the [Developer Experience](contact.md) team to setup your API Key to the Play Console.

You can use the `npx @bcgov/gpublish` package to upload your app. See the [bc-wallet-mobile](https://github.com/bcgov/bc-wallet-mobile/) project as an example.