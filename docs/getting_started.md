# Project initiation

You have an idea for an app and you have approval from your ministry. You're excited to start building. 

Before getting started, book an onboarding meeting with the [Developer Experience team](contact.md). This meeting helps us set up your project in the mobile developer accounts. To make the most of our time together, prepare for the meeting and gather the required information.

## Information to prepare for your onboard meeting

| General information | Response |
|------|-------|
| Product Owner name<sup>1</sup> | |
| Techical Owner name<sup>1</sup> | |
| Targeted audience<sup>2</sup>| |
| App name| |
| App application/bundle ID<sup>3</sup> | | 
| Apple services<sup>4</sup> | |
| App platform<sup>5</sup>| |
| Who owns the code<sup>6</sup> | |
| Where is the code located<sup>7</sup>|
| App management access<sup>8</sup>||
| Does the app need a new backend service<sup>9</sup>| |


1. Provide contact information for both the product and technical owners. Ideally, both positions should be government employees. 
1. Who will use this app? Will it be the general public, internal government employees and/or contractors? The app's [distribution method](distribution_methods.md) is dependent on this answer. 
1. The Google application ID and Apple bundle ID should be in the form `gov.bc.ca.appname`. The ID must be unique across all apps published under the Province's accounts. The Developer Experience Team will work with you to ensure a unique ID. Use the same value for both the bundle ID and application ID. Refer to Google's [application ID](https://developer.android.com/build/configure-app-module#set-application-id) and Apple's [Bundle IDs](https://developer.apple.com/documentation/appstoreconnectapi/bundle_ids) documentation for more details.
1. Provide any capabilities the Apple app will require, such as push notifications and maps. Refer to [Apple's capabilities documentation](https://developer.apple.com/help/account/reference/supported-capabilities-ios/) for the complete list.
1. Is the app for both Android and iOS devices or only one of those platforms?
1. Does the app's intellectual property belong to the ministry or the vendor? 
1. If the ministry owns the app's intellectual property, will the code be in GitHub, BitBucket Server or elsewhere? Can the code be public? If the code will live on the [bcgov GitHub organization](https://github.com/bcgov), provide us with the developers' GitHub IDs so we can add them to the organization.
1. Who should have access to manage the app on the app stores and what access level should they have? Refer to the [App Managment](app_management.md) section for more details.
1. If your app needs a new backend service then talk to the [Platform Service Team](https://cloud.gov.bc.ca) to get it setup on OpenShift.

We look forward to meeting with you!