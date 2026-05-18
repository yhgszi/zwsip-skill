# 知识产权业务 Skill 框架说明

## 目标

本项目用于建设一个可开源发布的知识产权业务 Skill。它的第一阶段目标不是替代销售或专业代理人，而是让用户先通过 AI 了解商标、专利、版权、宣誓等业务，并在需要时生成结构化 Markdown 资料，方便销售或专业人员继续跟进。

## 架构原则

- 根目录 `SKILL.md` 负责开源仓库发现、触发说明、流程调度和资源路由，方便 GitHub/Codex 这类工具第一时间识别这是一个 Skill。
- `skills/intellectual-property-skill/SKILL.md` 是推荐安装的正式 Skill 入口，匹配常见公开 Skill 仓库结构。
- `skills/intellectual-property-skill/references/remote-update.md` 负责远程更新策略：联网时优先读取 GitHub raw 最新公开文档，本地文件作为兜底。
- `skills/intellectual-property-skill/references/response-style.md` 负责客户回复提示词工程，所有客户答案都应先遵循它。
- `skills/intellectual-property-skill/references/` 负责业务知识，按商标、专利、版权、宣誓、通用规则、交接流程拆分。
- `skills/intellectual-property-skill/assets/` 负责可复用模板，例如客户资料交接模板。
- 不把所有内容堆到一个文件里，后续资料按业务模块合并到现有文件。
- 价格、政策、官方周期等易变化信息必须标注来源和日期。

## 开源发现优化

为了让用户在 GitHub、Codex 或其他 Agent 工具中搜索知识产权相关 Skill 时更容易发现本仓库，当前采用以下公开入口：

- 仓库名：`intellectual-property-skill`
- 根目录入口：`SKILL.md`
- 根目录 UI 元数据：`agents/openai.yaml`
- 推荐安装目录：`skills/intellectual-property-skill/`
- GitHub About 描述包含中英关键词：知识产权、AI Agent Skill、商标、专利、版权、trademark、patent、copyright、PCT、Hague、MPEP。
- GitHub Topics 包含：`intellectual-property`、`ai-agent`、`codex`、`skill`、`trademark`、`patent`、`copyright`、`pct`、`mpep`、`hague-system`、`legaltech`、`knowledge-base`。
- Skill frontmatter 中保留核心触发词；README 避免堆关键词，优先保持自然、可信、适合安装用户阅读。
- 新仓库如果被搜索器加上 `stars:>1` 过滤，短期内会被排除；这需要真实 GitHub star 和使用活跃度累积，不能仅靠 README 解决。

根目录 `SKILL.md` 不复制业务正文，只路由到 `skills/intellectual-property-skill/references/` 和 `skills/intellectual-property-skill/assets/`，避免后续维护两份业务口径。

## 资料补充顺序

1. 先补 `common-consultation-rules.md`，明确统一口径、隐私边界、免责声明。
2. 再补 `intake-workflow.md`，确定销售真正需要哪些字段。
3. 按业务优先级补 `trademark.md`、`patent.md`、`copyright.md`、`declaration.md`。
4. 最后完善 `sales-handoff.md` 和 `assets/client-intake-template.md`，让输出资料符合销售接单习惯。

## 客户回复口径

Skill 的默认回复应像真正的销售或服务人员，而不是像资料检索机器人。常规咨询尤其是价格、周期、材料问题，应优先给客户能直接决策的信息：

- 如果环境允许联网，先按 `references/remote-update.md` 获取最新公开规则；不能联网时使用本地安装副本。
- 先读取 `references/response-style.md`，再读取对应业务资料。
- 先回答客户最关心的问题，再补必要条件。
- 报价类问题默认按“费用、周期、需要材料、下一步”组织。
- 不主动输出内部来源、报价表日期、官方规费细节、长免责声明或检索过程。
- 不说“根据这个 skill”“报价表显示”等内部话术。
- 每次最多追问一个关键问题，方便客户继续沟通。

## 自动更新边界

Codex 当前的 GitHub skill 安装方式是复制目录到本地，安装器不会自动覆盖已安装目录。因此真正“无感更新”只能通过远程公开文档实现：本地 skill 作为启动器，联网时读取 GitHub raw 最新规则和资料。这个机制可以更新回复口径和业务资料，但如果入口文件、目录结构或 skill 名称变化，用户仍可能需要重新安装。

## 销售对接流程

Skill 已配置销售对接信息：

- 联系人：mike
- 电话：13823783145

当用户咨询到适合人工继续跟进的阶段时，AI 应先询问用户是否需要整理资料并对接销售。用户同意后，AI 才生成 Markdown 交接文档，方便用户自行发送给销售人员。

## 表格资料转换

报价单、费用表、周期表等 Excel 文件建议先转换成 Markdown，再按公开范围放入 Skill 的 `references/` 目录，方便 AI Agent 快速检索。

当前已转换：

- `docs/知识产权业务报价（2026.5.16）.xlsx`
- `docs/知识产权业务报价（2026.5.16）.md`

转换后的 Markdown 保留工作表标题、表格、长备注和合并单元格中的上下文。后续如果要放入开源 Skill，需要先确认报价、服务范围、官方费用、周期和内部销售策略是否适合公开。

## PDF 原始资料使用

`docs/e9r-01-2024/` 目前包含 43 个 MPEP PDF 文件，总计约 59MB、4216 页。抽查结果显示大多数 PDF 可以直接提取文本，适合作为权威原始来源保存，但不适合让 AI 在每次用户咨询时临时逐个读取。

当前已生成 Markdown 缓存：

- `docs/e9r-01-2024-md/INDEX.md`
- `docs/e9r-01-2024-md/*.md`
- `skills/intellectual-property-skill/references/mpep-e9r-01-2024/INDEX.md`
- `skills/intellectual-property-skill/references/mpep-e9r-01-2024/*.md`

缓存共 44 个 Markdown 文件，其中 43 个对应原始 PDF，1 个为索引文件。总大小约 17MB，索引显示提取文本约 1766 万字符。

建议做法：

- 保留 PDF 作为原始来源和审计依据。
- 另行生成按章节拆分的 Markdown 或纯文本缓存，供 AI 检索。
- 建立一个简短索引文件，说明每个 MPEP 章节对应主题，例如 1500 外观专利、1800 PCT、2100 专利性、2900 海牙外观。
- 在 Skill 中只放路由说明和必要摘要，不要把 4000 多页正文直接塞进 `SKILL.md`。
- 用户咨询美国专利、PCT、海牙或美国外观专利时，先根据索引定位章节，再读取对应 Markdown 片段。

## 是否需要服务器

第一版不需要服务器。Skill 可以直接作为公开知识库和资料整理流程使用。

后续如果需要以下能力，再设计服务器或 API：

- 自动提交客户线索到 CRM；
- 自动通知销售；
- 动态报价；
- 查询订单或案件进度；
- 读取不适合开源的内部知识库；
- 记录来源、转化和服务质量数据。

服务器能力应作为可选增强，不应影响开源 Skill 的基础使用。

## 发布前检查

- 删除或改写所有未确认的占位内容。
- 确认每个业务模块都有来源、日期或公司审核状态。
- 确认不包含内部机密、客户隐私、账号密钥或未授权报价。
- 确认免责声明清晰。
- 确认销售交接 Markdown 模板可直接使用。
