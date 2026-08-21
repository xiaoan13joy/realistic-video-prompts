# 🎬 真人写实 AI 视频提示词 Skill

> 基于参考图，用电影摄影师的方式设计动作、运镜和现场音效

适配四大视频模型：**Seedance 2.0（即梦）** / **可灵 Kling** / **MiniMax Hailuo** / **MiniMax H3**

双平台可用：**Claude**（标准 Skill 格式）+ **GPT**（Instructions / Knowledge）

![License](https://img.shields.io/badge/license-MIT-green)
![Platform](https://img.shields.io/badge/platform-Claude%20%7C%20GPT-blue)
![Version](https://img.shields.io/badge/version-4.5-orange)

## ✨ 核心特性

- 🖼️ 参考图驱动：不复述图中主体、外貌、环境、光线或氛围
- 🎥 电影摄影师视角：镜头与运镜 + 可选前景/特殊构图 + 动作与表演 + 人景融合 + 现场音效
- 🔍 每个镜头明确大光圈、浅景深，强化写实电影感
- 🎬 动态镜头优先：尽量不用定镜头；定机位也保留克制的手持微晃
- 🪟 根据画面合理加入前景遮挡、倒影、画中画、偏心或引导线构图
- 🧍 动作逐部位拆解：视线、眼睑、眉毛、嘴唇、头颈、肩膀、手指、重心与步态按时间顺序展开
- 🚫 避免“深情地”“带着故事感”等文学化描写，只写镜头可观察、模型可执行的动作
- 🧩 固定人景融合：`人物与场景大小适配，人物与场景光影自然融合`
- 🎞️ MiniMax Hailuo 多镜头模板及 `[推进]`、`[跟随]` 等方括号运镜指令
- 🧑 Seedance 与 MiniMax H3 专属真人皮肤限定：SSS、毛孔微纹理、仅 T 区微油、绒毛微汗及防蜡像负面词
- 🤖 首次询问目标模型，会话内自动沿用，用户主动要求时切换
- ❓ 只在镜头设计或动作表演缺失时一次性追问
- 🔊 每条固定无音乐，保留与画面同步的现场音效
- 💬 输出语言自动跟随用户

## 📁 仓库结构

```text
realistic-video-prompts/
├── SKILL.md
├── README.md
├── LICENSE
├── references/
│   ├── camera-language.md
│   ├── model-adaptations.md
│   └── photoreal-skin.md
└── gpt-single-file.md
```

## 🚀 快速开始

### 💻 Claude Code

```bash
git clone https://github.com/xiaoan13joy/realistic-video-prompts.git \
  ~/.claude/skills/realistic-video-prompts
```

重启会话后，提出“视频提示词”相关需求即可触发。

### ☁️ Claude.ai

1. 从 [Releases](../../releases) 下载最新 ZIP，或使用 **Code → Download ZIP**。
2. 打开 **Settings → Capabilities → Skills → Upload skill** 并上传。
3. 确保 ZIP 解压后的根目录直接包含 `SKILL.md`。

### 🤖 ChatGPT（Custom GPT）

| 方式 | 操作 |
|---|---|
| **Instructions + Knowledge（推荐）** | 将 `SKILL.md` 正文粘贴到 Instructions；将 `references/` 下三个文件上传为 Knowledge |
| **单文件** | 将 `gpt-single-file.md` 整体粘贴到 Instructions |

使用 Instructions + Knowledge 时，可在 Instructions 末尾追加：

> 生成提示词前，必须检索知识文件中的镜头语言词库、模型适配指南和真人皮肤质感限定，并严格按当前模型的格式输出。

## 🎯 使用流程

```text
你：（附上图片）帮我做成真人视频。
AI：请问本次使用哪个视频模型？
    A. Seedance 2.0  B. 可灵 Kling  C. MiniMax Hailuo  D. MiniMax H3
你：C
AI：还缺以下信息，请补充：
    - 镜头设计：希望什么景别、机位或运镜？
    - 动作与表演：人物要做什么，情绪如何变化？
你：中近景缓慢推进，她先看向窗外，再回头对镜头微笑。
AI：「当前模型：MiniMax Hailuo」
    镜头1：[推进] 中近景，大光圈，浅景深；窗框在前景边缘形成画中画；人物视线先移向窗外，眼睑轻眨一次，头部随后小幅侧转，肩膀保持不动……
    镜头2：[右移] 镜头短暂掠过前景窗框；视线先回到镜头，停顿后头颈跟随回转，下颌略微放松，嘴角再缓慢上扬……
    声音：无音乐，保留衣料摩擦、轻微呼吸与画面内环境声。

之后的请求自动沿用 Hailuo，直到你要求切换模型。
```

## 🧭 四大模型速查

| | Seedance 2.0 | 可灵 Kling | MiniMax Hailuo | MiniMax H3 |
|---|---|---|---|---|
| 提示词风格 | 结构化长提示词 | 简洁自然语言 | 详细多镜头提示词 | 镜头/时间段自然语言 |
| 重点 | 多镜头叙事、真人皮肤限定 | 图生视频的动作和运镜 | 表情、镜头控制、多镜头叙事 | 多模态参考、真人皮肤限定 |
| 特殊结构 | `镜头1：...镜头2：...` | 单段自然语言 | `[推进]`、`[拉远]`、`[跟随]` 等 | 全局视觉约束 + 特写补强 |

详见 [`references/model-adaptations.md`](references/model-adaptations.md)。

## 📐 提示词铁律

1. **物理可信优先**：动作、光影和材质符合真实物理规律。
2. **一镜一事**：单个镜头只描述一个连贯动作。
3. **动态镜头优先**：每镜都要有明确运镜；定机位也要有克制手持微晃。
4. **图像内容不复述**：主体、环境和氛围以参考图为准。
5. **无音乐，有音效**：使用与可见动作同步的现场音。
6. **先构图，后动作**：每镜先写前景遮挡或特殊构图，再写动作表演。
7. **动作拆细**：按时间顺序和可见部位描述五官、头颈、躯干与四肢联动。

## 📝 更新日志

| 版本 | 变更 |
|---|---|
| v4.5 | 调整公式为“先前景/构图，后动作表演”；动作改为五官、头颈、躯干和四肢的可执行细节拆解 |
| v4.4 | 改为参考图驱动；不复述静态画面；动态运镜优先；新增前景/特殊构图和“无音乐，有音效” |
| v4.3 | 新增通用公式完整性检查；缺失内容一次性追问，补齐后再生成 |
| v4.2 | 只输出简洁中文；移除英文版；README 增加视觉标识 |
| v4.1 | 新增 MiniMax H3，并为 Seedance 与 H3 加入景别自适应的真人皮肤质感限定 |
| v4.0 | 新增模型确认与默认机制：首次询问、会话内沿用、用户主动切换 |
| v3.0 | 固定人景融合描述；全镜头使用大光圈；支持 GPT 双平台部署 |
| v2.0 | 增加 MiniMax 多镜头长提示词与方括号运镜结构 |
| v1.0 | 通用公式、三模型适配和镜头语言词库 |

## 🤝 贡献

欢迎提交 Issue 或 Pull Request，包括补充新模型适配、修正模型语法变化和丰富镜头语言词库。

## 📄 License

[MIT](LICENSE)
