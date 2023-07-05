# Google Signing


To learn about code signing, please review Google's [Sign your app](https://developer.android.com/studio/publish/app-signing) documentation.

This guide describes how an app team should work with Google keys. You must use the Province of BC's Google Play developer account to distribute your app.

React Native apps need extra setup to use the keys. Please see the [React Native Signing Guide](google_react_native_signing.md) for more details.

## Keys
Google Play uses two keys:

- upload key
- app signing key 

Please refer to Google's [Play App Signing](https://developer.android.com/studio/publish/app-signing#app-signing-google-play) documentation for an in-depth review of the two keys.

### Upload Key

The upload key signs your app for upload to the Google Play Store. The team's app release manager should [create the upload key](https://developer.android.com/studio/publish/app-signing#sign-apk). 

If your app's code is in the [bcgov GitHub organization](https://github.com/bcgov), then please use a [GitHub Action](https://docs.github.com/en/actions) to build and sign your app with the upload key. Refer to Google's [Sign your app from command line](https://developer.android.com/build/building-cmdline#sign_cmdline) documentation for instructions on how to do this. Store the key ([encoded as base64](https://docs.github.com/en/actions/security-guides/encrypted-secrets#storing-base64-binary-blobs-as-secrets)), its alias and the password as a [secret](https://docs.github.com/en/actions/security-guides/encrypted-secrets) in your app's repo. 


See the [bc-wallet-mobile](https://github.com/bcgov/bc-wallet-mobile/blob/main/.github/workflows/main.yaml) project for an example of a project using GitHub Actions.

If you are using a different git host, then please see its documentation on how to create a CI/CD pipeline. Use its secret feature to store the key and password securely.

If you do not use a CI/CD pipeline, then store the key and password somewhere securely.  However, we encourage teams to use a CI/CD pipeline. It provides repeatable builds and safely stores the credentials.

### App Signing Key

Please use the [Play App Signing](https://developer.android.com/studio/publish/app-signing#app-signing-google-play) service to sign your app. If you do not use this service and you lose your app’s signing key, you lose the ability to update your app. Google's [Using Play App Signing](https://developer.android.com/studio/publish/app-signing#enroll) documentation describes how to setup it up for your app.

