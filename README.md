# ``EdgeEngineTrial``

mimik Client Library provides a programmatic way to work with the edgeEngine Runtime to access information about the mobile device on which the application is running.

@Metadata {
    @CallToAction(purpose: link, url: "https://github.com/mimikgit/cocoapod-EdgeEngineTrial")
    @PageKind(article)
    @PageColor(yellow)
}

## Overview

The purpose of the mimik Client Library is to provide a programmatic way to work with the edgeEngine Runtime to access information about the mobile device on which the application is running, as well as mobile devices running within a cluster of mobile devices that are hosting the edgeEngine Runtime. Also, to allow developers to use edge microservices running within a particular cluster.

By leveraging the Core component of the mimik Client Library, developers can build applications compatible with the edgeEngine Runtime. This not only harnesses the strength of edge computing but also provides an inherent flexibility in its paradigm.

Additionally, this component provides utility APIs that help developers with core operations such as Authentication, edgeEngine Runtime Setup, deployment of edge microservices and handling of Network calls.

Furthermore, the mimik Client Library Engine component provides additional edgeEngine Runtime utility APIs, as well as vendoring the actual edgeEngine Runtime binary into the iOS project.

## Documentation

The full mimik client library EdgeClient documentation can be accessed from [GitHub Pages](https://mimikgit.github.io/cocoapod-EdgeCore/documentation/edgecore) or the Xcode docc archive file can be downloaded as a [zip](https://github.com/mimikgit/cocoapod-EdgeCore/tree/main/EdgeCore.doccarchive.zip) and opened locally in Xcode.

The EdgeEngineClient platform protocol part of the documentation can be access from [GitHub Pages](https://mimikgit.github.io/cocoapod-EdgeCore/documentation/edgecore/edgeengineclient) 

## EdgeEngineClient Platform Protocol

### Controlling the edgeEngine Runtime

- ``EdgeEngineClient/startEdgeEngine(parameters:)``
- ``EdgeEngineClient/stopEdgeEngine()``
- ``EdgeEngineClient/restartEdgeEngine()``
- ``EdgeEngineClient/resetEdgeEngine()``
- ``EdgeEngineClient/edgeEngineIsRunning()``
- ``EdgeEngineClient/edgeEngineRuntimeIsManaged()``
- ``EdgeEngineClient/edgeEngineParameters()``
- ``EdgeEngineClient/manageEdgeEngineRuntime(enable:)``
- ``EdgeEngineClient/expectedEdgeEngineVersion()``
- ``EdgeEngineClient/setCustomPort(number:)``

For adding edgeEngine framework to your project please see: [EdgeEngine](https://github.com/mimikgit/cocoapod-EdgeEngine)

## Supported Platforms, Targets
* `iOS Devices running iOS 15+`
* `iOS Simulators running iOS 15+`
* `iOS Mac Catalyst running macOS 12.0`

For more information about working with an iOS Simulator [go here](https://devdocs.mimik.com/tutorials/12-index#workingwithaniossimulator)

## Requirements
```
iOS 15.0+
```

## Installation

To install it, simply add the following lines to your Podfile:


```swift
platform :ios, '15.0'
source 'https://github.com/CocoaPods/Specs.git'
source 'https://github.com/mimikgit/cocoapod-edge-specs.git'

use_frameworks!
inhibit_all_warnings!

def mimik
  pod 'EdgeCore'
  pod 'EdgeEngineTrial'
end

target '{target}' do
  mimik()
end

post_install do |installer|
  installer.pods_project.targets.each do |target|
    target.build_configurations.each do |config|
      config.build_settings['ENABLE_BITCODE'] = 'NO'
      config.build_settings['VALID_ARCHS'] = '$(ARCHS_STANDARD_64_BIT)'
      config.build_settings['IPHONEOS_DEPLOYMENT_TARGET'] = '15.0'
      config.build_settings['BUILD_LIBRARY_FOR_DISTRIBUTION'] = 'YES'
    end
  end
end
```


## Tutorial

Visit this [tutorial](https://devdocs.mimik.com/tutorials/11-index) to learn more about the mimik client library and how to integrate it into your iOS project.

## Community

Don't forget to checkout all mimik client libraries at [mimik GitHub](https://github.com/mimikgit/).
You can also read about other mimik activies

Umbrella cocoapods:

 * [EdgeClientLibrary (Core + Engine)](https://github.com/mimikgit/cocoapod-EdgeClientLibrary)
 * [EdgeClientLibraryTrial (Core + EngineTrial)](https://github.com/mimikgit/cocoapod-EdgeClientLibraryTrial)
 
Individual cocoapods:
 
 * [EdgeCore](https://github.com/mimikgit/cocoapod-EdgeCore)
 * [EdgeEngine](https://github.com/mimikgit/cocoapod-EdgeEngine)
 * [EdgeEngineTrial](https://github.com/mimikgit/cocoapod-EdgeEngineTrial)
 * [EdgeUser](https://github.com/mimikgit/cocoapod-EdgeUser)

## Author

[mimik Technology Inc.](https://github.com/mimikgit/)

## License

The aforementioned mimik client libraries are available under the MIT license. See the LICENSE file for more information.
