platform :ios, '15'
use_frameworks! :linkage => :static

inhibit_all_warnings!

post_install do |installer|
  installer.pods_project.targets.each do |target|
    if target.name == 'BoringSSL-GRPC'
      target.source_build_phase.files.each do |file|
        if file.settings && file.settings['COMPILER_FLAGS']
          flags = file.settings['COMPILER_FLAGS'].split
          flags.reject! { |flag| flag == '-GCC_WARN_INHIBIT_ALL_WARNINGS' }
          file.settings['COMPILER_FLAGS'] = flags.join(' ')
        end
      end
    end
  end
end

target 'SessionsTestApp' do
  use_modular_headers!
  pod 'FirebaseAnalytics', '10.16.0'
  pod 'FirebaseAuth', '10.16.0'
  pod 'FirebaseCrashlytics', '10.16.0'
  pod 'FirebaseFirestore', '10.16.0'
  pod 'FirebaseFunctions', '10.16.0'
  pod 'FirebaseMessaging', '10.16.0'
  pod 'FirebaseStorage', '10.16.0'
  pod 'FirebaseRemoteConfig', '10.16.0'
  pod 'FirebaseDynamicLinks', '10.16.0'
  pod 'FirebaseABTesting', '10.16.0'
  pod 'FirebaseAppCheckInterop', '10.16.0'
  pod 'FirebaseCore', '10.16.0'
  pod 'FirebaseCoreExtension', '10.16.0'
  pod 'FirebaseCoreInternal', '10.16.0'
  pod 'FirebaseInstallations', '10.16.0'
  pod 'FirebaseMessagingInterop', '10.16.0'
  pod 'FirebaseSessions', '10.16.0'
  pod 'FirebaseSharedSwift', '10.16.0'
  pod 'GoogleAppMeasurement', '10.16.0'
end
