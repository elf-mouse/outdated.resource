# Web App 相关

## 桌面图标

### 终极方案

下面是兼容 iOS 4.2+ 及 Android 2.1+ 的通用写法：

```html
<link rel="apple-touch-icon-precomposed" href="/path/to/icon72x72@2x.png">
```

* `rel="apple-touch-icon-precomposed"`：不给 Icon 添加额外的效果；兼容 Android 1.5 - 2.1。
* Icon 尺寸：144px * 144px，兼容 iPhone、iPad 及绝大部分安卓设备。

### iOS

```html
<!-- Add to homescreen for Safari on iOS -->
<!-- 添加至主屏, 从主屏进入会隐藏地址栏和状态栏, 全屏(content="yes") -->
<meta name="apple-mobile-web-app-capable" content="yes">

<!-- 系统顶栏的颜色(content = black、white 和 black-translucent)选其一就可以 -->
<meta name="apple-mobile-web-app-status-bar-style" content="black">
<meta name="apple-mobile-web-app-status-bar-style" content="white">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">

<!-- 指定标题 -->
<meta name="apple-mobile-web-app-title" content="Web Starter Kit">

<!-- 指定icon, 建议PNG格式-->
<link rel="apple-touch-icon" href="touch-icon-iphone.png">
<link rel="apple-touch-icon" sizes="76x76" href="touch-icon-ipad.png">
<link rel="apple-touch-icon" sizes="120x120" href="touch-icon-iphone-retina.png">
<link rel="apple-touch-icon" sizes="152x152" href="touch-icon-ipad-retina.png">

<!--
 使用rel="apple-touch-icon"属性为“增加高光光亮的图标”, 系统会自动为图标添加圆角及高光；
 使用rel="apple-touch-icon-precomposed"属性为“设计原图图标”；
-->
```

尺寸说明：

__机型__ | __iPhone 5 and iPod touch (高分辨率)__ | __iPhone and iPod touch (高分辨率)__ | __iPad and iPad mini (高分辨率)__ | __iPad 2 and iPad mini (标准分辨率)__
-------- | -------------------------------------- | ------------------------------------ | --------------------------------- | -------------------------------------
尺寸 (px) | 120 x 120 | 120 x 120 | 152 x 152 | 76 x 76

__参考链接：__

* [iOS Human Interface Guidelines - Icon and Image Sizes](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/MobileHIG/IconMatrix.html)
* [Everything you always wanted to know about touch icons](http://mathiasbynens.be/notes/touch-icons)
* [Configuring Web Applications](https://developer.apple.com/library/ios/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html)

### Android Chrome

Android 下目前只有 Chrome 31 支持 Add to Homescreen。

```html
<!-- Add to homescreen for Chrome on Android -->
<meta name="mobile-web-app-capable" content="yes">
<link rel="icon" sizes="196x196" href="images/touch/chrome-touch-icon-196x196.png">
```

__参考链接：__

* [Chrome Add to Homescreen](https://developer.chrome.com/multidevice/android/installtohomescreen)

### Win 8

```html
<!-- Tile icon for Win8 (144x144 + tile color) -->
<!-- win 8 磁贴图标 -->
<meta name="msapplication-TileImage" content="images/touch/ms-touch-icon-144x144-precomposed.png">
<!-- win 8 磁贴颜色 -->
<meta name="msapplication-TileColor" content="#3372DF">
```

__参考链接：__

* [Pinned Sites](http://msdn.microsoft.com/en-us/library/ie/hh772707(v=vs.85).aspx)
* [MSDN - Pinned site metadata reference](http://msdn.microsoft.com/zh-cn/library/ie/dn255024(v=vs.85).aspx)
