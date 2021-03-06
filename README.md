# fake_weibo

[![Build Status](https://cloud.drone.io/api/badges/v7lin/fake_weibo/status.svg)](https://cloud.drone.io/v7lin/fake_weibo)
[![Codecov](https://codecov.io/gh/v7lin/fake_weibo/branch/master/graph/badge.svg)](https://codecov.io/gh/v7lin/fake_weibo)
[![GitHub Tag](https://img.shields.io/github/tag/v7lin/fake_weibo.svg)](https://github.com/v7lin/fake_weibo/releases)
[![Pub Package](https://img.shields.io/pub/v/fake_weibo.svg)](https://pub.dartlang.org/packages/fake_weibo)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://github.com/v7lin/fake_weibo/blob/master/LICENSE)

flutter版新浪微博SDK

## fake 系列 libraries

* [flutter版微信SDK](https://github.com/v7lin/fake_wechat)
* [flutter版腾讯(QQ)SDK](https://github.com/v7lin/fake_tencent)
* [flutter版新浪微博SDK](https://github.com/v7lin/fake_weibo)
* [flutter版支付宝SDK](https://github.com/v7lin/fake_alipay)
* [flutter版腾讯(信鸽)推送SDK](https://github.com/v7lin/fake_push)
* [flutter版talkingdata移动统计SDK](https://github.com/v7lin/fake_analytics)

## dart/flutter 私服

* [simple_pub_server](https://github.com/v7lin/simple_pub_server)

## docs

* [Android 应用接入](https://open.weibo.com/wiki/Sdk/android)
* [iOS 应用接入](https://open.weibo.com/wiki/Sdk/ios)
* [Android Github](https://github.com/sinaweibosdk/weibo_android_sdk)
* [iOS Github](https://github.com/sinaweibosdk/weibo_ios_sdk)

## android

```
# 不需要做任何额外接入工作
# 混淆已打入 Library，随 Library 引用，自动添加到 apk 打包混淆
```

## ios

```
iOS 9.0
```

```
在Xcode中，选择你的工程设置项，选中“TARGETS”一栏，在“info”标签栏的“URL type“添加“URL scheme”为你所注册的应用程序id

URL Types
weibosdk: identifier=com.weibo schemes=wb${appKey}
```

```
iOS 9系统策略更新，限制了http协议的访问，此外应用需要在“Info.plist”中将要使用的URL Schemes列为白名单，才可正常检查其他应用是否安装。
<key>LSApplicationQueriesSchemes</key>
<array>
    <string>sinaweibo</string>
    <string>sinaweibohd</string>
    <string>weibosdk</string>
    <string>weibosdk2.5</string>
</array>
<key>NSAppTransportSecurity</key>
<dict>
    <key>NSAllowsArbitraryLoads</key>
    <true/>
    <key>NSExceptionDomains</key>
    <dict>
        <key>sina.com.cn</key>
        <dict>
            <key>NSIncludesSubdomains</key>
            <true/>
            <key>NSThirdPartyExceptionAllowsInsecureHTTPLoads</key>
            <true/>
            <key>NSExceptionMinimumTLSVersion</key>
            <string>TLSv1.0</string>
            <key>NSThirdPartyExceptionRequiresForwardSecrecy</key>
            <false/>
        </dict>
    </dict>
</dict>
```
## flutter

* snapshot

```
dependencies:
  fake_weibo:
    git:
      url: https://github.com/v7lin/fake_weibo.git
```

* release

```
dependencies:
  fake_weibo: ^${latestTag}
```

* example

[示例](./example/lib/main.dart)

## Getting Started

This project is a starting point for a Flutter
[plug-in package](https://flutter.io/developing-packages/),
a specialized package that includes platform-specific implementation code for
Android and/or iOS.

For help getting started with Flutter, view our 
[online documentation](https://flutter.io/docs), which offers tutorials, 
samples, guidance on mobile development, and a full API reference.
