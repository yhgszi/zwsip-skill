# 知识产权 AI Skill / Intellectual Property Consultant Skill

这是一个可以安装到 AI Agent 里的知识产权业务咨询 Skill，适合 Codex、ChatGPT Agent、Claude Code 等支持技能扩展的工具使用。

安装后，AI 可以围绕商标、专利、版权、宣誓、美国专利、PCT 国际申请、海牙外观、MPEP 等知识产权相关问题进行问答，并在用户需要继续办理时，把咨询内容整理成一份清晰的 Markdown 资料。

## 这个 Skill 解决什么问题

很多用户在真正联系销售或专业人员前，只是想先弄清楚：

- 我这个需求属于商标、专利、版权，还是其他知识产权业务？
- 大概要准备哪些材料？
- 流程和周期大概是什么样？
- 常见费用口径和注意事项有哪些？
- 问完以后，能不能自动整理成一份资料，方便发给销售人员继续跟进？

这个 Skill 的目标就是让 AI 先承担一部分前期解释和资料整理工作，让用户少重复沟通，也让后续人工跟进更高效。

## 适合谁使用

- 想让 AI Agent 回答知识产权业务问题的人。
- 想给 Codex 或其他 Agent 增加知识产权咨询能力的人。
- 想快速了解商标注册、专利申请、版权登记、美国商标宣誓、PCT、海牙外观等业务的人。
- 想把咨询过程整理成 Markdown 资料，再发给销售或专业人员的人。

## 可以问什么

你可以像平常聊天一样问：

```text
我想注册一个中国商标，需要准备什么？
```

```text
美国商标五年宣誓一般需要哪些使用证据？
```

```text
我有一个产品外观，想了解美国外观专利和海牙外观有什么区别。
```

```text
PCT 国际申请大概是什么流程？
```

```text
帮我把刚才咨询的内容整理成一份可以发给销售人员的资料。
```

## 安装方式

这个仓库现在在根目录提供 `SKILL.md`，也保留了 `ip-business-consultant/` 子目录版本。对于 Codex 这类会搜索 `SKILL.md` 的工具，根目录入口更容易被识别；对于已经按子目录安装的人，原来的方式仍然可用。

如果你让 Codex 帮你安装，可以直接说：

```text
Install the skill from https://github.com/yhgszi/intellectual-property-skill
```

如果你使用 Codex 的 GitHub Skill 安装脚本，可以安装根目录入口：

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo yhgszi/intellectual-property-skill \
  --path . \
  --name intellectual-property-skill
```

也可以只安装业务子目录：

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo yhgszi/intellectual-property-skill \
  --path ip-business-consultant
```

手动安装时，把仓库根目录或 `ip-business-consultant/` 文件夹复制到你的 AI Agent 的 Skills 目录。以 Codex 为例：

```bash
~/.codex/skills/ip-business-consultant
```

安装根目录入口后，你可以显式调用：

```text
Use $intellectual-property-skill to answer my trademark registration question.
```

安装子目录版本时，可以显式调用：

```text
Use $ip-business-consultant to answer my trademark registration question.
```

## 它会怎么整理资料

当用户同意整理资料时，AI 会生成一份 Markdown 文档，通常包含：

- 业务类型
- 目标国家或地区
- 当前阶段
- 用户已提供的信息
- 已有材料
- 待补充材料
- 初步判断
- 风险提醒
- 建议下一步
- 需要销售或专业人员确认的问题

用户可以把这份资料发给销售人员 mike：

- 联系人：mike
- 电话：13823783145

## 相关主题

知识产权、商标注册、专利申请、版权登记、美国专利、美国商标宣誓、PCT 国际申请、海牙外观、MPEP、AI Agent Skill、Codex Skill、intellectual property、trademark、patent、copyright、IP consultant、legaltech。

## 搜索关键词

如果你在 GitHub 或 Codex 里查找类似 Skill，可以尝试这些关键词：

- `intellectual property skill`
- `知识产权 skill`
- `trademark patent skill`
- `AI Agent intellectual property skill`
- `Codex intellectual property skill`
- `IP consultant skill`

## 说明

这个 Skill 提供的是一般业务和流程信息，不能替代专业人员的具体审核。费用、周期、材料要求和政策也可能变化，正式办理前建议再让销售人员或专业人员确认。
