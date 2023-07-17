# Export encryption compliance

Your app must abide by [U.S. export restrictions](https://www.bis.doc.gov/index.php/policy-guidance/encryption) if it's available for download outside of the U.S. or Canada. This is because both Apple and Google's app store servers are in the United States. If a user from another country downloads the app, it comes from a U.S. server and the server exports the app to another country.


## Apple App Store

Use [App Store Connect's tool](https://developer.apple.com/help/app-store-connect/manage-app-information/detemine-and-upload-export-compliance-documentation) to determine if you need compliance documentation. Once you know your [app's export compliance](https://developer.apple.com/help/app-store-connect/reference/export-compliance-documentation-for-encryption), you can [Declare Your App’s Use of Encryption](https://developer.apple.com/documentation/security/complying_with_encryption_export_regulations) in the [Info.plist](https://developer.apple.com/documentation/bundleresources/information_property_list) file. Future app submissions will no longer need to answer compliance review questions.

Refer to Apple's [Overview of export compliance](https://developer.apple.com/help/app-store-connect/manage-app-information/overview-of-export-compliance) for further details.

## Google Play Store

Use Google's [Export compliance](https://support.google.com/googleplay/android-developer/answer/113770?hl=en) documentation.

Unlike Apple, Google does not ask for compliance documentation.  Your app is expected to follow U.S. regulations.

# Your app's compliance
It's important for you to determine your app's compliance. If you distribute your app outside of Canada, you need to follow [U.S. encryption export regulations](https://www.bis.doc.gov/index.php/policy-guidance/encryption). If you need help determining your compliance level, contact [Legal Services Branch](https://dir.gov.bc.ca/gtds.cgi?show=Branch&organizationCode=AG&organizationalUnitCode=LEGAL).