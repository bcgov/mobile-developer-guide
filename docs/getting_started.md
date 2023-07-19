# Project initiation

You have an idea for an app and you have approval from your ministry. You're excited to start building. 

Before getting started, book an onboarding meeting with the [Developer Experience team](contact.md). This meeting helps us set up your project in the mobile developer accounts. To make the most of our time together, prepare for the meeting and gather the required information.

## Information to prepare for your onboard meeting

### Contact info

Provide contact information for the:

* Product owner
* Technical owner

Ideally, both positions should be government employees. 

### Target audience

Who will use this app? Will it be:

* the general public
* internal government employees 
* internal government employees and contractors

 The app's [distribution method](distribution_methods.md) is dependent on this answer. 

### App details
 
#### Name

The name of your mobile app.

#### Platform

Is the app for: 

* Android devices
* iOS devices 
* Android and iOS devices

#### Application/bundle ID 

The Google application ID and Apple bundle ID should be in the form `gov.bc.ca.appname`. 

The ID must be unique across all apps published under the Province's accounts. The Developer Experience Team will work with you to ensure a unique ID. 

Use the same value for both the bundle ID and application ID.

Refer to Google's [application ID](https://developer.android.com/build/configure-app-module#set-application-id) and Apple's [Bundle IDs](https://developer.apple.com/documentation/appstoreconnectapi/bundle_ids) documentation for more details.



#### Apple services

Provide any capabilities the Apple app will require, such as push notifications and maps. Refer to [Apple's capabilities documentation](https://developer.apple.com/help/account/reference/supported-capabilities-ios/) for the complete list.

#### Management permissions

Who should have access to manage the app on the app stores and what access level should they have? Refer to the [App Managment](app_management.md) section for more details.

### Code details

#### Who owns the code

Who owns the app's intellectual property:

* The ministry
* The vendor


#### Where is the code located

If the ministry owns the app's intellectual property, where will the code be located:

* GitHub
* BitBucket Server 
* Elsewhere

Can the code be public? If the code will live on the [bcgov GitHub organization](https://github.com/bcgov), provide us with the developers' GitHub IDs so we can add them to the organization.

### Does the app need a new backend service

If your app needs a new backend service then talk to the [Platform Service Team](https://cloud.gov.bc.ca) to get it setup on OpenShift.
