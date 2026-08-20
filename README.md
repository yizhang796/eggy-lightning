# 蛋仔避闪电（Eggy Lightning）

一个可以直接在浏览器和 Android 手机上游玩的闪电躲避小游戏。

## 游戏玩法

- 操作蛋仔躲避不断落下的闪电。
- 游戏每 10 秒提升一级难度。
- 场上会周期性出现金币，收集后会计入本局和累计金币。
- 默认拥有 1 次护盾充能，也可以在战场上收集护盾补充，最多 3 次。点击护盾按钮或按 `Q`，可展开护盾抵挡一次雷击。
- 点击冲刺按钮或按 `E` / `Shift`，可短时间高速移动并免疫雷击，使用后需要等待冷却。
- 随等级提升，闪电预警时间会缩短，每波闪电数量会增加。
- 后期会出现追踪雷、雷墙封路和连续雷电压迫。
- 支持电脑鼠标/键盘操作和手机触屏操作。

## 在线运行

直接下载仓库后打开 `index.html` 即可游玩，不需要安装依赖或启动后端服务。

也可以通过 GitHub Pages 部署：

1. 进入仓库 `Settings` → `Pages`。
2. 在 `Build and deployment` 中选择 `Deploy from a branch`。
3. 选择 `main` 分支和 `/root` 目录。
4. 保存并等待网站生成。

## Android APK

已构建的测试版 APK 位于：

`releases/EggyLightning-v2.0.0-debug.apk`

应用信息：

- 应用名称：蛋仔避闪电
- 包名：`com.eggy.lightning`
- 版本：`2.0.0`
- 最低 Android 版本：Android 6.0（API 23）
- 当前 APK 使用 Debug 签名，适合安装测试，不适合直接提交应用商店。

## Android 源码

Android WebView 封装工程位于 `android/`，网页游戏会从应用 assets 中离线加载。结束界面采用渐变卡片、数据分栏、最高纪录和快捷重开布局。

构建环境：

- Java 17
- Android SDK 36
- Android Build Tools 36.0.0
- Gradle 9.1.0

## 项目结构

```text
.
├── index.html                         # 网页游戏 v2.0.0
├── android/                           # Android 工程源码
├── releases/
│   └── EggyLightning-v2.0.0-debug.apk # 可安装测试 APK
└── README.md
```

## 说明

游戏资源可离线运行。Android 工程中的 SDK、Gradle 缓存和构建中间文件没有提交到仓库。
