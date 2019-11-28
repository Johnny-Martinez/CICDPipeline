# This file contains the fastlane.tools configuration
# You can find the documentation at https://docs.fastlane.tools
#
# For a list of all available actions, check out
#
#     https://docs.fastlane.tools/actions
#
# For a list of all available plugins, check out
#
#     https://docs.fastlane.tools/plugins/available-plugins
#

# Uncomment the line if you want fastlane to automatically update itself
# update_fastlane

default_platform(:ios)

platform :ios do
  lane :register_app do
    #produce creates new iOS apps on both the Apple Developer Portal and App Store Connect with the minimum required information.
    produce(
      username: "STRING Your Apple ID Username",
      app_identifier: "STRING App Identifier (Bundle ID, e.g. com.krausefx.app) (PRODUCE_APP_IDENTIFIER)",
      app_name: "STRING App Name",
      team_name: "STRING The name of your Developer Portal team if you're in multiple teams",
      itc_team_name: "The name of your App Store Connect team if you're in multiple teams"
    )
  end

  lane :get_dev_certs do
    #Automate management of development certificates - Create or revoke certs
    #This will check if any of the available signing certificates is installed on your local machine.
    cert(development: true)
    #sigh can create, renew, download and repair provisioning profiles (with one command). 
    #It supports App Store, Ad Hoc, Development and Enterprise profiles and supports nice features, like auto-adding all test devices.
    sigh(development: true)
  end


end
