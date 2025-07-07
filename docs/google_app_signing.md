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

Securely store the key and its password. 


You may request to reset an upload key if it is lost. Only the account holder from the Developer Experience team can submit the reset request. [Contact us](contact.md) to start this process.



### App Signing Key

Use the [Play App Signing](https://developer.android.com/studio/publish/app-signing#app-signing-google-play) service to sign your app. If you don't use this service and you lose your app’s signing key, you lose the ability to update your app. Google's [Using Play App Signing](https://developer.android.com/studio/publish/app-signing#enroll) documentation describes how to set it up for your app.


## Automated build and signing

Automate your app's build and signing process by using a [GitHub workflow](https://docs.github.com/en/actions):

- Store the upload key ([encoded as base64](https://docs.github.com/en/actions/security-guides/encrypted-secrets#storing-base64-binary-blobs-as-secrets)), its alias and the password as a [secret](https://docs.github.com/en/actions/security-guides/encrypted-secrets) in your app's repo. 
- The [Google signing for React Native apps](google_react_native_signing.md#github-action) page provides an example workflow
  - If you're not using React Native, refer to Google's [Sign your app from command line](https://developer.android.com/build/building-cmdline) documentation to create a workflow that signs your app.
- The [bc-wallet-mobile](https://github.com/bcgov/bc-wallet-mobile/blob/main/.github/workflows/main.yaml) project is a good example of a project using GitHub Actions.

We encourage teams to use a CI/CD pipeline. It provides repeatable builds and safely stores the credentials.
