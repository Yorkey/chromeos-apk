chromeos-apk
======================

> 在Chrome OS, OS X, Linux and Windows上运行Android软件.

<img src="http://v14d.com/g/chromeapks/1.png" width="250px" />
<img src="http://v14d.com/g/chromeapks/2.png" width="250px" />
<img src="http://v14d.com/g/chromeapks/3.png" width="250px" />
<img src="http://v14d.com/g/chromeapks/4.png" width="250px" />
<img src="http://v14d.com/g/chromeapks/5.png" width="250px" />
<img src="http://v14d.com/g/chromeapks/6.png" width="250px" />
<img src="http://v14d.com/g/chromeapks/7.png" height="160px" />

### 现在支持 OS X, Linux and Windows

<img src="http://v14d.com/g/multiple.png" width="250px" />
<img src="http://v14d.com/g/WinApk.jpg" width="250px" />
>阅读 [定制ARChon运行时手册](archon.md) 以在除Chrome OS外的其他操作系统中运行Android应用.


### [视频演示](https://www.youtube.com/watch?v=O-yFLqp_sXs)

## Chrome OS 简单演示
- 下载一个官方版应用, [例如 Evernote](https://chrome.google.com/webstore/detail/evernote/dhfolfjkgpeaojbiicgheljefkfbbfkc), from the Chrome Web Store
- 或者下载这个开源软件: [2048.APK Game](https://github.com/vladikoff/chromeos-apk/releases/download/v1.1.0/com.uberspot.a2048.android-OFFICIAL.zip) by [Uberspot](https://github.com/uberspot/2048-android) 然后以“正在开发的扩展程序”方式加载它. 点击 "运行", 无视错误.

## 为 Chrome OS / App 设定转换
> 转换工具已经在 OS X, Windows and Ubuntu测试. 你也可以查看 [主动转换 APKs](manually-convert.md).

- 安装一个 [来自Chrome Store的示例应用程序](https://chrome.google.com/webstore/detail/kids-sight-words/inpoiemibmljfjmjmlokfdllnkjejhai) 来获得运行时. 测试出那个软件确认它能运行在你的硬件上.
- (Ubuntu 可能需要 `sudo apt-get install lib32stdc++6`)
- 安装 Node.js (via http://nodejs.org/)
- 安装工具 (需要添加 `sudo` 前缀):
```
npm install chromeos-apk -g
```
或者

```
sudo npm install chromeos-apk -g
```

## 使用方法

运行
`chromeos-apk [path to apk file]`

### 以手机方式运行

```
chromeos-apk com.soundcloud.android.apk
```

#### 以平板方式运行

```
chromeos-apk com.soundcloud.android.apk --tablet
```

这样就会为你生成一个文件夹, 例如 `com.soundcloud.android`. 复制这个文件夹到你的Chrome Book.
在你的 Chromebook 上跳转到 `chrome://extensions`, 启用 "开发者模式", 然后在 "Load unpacked extension(加载正在开发的扩展程序)" 按钮加载这个文件夹.
<img src="http://v14d.com/g/chromeapks/howto.png" width="500px" />

## 故障排除

为了确认Android应用能够兼容运行在你的 Chromebook, 首先需要安装一个官方应用来测试例如 Vine:
https://chrome.google.com/webstore/detail/vine/plfjlfohfjjpmmifkbcmalnmcebkklkh

如果你得到 `Failed to parse package name in the APK.` 的错误, 则你得为应用程序输入正确的报名. 你可以在Play Store浏览应用时通过URL地址得到报名.

## 备注

**This is a proof of concept. 在正规的运行时你可以马上运行支持Android 4.0或以上(可能是SDK>=15吧,测试发现这个东东自带的SDK貌似是19!!)的应用程序.
 By default the `chromeos-apk` tool replaces the Vine app. Read [the multiple apps manual](multiple-apps.md)
 to load more than one application at a time. To load unlimited number of apps read the [ARChon runtime guide](archon.md)**

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

## 已测试的应用

阅读 [清单手册](manifest.md) 来调教(哦不是调整)应用程序.

- Flipboard - 能工作
- Flixster - 能工作
- Twitter - 在手机和平板模式都工作
- Pandora - 能工作 [[截图](http://i.imgur.com/0d8XvXr.png)]
- Yahoo Screens, 在手机模式下天气和邮件都工作 (可能需要 在 `manifest.json` 从 `usePlayServices` 移除 `gcm`). 
- Soundcloud - 能工作, 播放声音时FC
- Chrome, Firefox, Opera, Spotify - 出错 (需要native(翻译为原生??)库)
- Opera Mini - 能工作, 在使用返回键时出错
- [Gyro Game](https://play.google.com/store/apps/details?id=pl.submachine.gyro&hl=en) - 能工作
- [Break Bricks Game](https://play.google.com/store/apps/details?id=com.tongwei.blockbreaker) - 能工作
- Swing Copters - 在Google Play服务上撞车了
- WhatsApp - 出错
- IMDB - 能工作
- Skype `com.skype.raider` - 能工作, 需要你主动键入包名在 CLI 中, 使用 `com.skype.raider`. 通过 [旧版本的 APK 5.0.0.x](http://www.androiddrawer.com/20511/download-skype-free-im-video-calls-app-apk/) 来使它工作.
- XBMC - 初始化加载后撞车了.
- Microsoft Remote Desktop - 这台车可能需要撞一次它才会听话.  


### 作者(致敬!!)

| [![twitter/vladikoff](https://avatars3.githubusercontent.com/u/128755?s=70)](https://twitter.com/vladikoff "Follow @vladikoff on Twitter") |
|---|
| [@vladikoff](https://twitter.com/vladikoff) |
