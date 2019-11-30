# update_fastlane

default_platform(:ios)

platform :ios do
#-----------------------------------Phase II, delete me when begining phase II
  # desc "produce creates new iOS apps on both the Apple Developer Portal and App Store Connect with the minimum required information."
  # lane :register_app do
  #   produce(
  #     username: "STRING Your Apple ID Username",
  #     app_identifier: "STRING App Identifier (Bundle ID, e.g. com.krausefx.app) (PRODUCE_APP_IDENTIFIER)",
  #     app_name: "STRING App Name",
  #     team_name: "STRING The name of your Developer Portal team if you're in multiple teams",
  #     itc_team_name: "STRING The name of your App Store Connect team if you're in multiple teams"
  #   )
  # end
  
  # desc "Automate management of development certificates - This will check if any of the available signing certificates is installed on your local machine.
  #       sigh can create, renew, download and repair provisioning profiles (with one command). 
  #       It supports App Store, Ad Hoc, Development and Enterprise profiles and supports nice features, like auto-adding all test devices."
  # lane :get_dev_certs do
  #   cert(development: true)
  #   sigh(development: true)
  # end
  
  # desc "Update iOS UDID's on the Developer Portal"
  # lane :sync_device_info do
  #   register_devices(
  #     devices: {
  #       "device name" => "UUID",
  #       "another device" => "UUID"
  #     }
  #   )
  #   end

  #   desc "Sync team Code-Signing assets"
  #   lane :sync_signing_assets do |options|
  #     sync_device_info
  #     selectedType = options[:type]
  #     match(type: "selectedType")
  #   end
  #-----------------------------------Phase II, delete me when begining phase II

    desc "Build for App Store submission"
    lane :build_appstore do
      #sync_signing_assets(type: "appstore") --Referencing lane sync_signing_assets-- Phase II
      increment_build_number
      gym(
        output_directory: "build_Appstore",
        export_method: "app_store"
      )
    end

    desc "Build for Ad Hoc submission"
    lane :build_adhoc do
      #sync_signing_assets(type: "adhoc") --Referencing lane sync_signing_assets-- Phase II
      increment_build_number
      gym(
        output_directory: "build_AdHoc",
        export_method: "ad-hoc"
      )
    end

    lane :distribute_to_appstore do
      build_appstore
      pilot(
        team_name: "STRING The name of your Developer Portal team if you're in multiple teams",
        changelog: "Version" {lane_context[SharedValues::VERSION_NUMBER]}, Build {lane_context[SharedValues::BUILD_NUMBER]}
      )
    end
  
end
