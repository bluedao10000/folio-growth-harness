# 报告与持久任务入口

- [产品知识研究](../knowledge/folio-product-knowledge.md)：固定源码与有限公开观察，已完成。
- [产品基线复核](../knowledge/product-baseline.md)：双域名公开面对照；国内目标已确认 codeiy.com。
- [市场审计](folio-growth-audit.md)：公开来源与假设，已完成；增长结果未验证。
- [决策清单](decisions.md)、[周报模板](weekly-template.md)、[验收记录](validation.md)。

研究集成状态已合并到本索引，不另维护 research-status。两份研究已集成，参与者、生产端到端和真实增长未验证。每日／每周任务已计划，尚无运行结果。

## FGH-001 · PR #1 评审修订任务卡

- 稳定 ID：FGH-001；创建／决策 owner：Dot（Growth Manager）；executor：Cloud Codex；独立 reviewer／文档 merger：本地 Technical Lead。
- 状态：进行中（in progress）；文档修订已准备，最终技术验收与独立跨会话恢复未验证。
- 范围：响应正式评审的六条意见；统一角色、恢复任务、验收、E02 规则、事件现状、证据等级，确认国内目标并记录本地 QA 局限。仅 Harness 文档；不改产品、生产、价格，不联系或收集参与者。
- 决策：[D04、D07、D10、D11](decisions.md)。
- 基线 head：`29522513c0411ee9349a3be34bfe725aa1bee866`；目标分支 `docs/folio-growth-harness-v1`；[PR #1](https://github.com/bluedao10000/folio-growth-harness/pull/1)。最终修订 SHA 以 PR head 和线程回报为准；审查者先核对再继续。
- 输入证据：[正式评审与六条 inline comments](https://github.com/bluedao10000/folio-growth-harness/pull/1#pullrequestreview-5911033273)、[产品源码基线](../knowledge/product-baseline.md)、[事件源码证据](../knowledge/metrics.md)。
- 预期与实际映射：[验收记录](validation.md)逐项列出六条修订、QA 错误及失败边界。
- 当前阻塞：E01 未产出实际 PDF；独立新会话恢复及 Technical Lead 复审尚未完成。文档修订无需等待真实模型授权。
- 下一行动：Technical Lead 从本卡独立读取链接，核对 PR 新 head、六项改动与测试范围，在新会话记录恢复和复审结果；Dot 根据其结论决定后续任务。当前 Cloud Codex 只提交修订与线程回复，不 merge／ready／resolve。
- 回滚：文档问题通过后续更正或回退 PR 修复；不 force push，不改 main；没有产品或生产修改可回滚。
- 交接记录 2026-11-15（UTC+8）：Dot 指定规则与范围 → Cloud Codex 读取正式评审并编写此卡、映射与修订 → 等待独立复审。此次仅同会话创建／读取持久卡，未启动另一个新会话，不声称跨会话测试通过。
- 独立复核待填写：审查者、时间、新 head、能否无需聊天恢复范围／下一行动、逐项验收结果、剩余阻塞、合并／不合并结论及合并后验证。禁止用此占位冒充结果。
