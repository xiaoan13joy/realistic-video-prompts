# 模型适配

只读取用户所选模型的章节。三模型共用同一镜头事实，不改变人物、动作、台词或结束状态。每个版本都追加核心文件规定的固定摄影规格。

## Seedance 2.0

### 适用输入

- 已有人物图 + 场景图时优先使用多参考图模式。
- 人物图或场景图是多视图拼图时，只作为 reference，不作为首帧。
- 单张真实起始画面才可作为 first frame。

### 参考绑定

按上传顺序使用自然语言编号：

```text
Image 1 exclusively defines the character's face, hairstyle, and outfit.
Image 2 exclusively defines the environment layout, lighting direction, and color atmosphere.
```

多人物时逐个命名，不写匿名的 `use the references`。

### 写法

- 默认用英文写画面，台词保留用户原语言。
- 使用导演式自然语言，先主体动作，再环境、运镜、质感与声音。
- 一个主运镜；用 `slow / smooth / gentle / gradual / stable` 控节奏。
- 完整保留核心文件规定的固定摄影规格，其余摄影参数按镜头需要精简。需要额外焦段感时优先写成景别与空间效果。
- 建议约 80–160 个英文单词，复杂镜头仍保持在 2,000 字符内。

推荐骨架：

```text
[Reference bindings]. Starting from [start anchor], [ordered action and restrained performance].
[Environment motion]. Camera [one movement and framing]. [Photoreal skin and lighting language].
[Visible end state]. [Mandatory fixed cinematography specification].
No background music. Preserve synchronized [specific SFX] and natural ambience.
```

## Kling / 可灵

### 适用输入

- 已有人物图与场景图时使用多参考图或 I2V 能力。
- 平台支持引用占位符时必须显式写 `<<<image_n>>>`；若当前界面不支持占位符，退回 `Image 1 / Image 2` 的显式角色绑定。

### 参考绑定

```text
<<<image_1>>> exclusively defines [Character A]'s face, hair, and outfit.
<<<image_2>>> exclusively defines the location geometry, lighting, and palette.
```

多人物始终使用稳定名称，如 `[Character A: Lin]`、`[Character B: Yang]`。不要在后文改成 `the woman / she / he`。

### 写法

- 画面可用英文或中文；默认英文，中文台词逐字保留。
- 先写可见动作，再写人物台词，避免说话者漂移。
- 使用具体电影动作词：`slow dolly push`、`locked-off medium shot`、`gentle handheld follow`、`lateral tracking`。
- 单镜头只保留一个主运镜。用户明确要多镜头时逐镜标注并分别分配时长。
- 触觉细节服务物理可信度：衣料摩擦、发丝延迟、呼吸、蒸汽、雨滴、脚步受力。

推荐骨架：

```text
[Placeholder bindings]. [Scene and start anchor]. [Character name] [ordered action].
Camera [one concrete move]. [Micro-performance and physical response]. [Photoreal skin and lighting].
[Visible end state]. [Mandatory fixed cinematography specification].
Audio: no background music; only synchronized [specific SFX] and natural ambience.
```

## MiniMax H3

### 适用输入

- 适合真人脸、自然肢体动作、多图参考和原生场景音效。
- 普通生成时长保持 5–15 秒；避免在一个 prompt 中塞多个无关场景。
- 多参考模式可用人物图与场景图；音频参考不能作为唯一参考输入。

### 参考绑定

```text
Image reference 1 exclusively defines the main character identity and outfit.
Image reference 2 exclusively defines the scene layout, lighting, and color.
```

若用户明确在使用支持 H3 正式字段格式的界面，可把正文组织为：

```text
integrated_multimodal_description: [reference bindings, action timeline, camera, performance, end state]
overall_soundscape: [specific synchronized ambience and action SFX]
non_diegetic_music: None.
```

普通 ChatGPT/Codex 交付默认使用自然段，不强制字段格式。

### 写法

- 使用简洁的电影化自然语言。最终 prompt **必须不超过 1,000 字符**；成稿后检查字符数，超限时先删重复静态描述和次要微动作，不删核心动作、终点、参考绑定或声音约束。英文通常控制在 110–140 词。
- 一个主动作弧；13–15 秒可以有清楚的两到三拍递进，但不改场景。
- 起始帧已经锁定外观时，重点写画面如何变化，不复述全部人物与场景。
- 台词只有在用户提供时才写，逐字保留原语言并明确说话者。
- 原生音频只要求环境声、动作音效或用户提供的台词；明确 `non-diegetic music: None`。

推荐骨架：

```text
[Reference bindings]. Starting from [visible start state], [ordered action and performance].
Camera [one movement]. [Environment response and photoreal skin language]. [Visible end state].
[Mandatory fixed cinematography specification].
Soundscape: [specific synchronized SFX and ambience]. No background music.
```

## 三模型同时输出

仅在用户明确要求三模型版本或进行模型比较时：

1. 先写一份不带模型占位符的通用镜头规格。
2. Seedance 版使用 `Image 1 / Image 2` 角色映射与节奏词。
3. Kling 版使用 `<<<image_n>>>` 与稳定角色标签。
4. MiniMax H3 版压缩到 1,000 字符内，明确 soundscape 与无配乐。
5. 三版动作、终点、台词和音效事件保持一致。

不要把三套语法混进同一个 prompt。

用户未指定模型时，优先沿用当前对话已经建立的模型或引用语法；若没有任何模型上下文，先输出一份模型中性的英文 prompt，不自动展开三份版本。
