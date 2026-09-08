# 真人写实 AI 视频提示词 Skill

将人物、场景、动作、运镜、对白与声音要求整理成可直接复制的真人写实 AI 视频提示词。

当前 Skill 名称：`live-action-video-prompts`

支持：

- Seedance 2.0
- Kling / 可灵
- MiniMax H3
- 单镜头、长镜头与多镜头分镜
- 多参考图角色绑定与平台引用别名
- 连续空间关系、人流方向及前景遮挡
- 克制的真人微表演与真实物理动作
- 香港粤语原文、口型同步和现场音效

## 默认制片规则

- Prompt 正文默认使用英文；解释使用用户当前语言。
- 用户提供的台词保持原文、标点与语气。
- 未指定运镜时使用轻微手持晃动和自然摄影师惯性。
- 每条最终 Prompt 都包含浅景深、大光圈、电影感散景、真实光学眩光、8K 高帧率、胶片质感、35mm 与哈苏式自然色彩。
- 明确使用长焦、鱼眼或其他焦段时，`35mm` 表达为胶片质感，避免焦段冲突。
- 无背景音乐，只保留同步动作音效与自然环境声。

完整规则见 [SKILL.md](SKILL.md)。

## 仓库结构

```text
.
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── model-adapters.md
    ├── photoreal-language.md
    └── production-workflow.md
```

## 安装

```bash
git clone https://github.com/xiaoan13joy/realistic-video-prompts.git \
  ~/.agents/skills/live-action-video-prompts
```

## License

[MIT](LICENSE)
