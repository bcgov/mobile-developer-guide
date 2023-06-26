# Getting Started

You have an idea for an app. You have approval from your ministry and you're excited to start building. However, before diving in, please book an onboarding meeting with the Developer Experience Team at: [Developer.Experience@gov.bc.ca](mailto:Developer.Experience@gov.bc.ca). This meeting will help us set up your project in the mobile developer accounts. To make the most of our time together, please gather the information outlined below.

## Onboard Meeting Checklist

| Info | Response |
|------|-------|
| Product Owner<sup>1</sup> | |
| Techical Owner<sup>1</sup> | |
| App Audience<sup>2</sup>| |
| App name| |
| App application/bundle id<sup>3</sup> | | 
| Apple services<sup>4</sup> | |
| App Platform<sup>5</sup>| |
| Who owns the code<sup>6</sup> | |
| Where is the code located<sup>7</sup>|
| App Management Access<sup>8</sup>||
| Does the app need a new backend service<sup>9</sup>| |


1. Please provide contact information for both the product and technical owners. Ideally, both positions should be government employees. 
1. Who will use this app? Will it be the general public, internal government employees and/or contractors? The app's [distribution method](distribution_methods.md) is dependent on this answer. 
1. The Google application id and Apple bundle id should be in the form `gov.bc.ca.appname`. The id must be unique across all apps published under the Province's accounts. The Developer Experience Team will work with you to ensure a unique id.  Use the same value for both the bundle id and application id. Please refer to Google's [application id](https://developer.android.com/build/configure-app-module#set-application-id) and Apple's [Bundle IDs](https://developer.apple.com/documentation/appstoreconnectapi/bundle_ids) documentation for more details.
1. Please provide any capabilities the Apple app will require, such as push notifications, maps etc... Please refer to [Apple's capabilities documentation](https://developer.apple.com/help/account/reference/supported-capabilities-ios/) for the complete list.
1. Is the app for both Android and iOS devices or only one platform (e.g. only iOS).
1. Does the app's intellectual property belong to the ministry or the vendor? 
1. Please provide this information if the ministry owns the app's intellectual property. Will the code be in GitHub, BitBucket Server, or somewhere else? Can the code be public? If the code will live on the [bcgov GitHub organization](https://github.com/bcgov), then please provide the GitHub Ids of the developers. We will add them to the organization.
1. Who should have access to manage the app on the app stores and what access level should they have? Please refer to the [App Managment](app_management.md) section for more details.
1. If yes, have you talked to the [Platform Service Team](https://cloud.gov.bc.ca)?

We look forward to meeting with you!