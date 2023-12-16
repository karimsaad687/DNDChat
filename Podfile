
# Uncomment the next line to define a global platform for your project
 platform :ios, '15.0'
workspace 'DNDChat.xcworkspace'
project 'DNDChat.xcodeproj'

use_frameworks!

def _resource
  pod 'R.swift','~> 5.1.0'
  end


def _corePackage
  pod 'KRProgressHUD'
  pod 'NotificationBannerSwift'
  end

def _CorePods
  _resource
  _corePackage
  pod 'IQKeyboardManagerSwift'
  pod 'Kingfisher', '~> 7.0'
  pod "BSImagePicker", "~> 3.1"
  pod 'KDCircularProgress'
  pod 'VideoSDKRTC'
  end
target 'DNDChat' do
  # Comment the next line if you don't want to use dynamic frameworks
  
  _CorePods
  pod 'Alamofire'
  pod 'CropViewController'

post_install do |installer|
  installer.pods_project.targets.each do |target|
    target.build_configurations.each do |config|
	if target.name == 'R.swift.Library' ||
	   target.name == 'NotificationBannerSwift' ||
           target.name == 'CropViewController'
       	   config.build_settings['IPHONEOS_DEPLOYMENT_TARGET'] = '11.0'
      	end
        
    end
  end
end

  end

target 'chatsModule' do
  project '../DNDProject/chatsModule/chatsModule.project'
  _CorePods
  end

target 'NetworkLayer' do
  project '../DNDProject/NetworkLayer/NetworkLayer.project'
  _corePackage
  pod 'Alamofire'
  end

target 'DNDCorePackage' do
  project '../DNDProject/DNDCorePackage/DNDCorePackage.project'
  _corePackage
  
  end

target 'DNDResources' do
  project '../DNDProject/DNDResources/DNDResources.project'
  _resource
  
  end

target 'PhotoLibraryMedia' do
  
  project '../DNDProject/PhotoLibraryMedia/PhotoLibraryMedia.project'
  pod 'CropViewController'
  _resource
  _corePackage
  
end
