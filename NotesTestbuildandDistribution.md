## Steps to submit to apple store

#### Manually register devices
1. Manually register devices with name and UUID

2. Create archive remembering to manually bump version number.

3. Choose to distribute with testflight or another 3rd party application.
- Development team
- Account
- Select any on demand resources to be uploaded
- Manually add testers

### Environment Variables for Jenkins
- FASTLANE_USER: Your App Store Connect / Apple Developer Portal user, if your fastlane setup accesses App Store Connect or the Apple Developer Portal (e.g. submit a TestFlight build, create a profile, ...)
- FASTLANE_PASSWORD: Your App Store Connect / Apple Developer Portal password, usually only needed if you also set the FASTLANE_USER variable
- MATCH_PASSWORD: You need to provide the password of your match encryption if you use match
- FASTLANE_APPLE_APPLICATION_SPECIFIC_PASSWORD: You need to provide an application specific password if you have 2-factor enabled and use pilot or deliver to upload a binary to App Store Connect
- FASTLANE_SESSION: You need to provide a pregenerated session via fastlane spaceauth if you have 2-factor authentication enabled and want to use any actions that communicates with App Store Connect.
- LANG and LC_ALL: These set up the locale your shell and all the commands you execute run at. fastlane needs these to be set to an UTF-8 locale to work correctly, for example en_US.UTF-8. Many CI systems come with a locale that is unset or set to ASCII by default, so make sure to double-check whether yours is set correctly.

### Snapshot Setup
- Create a dedicated test target & scheme for snapshots.
- Run 'snapshot init' (in Terminal) to generate a custom 'Snapshot Helper.swift' file
- Add 'Snapshot Helper.swift' to your Test Target.
- Add a UI Test method to step through app views.
- Call snapshot() to take photos.