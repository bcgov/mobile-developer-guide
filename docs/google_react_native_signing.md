# Google Signing For React Native Apps

## Prerequisite
Your app must be setup to use [Google Play App Signing](Play App Signing](https://developer.android.com/studio/publish/app-signing#app-signing-google-play) and have an [upload key](). Please see the [Google App Signing](google_app_signing.md) guide for more details.

## Modify Gradle Files and Sign Release

Now that we got the upload key generated we need to modify the gradle files to have a release config for production builds. The configuration below relies on a .env file that stores:

* KEYSTORE={fileNameFromAbove}.keystore
* KEY_ALIAS={alias-from-above}
* STORE_PASSWORD={password-from-above}
* KEY_PASSWORD={password-from-above}

> MAKE SURE NOT TO COMMIT THE .ENV FILE

On the file build.gradle add a **release** config under signing config:

```javascript
signingConfigs {
        debug {
            storeFile file('debug.keystore')
            storePassword 'android'
            keyAlias 'androiddebugkey'
            keyPassword 'android'
        }
        release {
            // We can leave these in environment variables
            storeFile file("$System.env.KEYSTORE")
            keyAlias "$System.env.KEY_ALIAS"
            storePassword "$System.env.STORE_PASSWORD"
            keyPassword "$System.env.KEY_PASSWORD"
        }
    }
```

Additionally, we need to tell Gradle to use our new config for release builds:

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

Alternatively, you can [sign your release from Android Studio](https://developer.android.com/studio/publish/app-signing#sign_release).

## Build and Upload

Now that we got Gradle setup, we can run from the Android folder:

`./gradlew bundleRelease assembleRelease`

If everything goes well, you will see something like:

![](https://github.com/bcgov/mobile-signing-service/blob/master/wiki-page-assets/react-native-4.1.png)

You will then find a .aab build under app/build/outputs/bundle/release

Navigate to the Google Play Console, and select the app for which you just build a release. Then select Internal Testing -> Edit Release -> Drag and drop the .aab bundle.

![](https://github.com/bcgov/mobile-signing-service/blob/master/wiki-page-assets/react-native-4.2.png)

Google will then give you more info on your app and will present any warning or errors you need to address. Once all that is done, and you start internal testing you will be able to see them under Releases. 

![](https://github.com/bcgov/mobile-signing-service/blob/master/wiki-page-assets/react-native-4.3.png)

For any future releases, you will just need to update the build number, rebuild using Gradle, and upload to Google.