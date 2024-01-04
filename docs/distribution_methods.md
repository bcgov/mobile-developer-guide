# Mobile app distribution methods

Mobile apps are distributed through the public app stores or MDM InTune. Your distribution method is determined by who will use your app.

![Diagram of the various distribution methods. If the app is for the general public, it's distributed via the Apple App Store and Google Play Stores. If it's an app for Government employees, it's distributed via MDM inTunes. If it's an app for Employees and Contractors it is distributed as an unlisted app via the Apple App Store.](assets/distribution.drawio.svg)

## Public apps
Public apps are released through the Province's accounts on the Apple App Store and Google Play Store. 

You must list your app through the Province's accounts. The [Developer Experience team](contact.md) helps you get your app on these accounts.

Before contacting the Developer Experience team, we recommend reviewing the [project initiation information](getting_started.md).

Once setup is complete, you'll have access to [App Store Connect](https://appstoreconnect.apple.com) and [Google Play Console](https://play.google.com/console/about/) to manage your app.

## Internal apps
Employee apps are distributed through [MDM inTune by the OCIO Device Management Team](https://citz.sp.gov.bc.ca/sites/ES/DS/MDAS/Docs/SitePages/Home.aspx). While historically, employee apps only supported iOS devices, they're now also supported by Android. If you're planning to create an internal Android app, [contact us](contact.md). 

[Contact us](contact.md) at the start of your project so we can discuss the process for distributing an internal app. It requires setup from both the Developer Experience and OCIO Device Management teams.

### Apple Custom App 

Use this distribution method for internal apps used only by employees. These apps are either made specifically for the Province of BC or are a SaaS solution. 

Custom apps go through Apple's app review process. The same app review guidelines for App Store Apps apply to Custom Apps.

Custom Apps are licensed from [Apple Business Manager (ABM)](https://support.apple.com/en-ca/guide/apple-business-manager/welcome/web) and assigned to the OCIO Device Management team's Intune Tenancy. They will distribute the app through MDM-Intune. 

#### Product Owner responsibilities

The Product Owner will work with the relevant teams to decide whether to use the OCIO’s ABM or the Ministry’s own ABM.

If the Ministry decides to use its own ABM, it would need to create and manage it. As part of the setup it would add the OCIO’s MDM-Intune Organization ID as a location.

The Product Owner will provide the ABM ID to the developer.


#### Developer responsibilities

The developer handles developing the app and uploading it to [App Store Connect](https://appstoreconnect.apple.com). They will make the Custom App available to the appropriate ABM. Refer to Apple's [Distributing Custom Apps](https://developer.apple.com/custom-apps/) documentation for  instructions.


#### OCIO Device Management team responsibilities

The OCIO Device Management Team will distribute the app to employee devices. They will work with the Product Owner to schedule the release.


### Apple Enterprise App

Use this distribution method for internal apps used only by employees. These apps are specifically made for the Province and are not SaaS solutions. This distribution method is for apps that can't go through Apple's app review process.


#### Product Owner responsibilities

The Product Owner will work with the Developer Experience team to decide which GitHub organization will host the project's code.

They will get the binary from the developer and provide it to the OCIO Device Management team.

#### Developer resposibilities

The developer handles developing the app and providing the binary to the Product Owner. A repeatable CI/CD pipeline is expected as part of this process.


#### OCIO Device Management team resposibilities

The OCIO Device Management Team will distribute the app to employee devices. They will work with the Product Owner to schedule the release.

### Enterprise vs Custom App

|    | Enterprise  App | Custom App |
| -- | --------------- | ---------- |
| App goes through Apple's App Review | No | Yes |
| App usable with expired certificate |  No |  Yes | 
| App usable with expired provisioning profile |  No |  Yes | 
| Can be a SaaS solution | No | Yes |
| TestFlight | No | Yes |


### Apple Unlisted App

Use this method when your app is an internal app used by employees and contractors. Refer to [Apple's documentation](https://developer.apple.com/support/unlisted-app-distribution/) on how to distribute unlisted apps. These apps require some extra setup in App Store Connect. The [Developer Experience team](contact.md) will assist in this setup.

Unlisted apps will go through Apple's app review process. Ensure your app meets [Apple's guidelines](https://developer.apple.com/app-store/review/).

## App review process
Both the Apple App Store and Google Play Store have an app review process. 

When creating your app, it's important to consider how the app reviewer will interact with your app. For example, if your app requires a user to login, the app reviewer will need either an account or access to a demo account. 

Consult the [Apple app guidelines](https://developer.apple.com/app-store/review/) and [Google app guidelines](https://support.google.com/googleplay/android-developer/answer/9859455?hl=en&ref_topic=7072031&sjid=10634496881788336983-NA) when preparing your app's release. It's important to follow their guidelines to ensure a smooth review process.



## Beta testing distribution

An app can be distributed for beta testing before its official release. 

Apple offers [TestFlight](https://developer.apple.com/testflight/) and Google offers [open, closed and internal testing](https://support.google.com/googleplay/android-developer/answer/9845334?_ga=2.46417955.584331364.1687196439-22968901.1675209271&_gac=1.16068354.1687196439.EAIaIQobChMImu70vvDP_wIV4w6tBh0qkAu2EAAYASAAEgIVwvD_BwE). Both platforms allow you to invite testers to try out your app on their devices before its official release. This provides an opportunity to gather feedback and make improvements before the public launch.


## Further reading

### Apple documentation
* [App Store Connect Documentation](https://developer.apple.com/help/app-store-connect/)
* [Distribution Methods](https://developer.apple.com/help/app-store-connect/manage-your-apps-availability/set-distribution-methods)
* [App Distribution – From Ad-hoc to Enterprise](https://developer.apple.com/videos/play/wwdc2019/304/)
* [Explore unlisted app distribution](https://developer.apple.com/videos/play/tech-talks/10892/)

### Google documentation

* [Google Play Console Documentation](https://support.google.com/googleplay/android-developer/?hl=en&sjid=10634496881788336983-NA#topic=7071529)
* [Control when app changes are reviewed and published](https://support.google.com/googleplay/android-developer/answer/9859654?hl=en&ref_topic=7072031&sjid=10634496881788336983-NA)
* [Publish private apps](https://support.google.com/googleplay/work/answer/6145139?sjid=10634496881788336983-NA)


If you have any further questions, contact the [Developer Experience Team](contact.md). We're here to support you throughout the process.