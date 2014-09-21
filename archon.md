# ARChon 定制运行时手册

> ARChon 运行时可以让你在Chrome OS上或者其他支持Chrome浏览器的桌面操作系统运行无限数量通过 `chromeos-apk` 创建的Android应用.

<img src="http://v14d.com/g/WinApk.jpg" width="350px" />
<img src="http://v14d.com/g/multiple.png" width="350px" />

## 说明

**备注: 这个可能在Chrome OS外的操作系统上表现得不稳定**

**警告: 定制运行时会改变官方组建. 要回滚到官方组件你需要卸载定制后的应用, 然后重新安装**

已在OS X, Windows 和 Ubuntu测试. 你必须安装了 Chrome 37+ 的版本. (如果它无法工作请尝试Chrome金丝雀).
[OS X 备注](http://www.reddit.com/r/Android/comments/2gv035/you_can_now_run_android_apps_on_chrome_for/ckmwy13): Grab the latest version of Chrome Canary(此处暂无翻译), Chrome 无法工作因为64位是必须的定制运行时.

- 下载运行时: https://bitbucket.org/vladikoff/archon/get/v1.0.zip
- 以一个正在开发的扩展程序加载.

<img src="http://v14d.com/g/chromeapks/howto.png" width="500px" />
- (尝试这个打包好的开源游戏: [2048-ARChon.APK](https://github.com/vladikoff/chromeos-apk/releases/download/v1.1.0/com.uberspot.a2048.android-ARChon-runtime.zip) by [Uberspot](https://github.com/uberspot/2048-android) 然后以“正在开发的扩展程序”方式加载它. 点击 "运行", 无视错误.)
- 为了运行自定义程序, 请确认你拥有 `chromeos-apk@2.0.0` 或者更高版本的. (通过 `npm install -g chromeos-apk@latest` 来升级). 请阅读 [README.md](README.md) 来得到更多关于 `chromeos-apk` 工具的帮助.
- 创建你的自定义应用通过ARChon参数: `chromeos-apk com.imdb.mobile.apk --archon`.
这样就会为你创建一个自定义目录.
- 在任何你选择的平台上加载你想要的APK以正在开发的扩展程序.


## 备注

### 通过 `chromeos-apk` 工具来转换旧版本APK到 ARChon 运行时.

- 从 `manifest.json` 里面移除 `"key"` 字段 .

### 卸载 ARChon

- 从 `chrome://extensions` 移除. 在Chrome OS上重新安装官方应用来获得官方运行时(例如Evernote).

### ARChon 源码

ARChon 的源码托管在这: https://bitbucket.org/vladikoff/archon/src. 之所以放在 BitBucket 是因为 GitHub 有单个文件大小 100mb 限制. 无限制地研究并调教 ARChon 吧. 

### 改变应用的分辨率

在运行时的两处进行调整: 你需要在这两处调整平板分辨率: https://bitbucket.org/vladikoff/archon/src/master/gen_main.min.js and
https://bitbucket.org/vladikoff/archon/src/master/gen_index.min.js

需找 `tablet: {"long": 1280, "short": 800}`, 调整它, 适配你的分辨率, 然后重新加载运行时. 

### 调教应用们

在`manifest.json`中增加 `"resize": "scale"` 到字段`"arc_metadata"` .

请阅读 [清单指南](manifest.md) 以更高端的手段调教应用.

