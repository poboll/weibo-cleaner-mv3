# 眼不见心不烦（新浪微博）MV3 移植版

<div align="center">

<img src="docs/social-preview.png" alt="眼不见心不烦 MV3" width="640">

**让经典的微博过滤扩展在 Manifest V3 时代继续活下去**

[![Version](https://img.shields.io/badge/version-2.6.1--mv3-f58220.svg)](#-变更说明)
[![Manifest V3](https://img.shields.io/badge/Manifest-V3-4285f4.svg)](https://developer.chrome.com/docs/extensions/develop/migrate)
[![License: MPL-2.0](https://img.shields.io/badge/License-MPL--2.0-18a058.svg)](LICENSE)
[![Upstream](https://img.shields.io/badge/上游-tiansh%2Fyawf-9a9ca3.svg)](https://github.com/tiansh/yawf)

[下载](../../releases/latest) · [安装教程](#-安装) · [变更说明](#-变更说明) · [在线主页](https://poboll.github.io/weibo-cleaner-mv3/)

</div>

---

## 📖 背景

「眼不见心不烦（新浪微博）」是田生（[@tiansh](https://github.com/tiansh)）开发的经典微博过滤与版面改造扩展：屏蔽关键词、屏蔽用户、过滤广告与推广、改造版面……曾是微博重度用户离不开的深度净化工具。

随着 Chrome 淘汰 Manifest V2，Chrome 139 起豁免策略被移除、Chromium 154 起 MV2 运行时代码被整体删除，**商店版扩展在新内核浏览器（包括 Arc）中被强制停用**，而商店里的包也已在 2026-08-31 的 MV2 清理中下架。

本仓库将商店版 **2.6.1** 的代码以 **Manifest V3** 标准重新打包，使其在新内核浏览器中原样复活。

> ⚠️ 本项目与原作者无隶属关系。所有过滤逻辑代码版权归原作者所有，依 **MPL-2.0** 许可发布；本仓库的变更仅限打包清单（见[变更说明](#-变更说明)）。

## ✨ 它能做什么

- **屏蔽**：关键词、用户、来源、包含链接的微博，正则匹配
- **净化**：隐藏广告、推荐、热门话题等版面元素
- **改造**：版面布局调整、阅读体验优化
- 所有规则在扩展设置页可视化配置，规则可导入导出

> 功能以原版 2.6.1 为准，本仓库不新增、不修改任何过滤逻辑。

## 📥 安装

1. 前往 [Releases](../../releases/latest) 下载 `weibo-cleaner-mv3.zip` 并解压到**长期保留**的目录；
2. 打开扩展管理页（地址栏输入 `chrome://extensions`）；
3. 打开右上角 **开发者模式**；
4. 点击 **加载已解压的扩展程序**，选择解压出的文件夹；
5. 打开微博（weibo.com），右键 → 扩展设置，开始配置你的过滤规则。

### 从旧版迁移

如果你此前安装过商店版并配置了过滤规则：本移植版通过保留原始扩展签名的方式使用**与商店版相同的扩展 ID**，`chrome.storage` 中的规则会自动延续，无需重新配置。

## 📝 变更说明

依 MPL-2.0 第 3 条要求，声明本仓库对原始文件的全部变更：

| 文件 | 变更 |
|---|---|
| `manifest.json` | **整体重写**：`manifest_version` 2 → 3；移除已被 MV3 移除的清单字段；`content_scripts` 保持原匹配域并新增 `https://s.weibo.com/*`（搜索页）；`run_at` 设为 `document_start`；为保留用户设置追加原始扩展公钥（`key`） |
| `weiboCleaner.js` | **零修改**，与商店版 2.6.1 一致 |
| 其余 | 新增本 README、LICENSE、文档页等仓库周边文件 |

## 🧭 上游现状与替代方案

- 上游仓库 [tiansh/yawf](https://github.com/tiansh/yawf)（883+ Stars）目前 `yyawf` 分支是一次 "Under construction" 的重写（v0.0.11），商店版 2.6.1 仍是最后的完整发布；
- **推荐并行方案**：将官方用户脚本 [yyawf.user.js](https://github.com/tiansh/yawf) 安装到 [篡改猴](https://www.tampermonkey.net/) / [脚本猫](https://scriptcat.org/) 中使用——用户脚本不受 Manifest V2 淘汰影响，且便于跟随上游更新；
- 本仓库适合希望「装上就生效、沿用旧规则」的扩展党。

## ❓ 常见问题

<details>
<summary>微博改版导致部分功能失效怎么办？</summary>

本仓库不修改过滤逻辑，功能层面与 2020 年的 2.6.1 一致；微博近年 DOM 变化可能使部分版面改造项失效，过滤类功能通常仍然可用。欢迎报告现象，但修复依赖上游。
</details>

<details>
<summary>Firefox 用户怎么办？</summary>

Firefox 至今完整支持 Manifest V2，直接寻找旧版安装即可；或同样使用篡改猴 + 官方用户脚本。
</details>

<details>
<summary>为什么用「加载已解压」而不是打包 crx？</summary>

未上架商店的 crx 会被浏览器拒绝安装；开发者模式加载是当前唯一无门槛方式。缺点是每次浏览器更新后若扩展被停用，需回到扩展管理页确认开关。
</details>

## 🙏 致谢

- **田生（[@tiansh](https://github.com/tiansh)）** 与 [tiansh/yawf](https://github.com/tiansh/yawf) 社区 —— 一切过滤逻辑的创造者
- 本仓库的 MV3 清单改造由 [poboll](https://github.com/poboll) 完成

## 📄 许可证

- `weiboCleaner.js` 及其衍生：[MPL-2.0](LICENSE)，Copyright © 田生（tiansh）
- 本仓库新增的打包文件与文档：同以 [MPL-2.0](LICENSE) 发布以保持一致
