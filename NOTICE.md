# NOTICE / 变更声明

本仓库包含 Chrome Web Store 商店版「眼不见心不烦（新浪微博）」扩展 2.6.1 的
Manifest V3 移植。

**来源与许可链条**

- 过滤逻辑的原始作者：田生（tiansh），https://github.com/tiansh/yawf
  （药方 / YAWF 用户脚本，用户脚本头部与 weibov7 分支 LICENSE 均为 **MPL-2.0**）。
- 商店扩展来源说明：原作者已公开声明**从未发布过浏览器扩展**
  （见 https://github.com/tiansh/yawf/issues/226 ，2026-10-01）。
  商店版扩展是第三方对该脚本衍生代码的打包，打包者未附带许可声明。
  本仓库基于代码来源认定其为 tiansh 用户脚本的 MPL-2.0 衍生作品并依此发布；
  如原作者或权利人提出异议，本仓库将第一时间配合处理或下架。
- 移植变更：仅重写 `manifest.json` 以符合 Manifest V3
  （清单字段调整、新增 `s.weibo.com` 匹配、`run_at: document_start`、
  保留原扩展公钥以延续用户数据）；`weiboCleaner.js` 未做任何修改。
- 本仓库新增文件（README、文档页等）亦以 MPL-2.0 发布。

依据 MPL-2.0 第 3 条，本声明与 LICENSE 随源文件一同提供；
MPL 覆盖文件的源代码始终可以在本仓库公开获取。
