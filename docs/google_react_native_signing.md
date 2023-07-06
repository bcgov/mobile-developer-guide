# Google Signing For React Native Apps

## Prerequisite
Your app must be setup to use [Google Play App Signing](Play App Signing](https://developer.android.com/studio/publish/app-signing#app-signing-google-play) and have an [upload key](https://developer.android.com/studio/publish/app-signing#sign-apk). Please see the [Google App Signing](google_app_signing.md) guide for more details.

## Modify Gradle Files and Sign Release

Once the prerequisites are met, modify the gradle files to have a release config for production builds. The configuration below assumes the production build will be run from a GitHub Action. It assumes the following are setup as secrets in your GitHub repo.

* KEYSTORE={fileNameFromAbove}.keystore
* KEY_ALIAS={alias-from-above}
* STORE_PASSWORD={password-from-above}
* KEY_PASSWORD={password-from-above}

Example:
```yaml
 - name: Build APK
   run: ./gradlew bundleRelease assembleRelease
   env:
     KEY_ALIAS: ${{ secrets.SIGNING_KEY_ALIAS }}
     STORE_PASSWORD: ${{ secrets.SIGNING_STORE_PASSWORD }}
     KEY_PASSWORD: ${{ secrets.SIGNING_KEY_PASSWORD }}
```

In the `build.gradle` file add a `release` config under signing config:

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