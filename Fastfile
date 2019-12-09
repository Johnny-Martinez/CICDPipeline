default_platform(:ios)

platform :ios do
#-----------------------------------Phase II, delete me when begining phase II
  # lane :register_app do
  #   produce(
  #   username: "bschick1@mac.com",
  #   app_identifier: "com.razeware.chew",
  #   app_name: "Chew Chew Train",
  #   team_name: "Brian Schick",
  #   itc_team_name: "Brian Schick"
  #   )
  # end
  
  # lane :get_dev_certs do
  #   cert(development: true)
  #   sigh(development: true)
  # end

  # desc "Re-obtain match code-signing credentials after switching to a Beginning or Ending project folder"
  # lane :bootstrap_code_signing do
  #   sync_device_info
  #   match(type: "development")
  #   match(type: "adhoc")
  #   match(type: "appstore")
  # end
  
  # desc "Update iOS UDID's on the Developer Portal"
  # lane :sync_device_info do
  #   register_devices(
  #   devices_file: "fastlane/Devicefile"
  #   )
  # end
  
  # desc "Sync team Code-Signing assets"
  # lane :sync_signing_assets do |options|
  #   sync_device_info
  #   selectedType = options[:type]
  #   match(type: selectedType)
  # end
#-----------------------------------Phase II, delete me when begining phase II
  desc "Compiles app for App Store submission"
  lane :build_appstore do #build is stored in build_Appstore directory
    
    #begining git actions
    ensure_git_status_clean
    ensure_git_branch(branch: staging)
    git_pull

    #sync_signing_assets(type: "appstore") --Referencing lane sync_signing_assets-- Phase II
    increment_build_number
    gym(
      output_directory: "build_Appstore",
      export_method: "app_store"

    #ending git actions
    commit_version_bump(
      force: true,
      message: "Version bumped by fastlane"
    )
    add_git_tag(
      grouping: "fastlane",
      build_number: lane_context[SharedValues::BUILD_NUMBER]
    )
    push_to_git_remote
    )
  end
  
  desc "Compiles app for Ad Hoc submission. Distribute app to testers on registered devices only. Apps expire in a few days and will stop working."
  lane :build_adhoc do
    #sync_signing_assets(type: "adhoc") --Referencing lane sync_signing_assets-- Phase II
    increment_build_number
    gym(
      output_directory: "build_AdHoc",
      export_method: "ad-hoc"
    )
  end
  
  desc "Calls on build_appstore, which then will increment build number and compiles app along with distributing to TestFlight. App expires after 90 days."
  lane :distribute_to_appstore do
    build_appstore # --Referencing lane build_appstore to compile app
    pilot(
      team_name: "STRING The name of your Developer Portal team if you're in multiple teams",
      changelog: "Version lane_context[SharedValues::VERSION_NUMBER]}, Build {lane_context[SharedValues::BUILD_NUMBER]}" #What to Test field.
    )
  end
  
  lane :release do
    precheck
    snapshot
    framit(gold: true)
    deliver(
    ipa: "./build_AppStore/ChewChewTrain.ipa",
    run_precheck_before_submit: false,
    force: true,
    team_name: "<teamname>"
    )  
  end
  
end
