# Google app signing

This guide describes how an app team should work with Google keys. You must use the Province of BC's Google Play developer account to distribute your app.

To learn about code signing, review Google's [Sign your app](https://developer.android.com/studio/publish/app-signing) documentation.


React Native apps need extra setup to use the keys. Review the [React Native Signing Guide](google_react_native_signing.md) for more details.

## Keys
Google Play uses 2 keys:

- Upload key
- App signing key 

Use Google's [Play App Signing](https://developer.android.com/studio/publish/app-signing#app-signing-google-play) documentation for an in-depth review of the 2 keys.

### Upload Key

The upload key signs your app for upload to the Google Play Store. The team's app release manager should [create the upload key](https://developer.android.com/studio/publish/app-signing#sign-apk). 

If your app's code is in the [bcgov GitHub organization](https://github.com/bcgov), use a [GitHub Action](https://docs.github.com/en/actions) to build and sign your app with the upload key. 

Refer to Google's [Sign your app from command line](https://developer.android.com/build/building-cmdline#sign_cmdline) documentation for instructions on how to do this. Store the key ([encoded as base64](https://docs.github.com/en/actions/security-guides/encrypted-secrets#storing-base64-binary-blobs-as-secrets)), its alias and the password as a [secret](https://docs.github.com/en/actions/security-guides/encrypted-secrets) in your app's repo. 


The [bc-wallet-mobile](https://github.com/bcgov/bc-wallet-mobile/blob/main/.github/workflows/main.yaml) project is a good example of a project using GitHub Actions.

If you're using a different git host, review its documentation on how to create a CI/CD pipeline. Use its secret feature to store the key and password securely.

If you don't use a CI/CD pipeline, store the key and password somewhere securely. 

You may request an upload key reset if the key is lost. Access to this feature is restricted by Google. The account holder from the Developer Experience team will submit the reset request. [Contact us](contact.md) to start this process.

We encourage teams to use a CI/CD pipeline. It provides repeatable builds and safely stores the credentials.

### App Signing Key

Use the [Play App Signing](https://developer.android.com/studio/publish/app-signing#app-signing-google-play) service to sign your app. If you don't use this service and you lose your app’s signing key, you lose the ability to update your app. Google's [Using Play App Signing](https://developer.android.com/studio/publish/app-signing#enroll) documentation describes how to set it up for your app.

