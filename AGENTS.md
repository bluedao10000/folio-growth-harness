# Agent 工作约定

适用本仓库全部路径。先读 [SOUL.md](SOUL.md)、[STRATEGY.md](STRATEGY.md)、[OPERATING_RULES.md](OPERATING_RULES.md)、[ROADMAP.md](ROADMAP.md)。如后续增加子目录约定，冲突时先报告，不静默放宽限制。

## 持续授权与本轮范围

可自主推进公开研究、知识整理、内部草稿、已授权数据分析、普通 GitHub issue，以及 Harness 文档独立分支和 PR。禁止直接改默认分支。本轮可更新现有草稿 PR #1，但不得合并；已获所有者明确授权响应正式评审，在同一 PR 后续提交；推送前核对远端 head，出现额外变更先协调，避免覆盖。

外部营销发布、联系用户或社群、支出／广告、生产环境或生产数据变更、定价／促销、合并生产行为变更必须获得明确批准。本轮不创建产品 PR，不修改产品源码或生产配置。此前 E01 已授权隔离本地 mock／合成验证；本次评审修订优先且范围仅文档，保留未完成 QA 记录，不继续产品测试。不得将本地结果写成线上成功。

## 分工与证据

Dot（Growth Manager） 负责假设、研究、优先级与推荐；Codex 执行明确批准的工程工作。Cloud Codex 在另行明确工程范围后执行独立分支与 PR；Dot（Growth Manager） 验收，本地技术负责人最终评审与合并，合并后验证。本轮不实现埋点、服务、工作流或投放系统。职责见 [agents](agents/README.md)。

产品参考只读 `bluedao10000/resume` 的 `cn`，固定提交见 [产品基线](knowledge/product-baseline.md)。不从其他分支推断国内版能力。代码、文档声明、线上观察、假设、建议必须分开；没有真实验收不得宣称生产可用。

## 安全与完成标准

不提交凭据、真实简历、个人信息、敏感内部操作细节。公开报告只用公开来源及获准公开的聚合结果。审批记录中不复制私密原文。

使用平台支持的 GitHub 身份，不索取 PAT。操作被拒绝先确认是否已执行；只有新的相关授权证据才可重试一次，不换路线绕过限制。空仓库没有基线时不得擅自初始化默认分支。

交付前执行 [验收清单](evals/acceptance.md)：文件、链接、证据、权限、diff、远端 PR head。未集成独立研究报告时明确阻塞，保留草稿状态，不称为最终就绪。

## 状态与证据

统一使用已完成（completed）、进行中（in progress）、待审批（pending approval）、阻塞（blocked）、未验证（unverified）。每项说明范围和证据，不用“已完成”掩盖生产未验证。样例、内部测试和自动化任务执行均不计作真实增长。

常态流程允许本地 Technical Lead 独立复核并合并达标的 Harness 文档 PR，不永久停在 Draft。当前 PR #1 的本次修订仍保持 Draft，Cloud Codex 不合并、不标 ready、不解决评审线程。国内增长与生产验收目标已由所有者确认为 https://www.codeiy.com/；r.story2u.xyz 只保留为历史对照。
