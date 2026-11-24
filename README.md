# 四季徽羽 Android App

这是将提供的《四季徽羽_场地费用计算器》HTML 原样作为本地页面封装进 Android WebView 的离线 APP 工程。

## 功能与实现
- UI 和计费逻辑来自 `app/src/main/assets/index.html`，保留上传 HTML 的页面、交互和计算规则。
- Android 原生外壳负责全屏页面承载、状态栏/导航栏颜色和系统返回键。
- 无 `INTERNET` 权限，不依赖服务器或网络。
- 开启 WebView DOM Storage，供 HTML 的 localStorage 在设备本地保存规则。
- 应用 ID：`com.sijihuoyu.app.debug`（Debug APK）。

## 通过 GitHub Actions 构建 APK
1. 将本文件夹中的所有内容上传到 GitHub 仓库根目录（注意 `.github` 隐藏目录也要上传）。
2. 打开 GitHub 仓库的 Actions。
3. 选择 `Build Four Seasons Badminton APK`。
4. 点击 `Run workflow`。
5. 成功后打开本次运行记录，在 Artifacts 下载 `sijihuoyu-android-debug-apk`。
6. 解压得到 `app-debug.apk`，发送到 Android 手机安装。
7. 手机如提示限制，允许当前文件管理器/浏览器“安装未知应用”。

## 构建环境
- JDK 17
- Gradle 8.9（由 GitHub Actions 安装，无需 gradlew）
- Android SDK Platform 35
- Android Build Tools 35.0.0
- Android Gradle Plugin 8.7.3

## 注意
- 这是可侧载安装的 Debug APK，不是 Google Play 发布签名包。
- 本次执行环境没有 Android SDK/Gradle，未在此处直接产出 APK；请使用 GitHub Actions 云端构建。
- APP 运行时完全离线。首次 GitHub 云端构建需要下载 Gradle/Android SDK 依赖。
- 如果需要更新页面，替换 `app/src/main/assets/index.html` 后重新运行 Actions。
