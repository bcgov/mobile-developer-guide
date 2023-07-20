# Publish your app

Learn how to setup your CI/CD pipeline to upload your app to App Store Connect and Play Console.

## Distribution methods

Review [Mobile App Distribution Methods](distribution_methods.md) for an overview of app distribution.

## CI/CD

Let the [Developer Experience](contact.md) team know if your app will use a CI/CD pipeline to upload your app. We'll give you access to the necessary API keys.

 The [bc-wallet-mobile](https://github.com/bcgov/bc-wallet-mobile/) project is a good example of an app using GitHub Actions to upload to both app stores.

## App Store Connect

Let us know if you plan to:

1. Upload the build
or
1. Upload the build and ship it to TestFlight

The upload path you pick determines which API Key to use. 

The bcgov GitHub organization stores the [App Store Connect API](https://developer.apple.com/documentation/appstoreconnectapi) keys as secrets. Send the [Developer Experience](contact.md) team your repo name and we'll give it access to those secrets.

You can use [codemagic-cli-tools](https://docs.codemagic.io/knowledge-codemagic/codemagic-cli-tools/) to upload your app. 

## Play Console
Contact the [Developer Experience](contact.md) team to setup your API Key to the Play Console.

You can use the `npx @bcgov/gpublish` package to upload your app. 