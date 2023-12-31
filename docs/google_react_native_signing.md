# Google signing for React Native apps

Learn how to setup Google signing in a CI/CD pipeline using GitHub Actions.

Need a general overview of what app signing is? Review React Native's [Publishing to Google Play Store](https://reactnative.dev/docs/signed-apk-android) guide which describes how to sign an app from a developer's computer. 

Follow these steps to sign your React Native app:

1. [Setup Google Play App Signing](google_react_native_signing.md#setup-google-play-app-signing)
1. [Create the upload key](google_react_native_signing.md#create-the-upload-key)
1. [Update Gradle files ](google_react_native_signing.md#update-gradle-files)
1. [Setup GitHub Action](google_react_native_signing.md#github-action)
1. [Upload the build](google_react_native_signing.md#upload-the-build)

## Setup Google Play App Signing
Your app must be setup to use [Google Play App Signing](https://developer.android.com/studio/publish/app-signing#app-signing-google-play).

## Create the upload key
Follow React Native's [instructions to generate an upload key](https://reactnative.dev/docs/signed-apk-android#generating-an-upload-key).


In your app's GitHub repo, setup 4 secrets:

* ANDROID_UPLOAD_KEYSTORE_BASE64={file-name-from-above}.keystore - encoded as base64
* ANDROID_KEY_ALIAS={alias-from-above}
* ANDROID_SIGNING_STORE_PASSWORD={password-from-above}
* ANDROID_SIGNING_KEY_PASSWORD={password-from-above}

To encode the keystore file as base64, use this command:

`base64 -i your-keystore-file.keystore | pbcopy`


## Update Gradle files 

In the `android/app/build.gradle` file add a `release` config under `signingConfigs`. 

```js
signingConfigs {
        debug {
            storeFile file('debug.keystore')
            storePassword 'android'
            keyAlias 'androiddebugkey'
            keyPassword 'android'
        }
        release {
            // This will look for the release.keystore file in the android/app/ folder. The release.keystore file will be created in the GitHub Action
            storeFile = file("release.keystore")
            // The environment keys must match the secret keys setup in GitHub
            keyAlias System.getenv("ANDROID_KEY_ALIAS")
            storePassword System.getenv("ANDROID_SIGNING_STORE_PASSWORD")
            keyPassword System.getenv("ANDROID_SIGNING_KEY_PASSWORD")
        }
    }
```

You also need to tell Gradle to use the new config for release builds:

```js
    buildTypes {
        debug {
            signingConfig signingConfigs.debug
        }
        release {
            // Using release from above
            signingConfig signingConfigs.release
        }
    }    
```

Optionally, set the versionCode automatically from GitHub Actions 
```js
defaultConfig {
        ...
        versionCode System.getenv("VERSION_CODE") ? System.getenv("VERSION_CODE").toInteger() : 1
        versionName "1.1"
        ...
    }
```

## GitHub Action

Review the [bc-mobile-wallet](https://github.com/bcgov/bc-wallet-mobile) project for a complete GitHub Action workflow. 

Example of a basic GitHub Action:

```yaml
name: Build
on: 
  push:
    branches: [ "main" ]

jobs:
  build:
    name: Build and sign android bundle
    runs-on: ubuntu-latest

    env:
      # The file name name MUST match the storeFile in the build.gradle file
      KEYSTORE_FILE: android/app/release.keystore

    steps:
      - name: Checkout
        uses: actions/checkout@v3

      - name: Setup Node.js environment
        uses: actions/setup-node@v3 
        with:
            cache: 'yarn'
            node-version: 19

      - name: Install node modules
        run: |
          yarn install --frozen-lockfile

      - name: Setup Gradle 
        uses: gradle/gradle-build-action@v2

      # The keystore was base64 encoded. It must be decoded in order to use it
      - name: Decode keystore file
        env:
          UPLOAD_KEYSTORE: ${{ secrets.ANDROID_UPLOAD_KEYSTORE_BASE64 }}
        run: |
          echo "${UPLOAD_KEYSTORE}" | base64 -d > ${KEYSTORE_FILE}

      - name: Sign app 
        env:
          # These environment keys MUST match the keys in the build.gradle file
          ANDROID_KEY_ALIAS: ${{ secrets.ANDROID_KEY_ALIAS }}
          ANDROID_SIGNING_KEY_PASSWORD: ${{ secrets.ANDROID_SIGNING_KEY_PASSWORD }}
          ANDROID_SIGNING_STORE_PASSWORD: ${{ secrets.ANDROID_SIGNING_STORE_PASSWORD }}
          # Automatically update the VersionCode number in the build.gradle file. The number is not committed to git.
          VERSION_CODE: ${{ github.run_number }}
        run: |
            npx react-native build-android --mode=release
       
      - name: Upload Artifact
        uses: actions/upload-artifact@v3
        with:
            name: Signed App Bundle
            # This is the default path where the bundle is created
            path: android/app/build/outputs/bundle/release/app-release.aab
            if-no-files-found: error
            retention-days: 7    
```

## Upload the build

### GitHub Action upload
Review the [Publish Your App](publish.md) page for information on how to upload from your CI/CD pipeline.

### Manual upload

To upload the file:

1. Download the `app-release.aab` file from the GitHub Action 
1. Follow Google's [Prepare and roll out a release](https://support.google.com/googleplay/android-developer/answer/9859348?sjid=4924136940059865319-NA) documentation