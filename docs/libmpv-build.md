# libmpv 构建来源与许可

播放内核使用 shinchiro 的 Windows 构建（x86-64-v3 / AVX2 版）。

| 项 | 值 |
| --- | --- |
| 包名 | `mpv-dev-x86_64-v3-20261111-git-bcde6b93cc` |
| mpv 版本 | `v0.42.0-38-gbcde6b93c` |
| FFmpeg 版本 | `N-128766-gcd4e96eb3` |
| 架构 | x86-64-v3（AVX2 / BMI2 / FMA 等指令集，需 CPU 支持） |
| 运行时文件 | `libmpv-2.dll`（124,694,016 字节） |
| SHA-256 | `fd80c3f48015a6956b8b13c05fa1599a8e3df2d3c76e1d58ee19ccc2cdb56ce4` |
| 本地放置 | `libmpv\win-x64\libmpv-2.dll`（已 gitignore，不入库） |

## 许可

- mpv 本体为 **GPLv2+**；该构建包含 GPL 组件（FFmpeg 等），**不是 LGPL 构建**。
- 本项目（BiliDesk）为 GPLv3，与 GPLv2+ 兼容；分发安装包时需要：
  1. 随包附带 GPLv2 许可证文本；
  2. 提供 mpv / FFmpeg 对应源码的获取方式（上游仓库或构建方源码包）。
- 安装器/发布脚本在打包前应校验上面的 SHA-256。

## 来源

- 构建发布：shinchiro 的 `mpv-dev-x86_64-v3-*`（SourceForge: mpv-player-windows）
- mpv 源码：https://github.com/mpv-player/mpv （commit `bcde6b93cc`）
- FFmpeg 源码：https://ffmpeg.org