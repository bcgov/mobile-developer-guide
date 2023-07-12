# Managing your app 

Provide the Developer Experience Team with the names and email addresses of who will:

* Administer the app
* Develop the app
* Respond to user reviews

We'll use this information to setup your team members on the app stores.  

## Managing user access to App Store Connect

[App Store Connect](https://appstoreconnect.apple.com/login) is the platform that allows teams to manage their apps on the Apple App Store. By assigning roles to users, you control who has access to do certain functions. 

A person may have more than one role. For example, a user may have both the App Manager and Customer Support roles. Please consult Apple's [Program Roles](https://developer.apple.com/support/roles/) documentation for the functions available to each role. 

Roles available to app team members are: 


### App Manager Role
The primary purpose of an App Manager is to oversee the management of an app on App Store Connect. Activities they perform include managing an app's submission, App Store data, and versions. They act as the central point of contact for the app's development team. This role is assigned to the Product and Technical Owners. 

### Customer Service Role
The Customer Service role responds to customer reviews. This role is usually assigned to the Product Owner. Some teams have dedicated team members in this role.

### Developer Role
The Developer role focuses on the technical aspects of app management. Developers can upload the app's build file, access TestFlight, and manage internal testers.

### Marketing Role
The Marketing role focuses on promoting and enhancing the visibility of apps. This role uses a subset of the functions available to the App Manager role. These include modifying an app's details, viewing its rating, and creating new versions.

### Sales Role
Users in the Sales role can view app analytics, sales and trends reports. This role is usually assigned to the Product Owner. But, some teams have dedicated team members in this role.




### Apple ID
Any email address may be used to create an account on App Store Connect. It does not need to be one associated with an Apple ID. But, the user will [need to create an Apple ID](https://developer.apple.com/help/app-store-connect/manage-your-team/add-and-edit-users) when activating the account.


## Managing user access to Google Play Console

[Play Console](https://accounts.google.com/ServiceLogin?service=androiddeveloper&passive=true&continue=https%3A%2F%2Fplay.google.com%2Fconsole%2Fdeveloper%2F&_ga=2.124271306.1978797360.1688067469-933612381.1687381212) is the platform that allows teams to manage their apps on the Google Play Store. It uses permission settings to control who has access to do certain functions. The Developer Experience Team will create 3 permission groups for your app:

* Admin
* Release
* Report

Users will then be assigned into one, or more, of these permission groups. 

See the "Permission definitions and uses" section in Google's [Add developer account users and manage permissions]( https://support.google.com/googleplay/android-developer/answer/9844686) documentation. It provides a complete list of the permissions available.


### Admin permission group
Users in this group have full access to the app. Their permissions also include inviting new users to the developer account. They can also add and remove permissions for other users who have access to the same apps. The Product and Technical Owners are members of this group.

### Release permission group
The permissions available to this group include the following:
* Release to production, exclude devices and use Play app signing
* Release apps to testing tracks
* Manage testing tracks and edit tester lists

The Developer Experience Team will work with you to decide which options you'd like to enable. 

Users in the [admin permission group](#admin-permission-group) can administer this group. This allows them to add or remove users from the group and enable or disable permission options.


### Report permission group
This permission group lets a user view all information for this app, but not financial data. The permission to view financial data can be enabled at the discretion of the Product Owner. Users in the [admin permission group](#admin-permission-group) for the app can administer this group.


### Google account
A user doesn't need a Gmail account in order to make a Google account. Refer to the "Use an existing email address" section in Google's [Create a Google Account](https://support.google.com/accounts/answer/27441?hl=en) documentation.
