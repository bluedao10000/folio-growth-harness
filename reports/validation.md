# 文档交付与任务验收

更新时间：2026-11-15（UTC+8）。任务：[FGH-001](README.md)。分支 `docs/folio-growth-harness-v1`；修订前 head `29522513c0411ee9349a3be34bfe725aa1bee866`；main 基线 `8acf7e4378c743ad19ae57e8d663317c096ce771`。

## FGH-001 范围和实际交付

范围仅 Harness 文档修订。Dot 决定增长工作流与探索性规则；Cloud Codex 执行；Technical Lead 独立复审。预期响应以下六条正式意见，保持当前 Draft，不 merge／ready／resolve，不修改产品或生产。

| 评审要求 | 实际修订／证据位置 | 状态与失败边界 |
| --- | --- | --- |
| [4578651248 角色与长期规则](https://github.com/bluedao10000/folio-growth-harness/pull/1#discussion_r4578651248) | [规则](../OPERATING_RULES.md)、[角色](../agents/README.md)、[AGENTS](../AGENTS.md)、[入口](../README.md)、D07、验收清单区分首次 Draft 和长期 Technical Lead 文档合并 | 已完成文档修订；独立复审未验证；Cloud Codex 不自并 |
| [4578651253 可恢复流水](https://github.com/bluedao10000/folio-growth-harness/pull/1#discussion_r4578651253) | [任务卡 FGH-001](README.md)含 owner／executor、范围、状态、阻塞、下一行动、决策／证据／PR／验收；[手册](../playbooks/README.md)定义恢复流程 | 已完成持久卡；独立新会话恢复已由 Dot 回报通过，正式 Technical Lead 复审仍待完成 |
| [4578651257 实际交付验收](https://github.com/bluedao10000/folio-growth-harness/pull/1#discussion_r4578651257) | [验收清单](../evals/acceptance.md)增加按任务比较范围、预期／实际、证据、失败边界、回滚及收尾；本表为实例 | 已完成文档；Technical Lead 需按卡独立复核 |
| [4578651260 E02 判定](https://github.com/bluedao10000/folio-growth-harness/pull/1#discussion_r4578651260) | [E02](../experiments/E02-positioning.md)预先 0/1 三项、首次曝光分配、分版分母、完成率、误解率、5 条／20 个百分点待批规则与证据不足处理；同步登记、模板、D04、路线 | 已完成设计；数据／实验／招募待审批，没有参与者或赢家 |
| [4578651261 指标现状](https://github.com/bluedao10000/folio-growth-harness/pull/1#discussion_r4578651261) | [指标字典](../knowledge/metrics.md)引用固定 cn 的 track/events 源码，区分现有匿名首页事件、未知生产聚合、拟议下游；同步策略 | 已完成源码核对；未访问分析后台，业务基线未知 |
| [4578651267 市场证据](https://github.com/bluedao10000/folio-growth-harness/pull/1#discussion_r4578651267) | [市场审计](folio-growth-audit.md)把模板入口竞争降为假设，注明渠道排序依据与未知；robots GET 与收录／增长分开 | 已完成表述修订；无流量、排名或竞争强度实测 |

research-status 内容已并入[报告索引](README.md)，删除重复文件并迁移引用。国内目标以所有者确认的 codeiy.com 为准；r.story2u.xyz 仅保留历史公开面对照。

## 文档检查与回滚

必需根文件和六个目录保留，LICENSE 不变；本次仅 Markdown。本次检查：23 个 Markdown 文件、139 处链接引用；相对路径无缺失；37 个外部链接目标（含评审锚点）全部 HTTP 200，评审锚点 ID 另由 GitHub API 返回核对；git diff --check 通过。远端 head 和 draft 在提交后读取核实；具体最终 SHA 见 PR head 与线程交付消息。本提交不自引用尚未生成的 SHA。

未写入凭据、真实简历、用户数据或敏感部署标识。研究记录不含原始生产响应或私人讨论。文档回滚采用后续更正／回退 PR，不 force push、不直接改 main。当前没有产品／生产变更需要回滚。

独立复核方法：新会话只从 FGH-001 卡进入，定位本表六个对应文件与评审线程，检查 diff 和远端 SHA、状态及所有未验证项，记录审查身份／时间／下一行动与结论。随后独立 reviewer 仅收到持久任务入口，已恢复负责人、证据、阻塞与下一行动（Dot 于 2026-11-15 回报，检查对象为 6fde17c 的卡）。未取得可公开的原始审查记录链接；此处明确记录回报来源及缺口，不将其等同正式 Technical Lead 技术复审。同会话持久化可读仍不算跨会话通过。

## E01 单独 QA 结果：本地 mock 有限验证完成

此前授权的本地隔离验证读取 resume/cn `0d0ea46afb252c8cfcbcb9f27ed128ed070a3536`、prototype 说明和官方林知夏／sampleJD。未修改产品仓库跟踪文件；运行目录为独立归档副本，不向产品仓库提交任何变更。

可复现环境：Node 24.22.1、npm 11.9.0；官方 demoAgent；浏览器拦截非本地网络，配置／会话／Agent 使用本地 mock，无模型凭据。

1. 原样 `npm ci` 失败：`EUSAGE`，缺少 lock 中的 `@emnapi/runtime`、`@emnapi/core`。`--legacy-peer-deps` 仍失败，具体缺项为 runtime 1.11.3、core 2.0.0-beta.2。
2. 隔离副本使用 `npm install --package-lock=false --legacy-peer-deps` 成功，未改原锁文件；因此不能声称严格锁文件可复现安装通过。
3. 首次 dev 启动因默认配置目录不可写失败；将 XDG_CONFIG_HOME 指向可写隔离临时目录后启动成功，但首页返回 HTTP 500，服务端错误为 `The Console.createTask method is not implemented`，导致 Playwright 等待“试用示例”超时。
4. `npm run build` 在隔离副本成功，使用 `wrangler dev --local --config dist/server/wrangler.json --ip 127.0.0.1 --port 5173` 运行产物，完成实际浏览器流程。此前 dev 错误可复现，但不能归为生产缺陷；替代安装不证明严格 lockfile 安装通过。
5. 同一林知夏原稿两次作为来源，产生两个独立岗位版本；原稿全对象保持不变，个人事实／经历／技能集合不新增，仅排序与版本元数据不同。A 缺 B2B SaaS／英语沟通，B 缺 Python／SQL，均未注入简历。B 直接编辑目标职位后刷新保留，不影响 A／原稿，不增加副本或重放调用。两份实际 JSON 导出与各自存储对象一致。
6. 两份实际 PDF 各一页 A4（594.96 × 841.92 pt），全部预期文本可提取、文字边界在页面内；逐页渲染检查未见裁切或重叠，虚构标记保留。点击打印入口核实调用后，由 Chromium 156.0.8078.79 的 page.pdf 打印引擎输出应用打印 CSS；不是截图／仅 HTML，也不是操作系统原生打印对话框已验收。两份 PDF 均在 B 人工标题修改前导出。
7. 仓库已有“JD 定制入口直接可见，取消不生成，确认保留来源且刷新不重放”和“聊天润色、JD 定制、编辑、持久化与模板切换”两项 mock E2E 均通过（2 passed，5.8s）。额外脚本曾因导出弹窗未关闭、按钮计数和虚构标签匹配错误失败；只修正外部测试脚本，未改产品。
8. 本任务本地服务已停止，5173 端口关闭；没有真实模型、生产登录／写入、参与者收集、费用或产品 PR。

### 证据与可访问性

| 产物 | 检查结果／指纹 | 持久交付状态 |
| --- | --- | --- |
| folio-A.pdf | 单页 A4；SHA-256 `930e552af7799e5b1ff41c302ea2feebf57fe50f90bbbf645506303c9cdec09c` | 本地已生成；未成功保存 Library |
| folio-B.pdf | 单页 A4；SHA-256 `b0abd3afcf376ec3251f71a7bf8ab944796c0edbe69008dc10a08ed3c46bddee` | 本地已生成；未成功保存 Library |
| 合成证据包 | 原稿、两 JD、两版 JSON、请求结果、PDF 文本／渲染、独立编辑记录和复现脚本 | 本地保留；没有可公开或长期访问附件链接 |

Library 保存失败的确切错误为 `hosted apps tools/list request failed with HTTP status 401`。没有伪造附件或用执行工作区路径冒充持久链接；公共仓库只写本摘要与指纹，不上传 PDF 或用户资料。独立审查者若需重看原文件，应先恢复获准的私有附件交付；哈希仅用于之后比对，不等同远程可访问证据。

结果边界：本地官方 mock 仅做规则排序，不能证明真实模型语义定制、codeiy 部署 SHA、生产闭环、真实用户激活或任何增长。两份短单页样例不覆盖长文分页、手机／Mac 原生打印或物理打印。原稿选择、演示只排序、浏览器打印步骤是待观察的摩擦候选，没有用户流失或转化数据。真实用户 E01 的 8 人／≥6/8 门槛及审批要求不变。
