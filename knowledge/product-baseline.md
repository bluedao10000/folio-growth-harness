# 产品证据基线

核验日期：2026-11-15。只读来源：[cn 分支](https://github.com/bluedao10000/resume/tree/cn)，本次固定提交：[0d0ea46afb252c8cfcbcb9f27ed128ed070a3536](https://github.com/bluedao10000/resume/commit/0d0ea46afb252c8cfcbcb9f27ed128ed070a3536)。分支之后可能变化，不能自动沿用本报告。

| 结论 | 类型和出处 | 限制 |
| --- | --- | --- |
| 对话整理、版本管理、岗位定制是产品定位 | 文档事实：[README](https://github.com/bluedao10000/resume/blob/0d0ea46afb252c8cfcbcb9f27ed128ed070a3536/README.md) | 产品描述，不代表用户已获得效果 |
| 文档声明支持本地导入、核对、模板及打印／导出 | 文档声明：同上 | 尚未逐项生产验收；不承诺原版式保真或 OCR |
| 文档要求不虚构经历、成绩、资格和 ATS 分数 | 约束：[AGENTS](https://github.com/bluedao10000/resume/blob/0d0ea46afb252c8cfcbcb9f27ed128ed070a3536/AGENTS.md) | 约束存在不证明所有输出正确 |
| 简历和完整对话以浏览器本地保存为主，无云端简历／聊天同步承诺 | 文档声明：README、AGENTS | 不能宣传所有数据从不离开浏览器；live 模型处理仍涉及发送输入 |
| 国内登录和支付存在配置说明 | 文档声明：README | 不证明线上登录、付费及完整闭环成功；混合市场描述需逐项核实 |

本页未登录生产站、未支付、未上传真实简历、未验收模型结果。公开宣传前通过 G1；独立产品研究与市场审计集成状态见 [报告目录](../reports/README.md)。

## 公开面复核：两个域名不能混用

观察时间：2026-11-15 21:47–21:50（UTC+8）。Dot（Growth Manager） 使用未登录 HTTPS GET 和浏览器查看；无注册、上传、AI、支付或生产修改。普通页面请求可能被站点现有匿名访问分析记录。以下与本地 mock 验收完全分开。

| 检查 | 历史指定／对照 r.story2u.xyz | 已确认国内目标 www.codeiy.com |
| --- | --- | --- |
| 首页响应 | HTTP 200，无跨域跳转 | HTTP 200，无跨域跳转 |
| canonical / OG | 指向自身 | 指向自身 |
| 公开运行模式 | live；market 字段缺失 | live；market=cn |
| 登录公开入口 | Google 说明，水合后按钮启用 | GitHub 和折叠邮箱验证码；微信未显示／配置 |
| sitemap | 仅自身首页 | 仅自身首页 |
| 爬虫策略 | 通用允许，API 禁止 | 额外托管规则禁止 Baiduspider、PetalBot、KimiBot 等 |

来源：[r 首页](https://r.story2u.xyz/)、[r 配置](https://r.story2u.xyz/api/config)、[r sitemap](https://r.story2u.xyz/sitemap.xml)、[r robots](https://r.story2u.xyz/robots.txt)、[codeiy 首页](https://www.codeiy.com/)、[codeiy 配置](https://www.codeiy.com/api/config)、[codeiy sitemap](https://www.codeiy.com/sitemap.xml)、[codeiy robots](https://www.codeiy.com/robots.txt)。

已完成：两个公开界面独立响应、自 canonical，并非已证实的别名／跳转。两边中文定位接近；实际搜索重复内容选择或排名影响未验证。源码 cn 与任何线上部署 SHA 的对应关系未验证。后续所有者明确“以 codeiy.com 为准”，国内增长和生产验收目标已确定；r 仅作为独立历史对照。此决定不改变两边既有路由或登录配置。

两边公开页面标注虚构、非实时演示；显示一个设计系统岗位的优先级调整与缺口，提到另一研究岗位，但不是实际可执行的“两岗位已验证”证据。FAQ 描述版本、原稿、人工核对、浏览器 PDF、本地存储与模型处理。r 的 SSR 按钮起初 disabled，水合后启用，不是持续不可点击缺陷。

两边结构化数据的免费 offer 标记 USD；是否符合 cn 意图待审核，不把零价币种直接定性为计费 bug。公开额度和价格配置不证明支付币种或成功结算，本次未交易。特定 bot 禁止是实际抓取政策障碍，不是全站失去索引的证明；索引、AI 检索、模型训练应分别决定。

未验证：生产登录、导入、AI 事实保持、两版独立保存、真实 PDF、设备布局、激活转化、留存与收入。Google 入口对国内激活可能有摩擦，但大陆可达性与流失未测。产品验收当前使用本地合成资料，不弥补生产证据。
