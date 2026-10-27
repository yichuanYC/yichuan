<div align="center">
  <img src="docs/logo.png" width="96" alt="易川">
</div>

<h1 align="center">易川</h1>

<p align="center"><strong>手机上的本地音频解密转换工具，外加一套日常小工具</strong></p>

<p align="center">
  <img src="https://img.shields.io/badge/version-0.1.30-3B82F6?style=flat-square" alt="version">
  <img src="https://img.shields.io/badge/Android-10%2B-3DDC84?style=flat-square&logo=android&logoColor=white" alt="Android 10+">
  <img src="https://img.shields.io/badge/size-17.1%20MB-6B7280?style=flat-square" alt="size">
</p>
<p align="center">
  <img src="https://img.shields.io/badge/Kotlin-Compose-7F52FF?style=flat-square&logo=kotlin&logoColor=white" alt="Kotlin + Compose">
  <img src="https://img.shields.io/badge/%E5%8C%85%E5%90%8D-io.github.yichuanyc.yichuan-2496ED?style=flat-square" alt="package">
</p>

<p align="center">
  <a href="../../releases/latest"><strong>下载 APK</strong></a> ·
  <a href="#它是什么">它是什么</a> ·
  <a href="#怎么装">怎么装</a> ·
  <a href="#怎么用">怎么用</a> ·
  <a href="#应用内更新">应用内更新</a> ·
  <a href="#版本记录">版本记录</a> ·
  <a href="#签名">签名</a>
</p>

## 它是什么

易川是一个在本机完成全部工作的音频解密转换工具，同时内置 29 件常用小工具、一个本地播放器与一套主题系统。

- 能读的加密文件：KGM / KGMA、NCM、QMC v1、KWM，覆盖酷狗、网易云、QQ 音乐、酷我四家
- 认得的真实容器：FLAC、MP3、WAV、OGG、M4A、AAC、APE、WMA 共 8 种，按文件实际内容决定后缀，不靠猜
- 转换全程在本机进行，不上传文件，音质不做二次压缩
- 产物统一写到 `下载/易川/`，同名文件自动改名，不覆盖已有文件
- 四家音乐应用的目录状态在首页逐条列出：能读、没有权限、目录不存在，一目了然

## 怎么装

1. 到 [Releases](../../releases/latest) 下载 `yichuan-<版本>.apk`，点开安装
2. 首次启动按引导授予两项权限：**所有文件访问**（扫描四家音乐应用目录）与**音乐和音频**（读取文件）
3. 系统要求：Android 10（API 29）及以上

> 0.1.18 起包名由 `com.example.shareapp` 改为 `io.github.yichuanyc.yichuan`。两者是不同的应用，装过 0.1.17 及更早版本的设备需先卸载再安装；旧安装包已全部下线，历史说明见 [CHANGELOG.md](CHANGELOG.md)。

## 怎么用

1. 打开首页，等扫描结束：待转换一栏会列出四家目录里可解密的文件
2. 点某一条的「转换」，或「全部转换」排队处理；进度与结果写在卡片里
3. 产物出现在已转换一栏，点 ▶ 直接播放，点条目进入播放页（支持后台播放与锁屏控制）
4. 两栏默认只显示三行，内容多时点标题右侧的角标展开
5. 想用别的应用播放或管理文件：设置 → 存储与缓存 → 「打开」，列出全部产物，点一条交系统播放器打开

## 应用内更新

入口：设置 → 关于易川 → 软件更新。

- 从本仓库的 latest release 检查版本，按 `versionCode` 数字段比较
- 支持跨版本升级：只比较 latest 与本机，中间隔几个版本都能一步升到最新
- 下载走前台服务，多连接分段下载（线程数可在软件更新页设 2/4/8/12/16，默认 8），支持断点续传与自动重试
- 下载源可选三档：直连优先 / 加速优先（自建反向代理）/ 镜像优先（公共镜像，需确认一次）
- 安装前校验包名、`versionCode` 与**签名证书 SHA-256**，任一不符直接拒绝
- 只拉起系统安装器，不做静默安装；应用内不内置任何 token

## 版本记录

`versionCode` 必须严格递增，否则系统会拒绝安装。资产文件名统一为 `yichuan-<versionName>.apk`。

| tag | versionName | versionCode | 说明 |
|---|---|---|---|
| `v0.1.18` | 0.1.18 | 19 | 新包名的第一个对外版本 |
| `v0.1.19` | 0.1.19 | 20 | 修复批次（体检 20 处）；最低系统改为 Android 10 |
| `v0.1.20` | 0.1.20 | 21 | 可读性批次：界面不再出现异常类名与内部状态码 |
| `v0.1.21` | 0.1.21 | 22 | 后台播放与状态栏媒体卡片：切页切后台不断，锁屏可控 |
| `v0.1.22` | 0.1.22 | 23 | 修切歌进播放页闪退；播放控制三档；通知渠道提级 |
| `v0.1.23` | 0.1.23 | 24 | 播放内核换成 Media3：后台播放更稳，媒体卡片跟随系统 |
| `v0.1.24` | 0.1.24 | 25 | 播放回到系统内核：96/192 kHz 与多声道能放；修卡顿与音调问题 |
| `v0.1.25` | 0.1.25 | 26 | 引导页加「初始设置」；首页列出四家目录状态 |
| `v0.1.26` | 0.1.26 | 27 | 全应用文案统一为精简书面语 |
| `v0.1.27` | 0.1.27 | 28 | 引导页视觉重做并跟随主题；应用图标默认浅色 |
| `v0.1.28` | 0.1.28 | 29 | 修媒体卡片图标、权限死按钮、来电续播等 8 项 |
| `v0.1.29` | 0.1.29 | 30 | 加载态统一环形进度与骨架屏；修预测性返回顿挫 |
| `v0.1.30` | 0.1.30 | 31 | 首页两栏可折叠；存储页可直接打开转换产物 |

旧的 `v0.1.1` – `v0.1.17`（versionCode 2–18）使用旧包名，已下线。

## 签名

发布包使用固定证书签名，SHA-256 指纹：

```
F7:E2:44:59:7E:00:15:CD:DA:1C:F2:A0:71:2C:57:FC:03:E9:36:73:0B:2B:3A:F6:1E:93:11:75:B4:80:10:20
```

签名变更意味着已安装用户无法覆盖升级，因此该证书长期不变。

## 关于本仓库

- 本仓库只存放发布产物（APK）与更新说明，**不含源码**
- 每个版本的完整说明见对应 Release；0.1.24 及更早的详情保留在 [CHANGELOG.md](CHANGELOG.md)
- 更新日志按分类条目书写：新增 / 改进 / 修复 / 注意，无内容的分类整节省略，单条一句话、句末不加句号，只写用户可感知的变化
