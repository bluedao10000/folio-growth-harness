# Folio 国内产品知识库 v0.1

核验日期：2026-11-15（UTC）。Dot（Growth Manager） 独立研究，经 Codex 整理为公开安全版本。删除不影响增长判断的部署配置、内部标识及运行细节；不保存原始响应或用户资料。

## 证据范围

源码固定为 [cn 的 0d0ea46afb252c8cfcbcb9f27ed128ed070a3536](https://github.com/bluedao10000/resume/commit/0d0ea46afb252c8cfcbcb9f27ed128ed070a3536)。这不证明生产部署了同一版本。研究者只用 HTTPS GET 读取公开首页、公开配置和发现文件；未登录、生成、支付、导出或验证跨设备体验，未做中国大陆网络实测，未运行产品测试。以下线上观察是研究报告记录，不是登录后端到端验收。

## 定位与工作流

事实（源码与首页说明）：Folio 是中文、Chat-first 的简历修改与岗位定制工具；导入已有简历或粘贴真实经历 → 提供 JD → 基于已有事实调整表达与顺序 → 核对 → 输出独立岗位版本。不是自动投递或 ATS 评分服务。来源：[README](https://github.com/bluedao10000/resume/blob/0d0ea46afb252c8cfcbcb9f27ed128ed070a3536/README.md)、[产品公开说明](https://github.com/bluedao10000/resume/blob/0d0ea46afb252c8cfcbcb9f27ed128ed070a3536/public/llms.txt)、[首页](https://www.codeiy.com/)。

建议定位：“保留原稿，用真实经历生成适合目标岗位的投递版本”。假设：同一经历生成多个岗位版本具有复用价值；暂无用户研究、转化或留存数据证明。

## 能力与限制

| 能力 | 源码／文档可见能力 | 不应承诺 |
| --- | --- | --- |
| 修改与版本 | 普通修改更新当前版本；岗位定制新增版本、保留原稿 | 每轮快照、完整历史和任意回滚 |
| 简历库 | 当前浏览器按身份分区保存 | 云端同步、清理浏览器后仍可恢复 |
| 导入 | PDF、DOCX、TXT、Markdown、Folio JSON；本地提取后核对 | OCR、旧 DOC 直接导入、原版式复刻 |
| AI 约束 | 要求不虚构经历、数字、学历和技能；缺事实需补充 | 模型永不幻觉、无需人工核对 |
| 排版和导出 | 四套模板、局部排版、浏览器 A4 打印 PDF、JSON 备份 | 服务端 PDF、移动打印完全一致、JSON 包含完整聊天 |
| 删除保护 | 确认与有限的一次撤销 | 无限撤销或永久恢复 |
| 示例 | 明确虚构的确定性演示 | 真实成功案例或真实 AI 效果 |

来源：[README](https://github.com/bluedao10000/resume/blob/0d0ea46afb252c8cfcbcb9f27ed128ed070a3536/README.md)、[导入架构](https://github.com/bluedao10000/resume/blob/0d0ea46afb252c8cfcbcb9f27ed128ed070a3536/docs/architecture/document-import.md)。这些是实现／说明核验，不是本轮生产测试。线上公开配置对导入设有限制，不宜宣传“无限制导入”；具体界限应以使用时界面为准。

## 数据保存与信任

事实：简历与完整聊天主要在当前浏览器保存；AI 请求会把必要内容发往服务端及模型服务，服务端也可能保存请求处理记录或结果。本地删除不等于服务端同步删除。本地文件解析不代表所有内容永不离开设备。来源：[README](https://github.com/bluedao10000/resume/blob/0d0ea46afb252c8cfcbcb9f27ed128ed070a3536/README.md)、[首页](https://www.codeiy.com/)。

建议：对外说明这一差别，使用虚构案例演示；真实请求前去掉不必要个人资料，提示备份。服务端保留期限、删除请求、供应商数据处理与合规状态尚待核验，不得称“已符合”某法规。

## 国内登录和支付

源码存在国内登录及支付支持；2026-11-15 的[公开配置](https://www.codeiy.com/api/config)声明国内 live 模式，邮箱和 GitHub 方式有配置，国内市场登录方式未启用。研究者结合[认证实现](https://github.com/bluedao10000/resume/blob/0d0ea46afb252c8cfcbcb9f27ed128ed070a3536/src/server/auth.ts)判断微信登录当前未启用。此为配置观察，非登录实测，也不证明支付可用。

套餐价格与支付开放状态须以登录后界面及另行验收为准；本报告不作销售承诺。额度消耗不等于固定简历份数，国内文档描述一次性 30 天额度购买，不应写成自动续订。来源：[计费说明](https://github.com/bluedao10000/resume/blob/0d0ea46afb252c8cfcbcb9f27ed128ed070a3536/docs/product/billing.md)。

## 发现性观察

线上[首页](https://www.codeiy.com/)含中文元信息、canonical、社交分享信息和结构化数据；这不代表已获得索引或富结果。[sitemap](https://www.codeiy.com/sitemap.xml)本次仅包含首页，[llms.txt](https://www.codeiy.com/llms.txt)可读取且描述边界。

研究记录的关键差异：[源码 robots](https://github.com/bluedao10000/resume/blob/0d0ea46afb252c8cfcbcb9f27ed128ed070a3536/public/robots.txt)只禁止 API 路径，但[线上 robots](https://www.codeiy.com/robots.txt)增加托管规则，对 Baiduspider、PetalBot、KimiBot、Bytespider 等特定爬虫设置禁止。通配允许不能抵消特定规则。该观察提示国内可发现性风险，不证明所有搜索引擎都无法收录。

建议：所有者先分别决定搜索索引、AI 搜索引用与模型训练的许可意图，再评估规则调整。不得为增长默认放开全部爬虫；本轮未修改任何设置。没有搜索平台、抓取日志或真实曝光数据，llms.txt 也不保证收录或引用。

## 可用主张与待验证事项

候选主张：基于已有经历和 JD、独立岗位版本、保留原稿、浏览器 PDF 打印、模板及事实缺口提示。必须经 G1 审核后才能对外使用。

禁用主张：保证通过 ATS、录用率提升百分比、绝不幻觉、云端同步、所有数据不出设备、无限免费、微信登录已开通、支付已验证、移动打印完全一致。

建议下一轮使用虚构资料验收导入 → 两个 JD → 两份岗位版本且原稿保留 → 核对事实 → PDF/JSON 输出。真实登录、支付、对外研究各需单独批准。本轮未执行。大陆性能、移动体验、AI 输出质量、真实转化留存和支付仍未知，见[决策清单](../reports/decisions.md)。动态线上来源需在使用前复核。
