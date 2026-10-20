# Understanding First · 理解优先

**让 AI 的输出变得容易理解、可以检查、能够用起来。**

一个受 Andrej Karpathy 关于“如何理解 LLM 输出”的建议启发的 Agent Skill。根据读者的困难，在清晰文字、关系图、交互 HTML 和讲解视频之间选择合适的表达形式，并让人能检查 AI 的结果。

这是 JerryYangAI / 广哥在硅谷的独立整理与实现，不是 Karpathy 官方项目，也不是 ASD-STE100 认证工具。

## 五个核心观点

| 观点 | 实践方向 |
|---|---|
| 01 · 先把话写清楚 | 借鉴 STE：短句、术语一致、动作明确，保留事实与限定条件 |
| 02 · 让关系显形 | 用图表解释结构、步骤、输入输出与反馈 |
| 03 · 把解释变成可操作的网页 | 改变参数，观察结果，验证自己的理解 |
| 04 · 用视频讲清变化 | 用动态演示、旁白与字幕解释一个过程 |
| 05 · 把精力转向监督与理解 | 让 AI 展示结果、证据、检查和不确定之处 |

前四项是截图中的表达方法，第五项来自其总结。这里的提示词、示例和验收办法是本项目的操作化补充，不是逐字引语。

## 安装到 Codex

```bash
git clone https://github.com/JerryYangAI/understanding-first-agent-skill.git
cd understanding-first-agent-skill
```

将 `skills/understanding-first` 文件夹复制到 Codex 的 skills 目录。以下命令不会覆盖已存在的同名 skill：

```bash
skill_root="${CODEX_HOME:-$HOME/.codex}/skills"
mkdir -p "$skill_root"
if [ -e "$skill_root/understanding-first" ]; then
  printf '%s\n' '同名 skill 已存在，请先检查版本；未覆盖。'
else
  cp -R skills/understanding-first "$skill_root/understanding-first"
fi
```

重新打开会话后使用：

> 请使用 $understanding-first，帮我理解 PCA。先解释最关键的机制，再做一个可以改变投影方向的 HTML 演示。说明这个演示省略了什么。

也可以直接把 [SKILL.md](skills/understanding-first/SKILL.md) 交给支持技能文件的 Agent 阅读。其他客户端的发现目录和安装方式以其文档为准；本仓库不宣称已在所有客户端验证。

## 使用示例

- “把这段技术说明改得更好懂，保留所有条件，不要做网页。”
- “用一张标注清楚的图解释 Agent Harness。区分模型、工具和状态。”
- “做一个能改变参数的 HTML，让我看懂什么是内部表示。”
- “把这个机制做成一分钟讲解视频，配音使用我已授权的工具。”
- “让我检查这份 AI 方案：哪些已验证，哪些仍是假设？”

默认不要求 API Key，也不绑定模型或媒体供应商。只有实际调用对应服务时才需要其工具和授权。用户要求文字就交付文字，不会强行制作四种文件。

## 文件

- [技能入口](skills/understanding-first/SKILL.md)
- [按表达形式选择方法](skills/understanding-first/references/formats.md)
- [来源、改写与授权边界](skills/understanding-first/references/sources.md)
- [中文案例与验收任务](examples/中文案例与验收.md)
- [朋友圈五张观点图及文案](social/README.md)

## 验证范围

技能结构可用 Codex skill-creator 的 `quick_validate.py` 检查。它只检查技能格式，不证明解释一定正确。

本仓库提供一个无需联网的交互 HTML 示例及人工验收清单。发布记录会区分实际完成的检查和待运行的行为测试。没有跨模型效果基准，也不承诺某种输出形式总是最好。

当前已完成的检查见 [VALIDATION.md](VALIDATION.md)。

## English

Understanding First is an independent, Chinese-first agent skill for making difficult material understandable through clear writing, labeled diagrams, interactive HTML, and narrated explanation. It preserves the requested format, protects factual qualifications, and makes assumptions and verification visible. It is inspired by a user-provided Karpathy passage, not affiliated with him. See the source note for attribution limits.

## License

[MIT](LICENSE) for this project's original material. Third-party references and standards retain their own rights.
