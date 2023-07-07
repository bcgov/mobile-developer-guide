# Publish Your App 

## Distribution methods
Please see the [Mobile App Distribution Methods](distribution_methods.md) page for an overview of how apps are distributed. 


## CI/CD
If you are using GitHub Actions as the CI/CD pipeline for your app, then you can upload the build artifact to both App Store Connect and Play Console from your pipeline. Let the [Developer Experience](contact.md) team know so we can give access to the API keys.

See the [bc-wallet-mobile](https://github.com/bcgov/bc-wallet-mobile/blob/main/.github/workflows/main.yaml) project as an example.

### App Store Connect
Let us know if you plan to just upload the build, or if you want to ship it to TestFlight. The credentials are stored in the bcgov organizations secrets. We will grant your repository access to them. 

### Play Console

