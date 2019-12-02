fastlane documentation
================
# Installation

Make sure you have the latest version of the Xcode command line tools installed:

```
xcode-select --install
```

Install _fastlane_ using
```
[sudo] gem install fastlane -NV
```
or alternatively using `brew cask install fastlane`

# Available Actions
## iOS
### ios build_appstore
```
fastlane ios build_appstore
```
Build for App Store submission
### ios build_adhoc
```
fastlane ios build_adhoc
```
Build for Ad Hoc submission
### ios distribute_to_appstore
```
fastlane ios distribute_to_appstore
```
Looks at a set of app store review rules to avoid being rejected.

----

This README.md is auto-generated and will be re-generated every time [fastlane](https://fastlane.tools) is run.
More information about fastlane can be found on [fastlane.tools](https://fastlane.tools).
The documentation of fastlane can be found on [docs.fastlane.tools](https://docs.fastlane.tools).
