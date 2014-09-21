# 对主动转换Apk的指引
> 如果命令行工具 (`chromeos-apk`) 对你的转换不奏效请阅读这篇文章. 

*****


- 得到你要转换的APK文件. 寻找APK的包名 (例如 `com.soundcloud.android`, 你可以在Play Store浏览应用时通过URL地址得到包名). 这个工作没有正确的包名就没法继续下去了.
- 复制一份 [_template](https://github.com/vladikoff/chromeos-apk/tree/master/_template) 目录. 命名 **新目录** 以正确的包名例如 `com.soundcloud.android` .
- 使用新目录, 将APK文件放进 `crx` 目录中, 如: [com.soundcloud.android/vendor/chromium/crx](https://github.com/vladikoff/chromeos-apk/tree/master/_template/vendor/chromium/crx)
- 更新 [manifest.json](https://github.com/vladikoff/chromeos-apk/blob/master/_template/manifest.json#L8) 文件来适配你的APK. 你也可以改变其他配置, 例如 `formFactor`: (`phone`(手机) 或 `tablet`(平板)), `orientation`: (`landscape`(横屏) 或 `portrait`(竖屏)) 为平板应用. 备注: 一些应用可能会因为 `tablet` 或 `portrait` 配置项出错.  
- 现在你就可以在Chrome的扩展程序中以正在开发的扩展程序把目录加载进去了.

## 为 ARChon 运行时

- 从 `manifest.json` 移除 `"key"` 字段. 
