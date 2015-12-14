## react-native-admob

A react-native component for Google AdMob banners

### Installation

##### iOS

1. `npm i react-native-admob -S`
2. Add [Google AdMob Framework](https://developers.google.com/admob/ios/quick-start#manually_using_the_sdk_download) to your Xcode project.
3. Add react-native-admob static library to your Xcode project like explained [here](http://facebook.github.io/react-native/docs/linking-libraries-ios.html).
4. To use it in your javascript code you can `import Banner from 'react-native-admob'` or `var Banner = require("react-native-admob")`

##### Android

Make the following additions to the given files.

**android/settings.gradle**
```
include ':RNAdMob', ':app'
project(':RNAdMob').projectDir = new File(rootProject.projectDir, '../node_modules/react-native-admob/android')
```

**android/app/build.gradle**
```
dependencies {
   ...
   compile project(':RNAdMob')
}
```

**MainActivity.java**

On top, where imports are:
```java
import com.sbugert.rnadmob.RNAdMobPackage;
```

Under `.addPackage(new MainReactPackage())`:
```java
.addPackage(new RNAdMobPackage())
```

### Usage

```javascript
<Banner
  bannerSize={"fullBanner"}
  adUnitID={"your-admob-unit-id"}
  didFailToReceiveAdWithError={this.bannerError} />
```

### Props
##### bannerSize
*Corresponding to [iOS framework banner size constants](https://developers.google.com/admob/ios/banner)*

* *banner* (320x50, Standard Banner for Phones and Tablets)
* *largeBanner* (320x100, Large Banner for Phones and Tablets)
* *mediumRectangle* (300x250, IAB Medium Rectangle for Phones and Tablets)
* *fullBanner* (468x60, IAB Full-Size Banner for Tablets)
* *leaderboard* (728x90, IAB Leaderboard for Tablets)
* *smartBannerPortrait* (Screen width x 32|50|90, Smart Banner for Phones and Tablets)
* *smartBannerLandscape* (Screen width x 32|50|90, Smart Banner for Phones and Tablets)

##### Events
*Corresponding to [Ad lifecycle event callbacks](https://developers.google.com/admob/ios/banner)*

* adViewDidReceiveAd()
* didFailToReceiveAdWithError(errorDescription)
* adViewWillPresentScreen()
* adViewWillDismissScreen()
* adViewDidDismissScreen()
* adViewWillLeaveApplication()


---

### TODO
- [ ] Add Interstitial Ads support
- [x] Add Android support (experimental)
- [ ] Add example project