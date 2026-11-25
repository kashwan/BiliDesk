<div align="center">

<img src="docs/logo_rounded.png" width="104" alt="BiliDesk 图标">

# BiliDesk

**干净、流畅的哔哩哔哩第三方 Windows 桌面客户端**

*WPF · .NET 10 · libmpv*

<br>

[![Release](https://img.shields.io/github/v/release/kashwan/BiliDesk?style=flat-square)](https://github.com/kashwan/BiliDesk/releases/latest)
[![Platform](https://img.shields.io/badge/Windows-10%2B-0078D4?logo=windows11&logoColor=white&style=flat-square)](#-下载安装)
[![.NET](https://img.shields.io/badge/.NET-10.0-512BD4?logo=dotnet&logoColor=white&style=flat-square)](#-从源码构建)
[![License](https://img.shields.io/github/license/kashwan/BiliDesk?style=flat-square)](LICENSE)

[下载](https://github.com/kashwan/BiliDesk/releases/latest) · [功能特性](#-功能特性) · [快捷键](#-快捷键) · [从源码构建](#-从源码构建)

<br>

<img width="100%" alt="BiliDesk 首页" src="docs/screenshot-home-rounded.png">

</div>

> [!IMPORTANT]
> 本项目为非官方、非商业的开源软件，与哔哩哔哩官方无任何关联；视频内容与版权归哔哩哔哩及各 UP 主所有。

> [!NOTE]
> 本项目是 [`kashwan/BiliDesk`](https://github.com/kashwan/BiliDesk) 的 `restructure-mpv-core` 独立发行线：已移除 VLC，只保留 mpv 播放内核；源码目录在仓库根目录，不使用原仓库 `main` 的嵌套结构。

## 🔀 仓库关系与维护方式

- 上游基线：[`ABING1111/BiliDesk`](https://github.com/ABING1111/BiliDesk) 的 `main`；仅选择性 cherry-pick 与 mpv 分支无关的修复，不整支合并。
- 技术来源：[`ABING1111/BiliDesk#117`](https://github.com/ABING1111/BiliDesk/pull/117)（`YuiYuK1:feat/mpv-core`）。该 PR 仍是 Draft，本发行线在其基础上重构并继续独立维护。
- 本仓库默认分支与唯一源码/发布分支都是 `restructure-mpv-core`；GitHub Actions 的 `workflow_dispatch` 入口也从该默认分支读取。
- `main` 保留为历史/CI 过渡分支，不再用于源码发布。
- 上游旧版本 tag/Release 仅作历史记录；当前安装包只从本发行线产生。

## ✨ 功能特性

**播放**

- mpv（libmpv）内核，DASH 音视频双流，最高 4K，HEVC 优先选流
- 默认画质可预选（该清晰度不可用时自动降级），线路跟随服务端（默认）或手动指定，免登录 1080P
- 倍速播放：0.25x–4.0x 预设，也可自定义输入任意倍速
- 视频「铺满窗口」与全屏
- 小窗播放：缩成置顶的 16:9 小窗浮在其它窗口之上（适合边打游戏边看攻略），可拖动，<kbd>Esc</kbd> 还原
- 按住鼠标左键 / 长按 <kbd>→</kbd> 进入倍速播放：默认 2x，期间 <kbd>↑</kbd> / <kbd>↓</kbd> 或鼠标滚轮在 1.5x / 2x / 3x 间循环切档，松手恢复原速（鼠标长按固定从 2x 起步，正片已高于 2x 时会先降速）
- 听视频模式，把 B 站当播客用
- 短视频本地合流：≤ 1 分钟的视频自动下载 1080P 后合流为 MP4 缓存播放
- 视频下载：可选清晰度（最高 8K，DASH 双流无损合流，不再受 720P 限制），下载前显示保存位置并可更改
- SponsorBlock 跳过赞助片段（默认关闭，需手动开启）

**弹幕**

- 滚动 / 顶部 / 底部全类型渲染
- 智能屏蔽、彩色开关、显示区域调节
- 外观可调：不透明度 / 字号 / 速度
- 半透明圆角胶囊底衬（默认开启，压在明亮画面上也能看清；可一键关掉恢复纯文字）
- 直播间弹幕实时接收（WebSocket，与点播共用外观 / 过滤设置）
- 直播间右侧弹幕列表（胶囊气泡 + 粉丝团 / 房管身份徽章）+ 清晰度切换（杜比 / 4K / 原画 / 蓝光 / 超清 / 高清 / 流畅）
- 直播间主播信息：头像 / 昵称（可进主页）/ 已开播时长 / 看过人数 / 分区

**浏览**

- 扫码登录，历史 / 收藏 / 稍后再看 / 动态 / 消息
- 首页推荐 / 热门 / 排行榜 / 直播 / 追番，分区浏览与搜索；动态页可按关键词筛选本页动态（标题 / 正文 / UP 名）

**个性化**

- 亮色 / 暗色 / 跟随系统三态主题，主题色可自定义
- 界面字体可自定义：系统字体任选（逐项预览），也可导入 .ttf / .otf / .ttc 字体文件，弹幕跟随同一字体
- 亚克力 / 云母窗口材质
- 托盘常驻；自动检查更新默认关闭，可在设置中开启

## ⌨️ 快捷键

| 按键 | 功能 |
| :---: | :--- |
| <kbd>Space</kbd> | 播放 / 暂停 |
| <kbd>←</kbd> <kbd>→</kbd> | 快退 / 快进 5 秒（按住 <kbd>Shift</kbd> 为 30 秒；长按 <kbd>→</kbd> 为倍速播放，默认 2x） |
| <kbd>↑</kbd> <kbd>↓</kbd> | 音量增减（长按倍速期间改为切换 1.5x / 2x / 3x） |
| <kbd>滚轮</kbd> | 音量增减（长按倍速期间改为切换 1.5x / 2x / 3x） |
| <kbd>M</kbd> | 静音切换 |
| <kbd>F</kbd> | 全屏 |
| <kbd>D</kbd> | 弹幕开关 |
| <kbd>L</kbd> | 点赞 |
| 长按点赞 | 一键三连（点赞 + 投币 2 枚 + 收藏到默认收藏夹） |
| <kbd>U</kbd> | 打开 UP 主主页 |
| <kbd>Esc</kbd> | 逐级返回（全屏 → 小窗 → 铺满窗口 → 关闭） |
| <kbd>中键</kbd> | 全局自动滚动：任意可滚动区域点按/按住进入，偏离锚点越远越快；再点一次退出 |
| <kbd>右键</kbd> | 播放器视频区：铺满窗口 / 收起右侧详情栏（再点还原） |
| <kbd>F5</kbd> | 刷新当前页面（首页 / 动态 / 分区 / 我的 / 历史 / 收藏 / 稍后再看 / 缓存 / 消息） |

## 📥 下载安装

前往 [**Releases**](https://github.com/kashwan/BiliDesk/releases/latest) 获取该分支的 mpv-core 测试包：

| 发行包 | 说明 |
| :--- | :--- |
| **便携版 zip** | 自包含，解压即用，无需安装 .NET 运行时 |
| **安装器** | 需要 .NET 10 或更高版本的桌面运行时（安装器会自动检测并引导下载；只装了 .NET 11 也可以直接用） |

## 🧰 从源码构建

需要 Windows 10+ 与 [.NET 10 SDK](https://dotnet.microsoft.com/download/dotnet/10.0)（x64）。

```powershell
git clone --branch restructure-mpv-core https://github.com/kashwan/BiliDesk.git
cd BiliDesk
dotnet build BiliDesk.csproj -c Release
```

libmpv 原生库**不进仓库**（约 122MB），需要自行下载并放到固定位置：

1. 从 [shinchiro 的 mpv Windows 构建](https://sourceforge.net/projects/mpv-player-windows/files/) 下载
   `mpv-dev-x86_64-v3-*.7z`（**x86-64-v3 / AVX2 版**，需要 CPU 支持 AVX2）；
2. 解压出其中的 `libmpv-2.dll`；
3. 放到下面这个路径（目录不存在就新建）：

   ```text
   libmpv/win-x64/libmpv-2.dll
   ```

构建时会自动复制到输出目录；文件缺失时工程仍可构建，只是播放内核不可用。

> 本地源码构建按 [`docs/libmpv-build.md`](docs/libmpv-build.md) 记录的参考版本放置 DLL；
> 发布工作流每次构建都会从 shinchiro 的最新 Release 解析 `mpv-dev-x86_64-v3-*.7z`，
> 用 GitHub 提供的 digest 校验归档，并把实际 DLL SHA-256 写入发布脚本再校验一次。
> 该 DLL 已被 `.gitignore` 排除，不会进入提交。

完整发布（便携版 zip + Inno 安装器载荷）运行仓库根目录的 `发布.ps1`。

## ⚖️ 许可

本项目基于 [GPL-3.0](LICENSE) 协议开源。
