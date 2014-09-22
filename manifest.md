# `manifest.json` 配置项

## `arc_metadata`

() 输入时请勿输入括号及括号中的中文翻译

true代表 真(启用), false 代表 假(禁用)

在源文件中 `arc_metadata` 的配置项:

```
"arc_metadata": {
  allowEmptyActivityStack(允许空的Activity栈): false,
  apkList(apk程序列表): [
    "custom-android-release-1400197.apk"
  ], 
  canRotate(允许旋转): false,
  disableAutoBackButton(禁用自动返回键): false,
  enableAdb(启用Adb): false,
  enableArcStrace(启用ArcStrace？): false,
  enableExternalDirectory(启用外置SD卡目录): false,
  enableGlErrorCheck(启用GL错误检查): false,
  formFactor(显示模式 phone为手机 tablet为平板): "phone",
  fpsLimit(帧数限制): 60,
  isSlowDebugRun(慢速调试运行): false,
  jdbPort(jdb调试端口): 0,
  logLoadProgress(log加载): false,
  minimumLaunchDelay(最低启动延迟): 0,
  name(名字,作用不详): "",
  ndkAbi(貌似和ndk有关,作用不详): "",
  orientation(屏幕方向 landscape是横屏 portrait是竖屏): "portrait",
  packageName(包名,重要!): "org.chromium.arc",
  resize(重新调整大小): "disabled",
  shell(启动后运行的命令??): [],
  stderrLog(日志标准): "S",
  useGoogleContactsSyncAdapter(启用Google联系人同步接口): false,
  usePlayServices(使用Google Play服务): [
   "gcm"
  ],
  sleepOnBlur(睡眠模糊): true
}
```
