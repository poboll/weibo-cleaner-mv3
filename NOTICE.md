# NOTICE / 变更声明

本仓库包含田生（tiansh）开发的「眼不见心不烦（新浪微博）」浏览器扩展商店版 2.6.1 的
Manifest V3 移植。

- 原始作品：https://github.com/tiansh/yawf （用户脚本，MPL-2.0）
           及 Chrome Web Store「眼不见心不烦（新浪微博）」扩展 2.6.1
- 原始许可：MPL-2.0（见用户脚本头部 `@license MPL-2.0` 与本仓库 LICENSE）
- 移植变更：仅重写 `manifest.json` 以符合 Manifest V3
  （清单字段调整、新增 `s.weibo.com` 匹配、`run_at: document_start`、
  保留原扩展公钥以延续用户数据）；`weiboCleaner.js` 未做任何修改。
- 本仓库新增文件（README、文档页、构建说明）亦以 MPL-2.0 发布。

依据 MPL-2.0 第 3 条，本声明与 LICENSE 随源文件一同提供；
MPL 覆盖文件的源代码始终可以在本仓库公开获取。
