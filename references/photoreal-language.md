# 真人写实语言

按镜头需要选词，优先写正向、可见、可执行的目标。负面约束只保留当前镜头确有必要的最短一句，不建立示例词库。

## 皮肤质感强度

### 面部特写 / 近景

选择 3–5 项：

```text
natural human skin micro-texture
visible but subtle pores
fine peach fuzz catching the side light
slight natural unevenness in skin tone
soft subsurface warmth at the ears and nose edges
restrained T-zone sheen, natural sebum rather than an oily face
faint expression lines and small asymmetries
```

### 中景

压缩成一行：

```text
natural human skin texture with subtle pores, slight tonal unevenness, and restrained highlights
```

### 全景 / 远景

使用简洁的整体写实描述：

```text
natural unretouched human appearance and believable skin response to the scene light
```

## 自然微表演

每镜选择 1–3 项，形成克制、连贯的微表演：

- 呼吸让肩膀或胸口产生极轻起伏。
- 自然眨眼一次，随后目光重新聚焦到明确对象。
- 下颌、嘴角或眉心产生与情境一致的细微变化。
- 吞咽、短暂停顿、半抬手又放下、指尖收紧或松开。
- 眼神先接收信息，再出现克制反应；不要直接贴“悲伤、震惊、愤怒”标签。

用户需要强情绪时按身体链路写：脸部变化 → 颈肩张力 → 呼吸 → 重心 → 手部落点。只选可在当前时长内清楚完成的环节。

## 物理可信度

- 人物启动或停止后，头发与松散衣料有轻微延迟。
- 行走时脚掌真实落地，重心从后脚转移到前脚。
- 拿起物体时手腕、手指和前臂共同承担重量。
- 接触桌面、门、杯子或衣料时，让动作产生对应声音与细小反作用。
- 风、雨、烟、蒸汽、窗帘或反射只选与场景相符的 1–2 项。

## 光线与摄影

写光源、方向和对皮肤的作用，不只写 `cinematic lighting`：

- 自然窗光：`soft window light from camera-left, preserving facial depth and natural skin highlights`。
- 金色时刻：`low warm sunlight grazing the cheek and hair edge, with soft open shadows`。
- 室内钨丝灯：`warm practical light above and behind the subject, balanced by soft ambient fill`。
- 阴天：`broad overcast daylight with gentle contrast and honest skin tone`。
- 夜景：`motivated practical light from the storefront, with controlled reflections on damp skin`。

不要同时指定互相冲突的光源。Seedance 版少写焦段与光圈数字；Kling 和 MiniMax H3 版可在确有帮助时写景别感，但仍以可见结果为主。

## 运镜选择

| 目的 | 主运镜 |
|---|---|
| 观察细微情绪 | locked-off close-up 或 very slow push-in |
| 跟随行走 | gentle lateral tracking 或 restrained handheld follow |
| 揭示人物与空间关系 | slow pull-back |
| 保持身份与口型稳定 | locked-off medium shot |
| 展示环绕关系 | slow controlled arc，人物动作保持简单 |

主运镜写清速度与结束位置，让摄影路径保持单一、连续。

## 音效映射

只写画面中有来源的声音：

| 可见事件 | 可用音效 |
|---|---|
| 行走 / 转身 | measured footsteps, sole contact, clothing rustle |
| 坐下 / 起身 | chair creak, fabric tension, soft foot adjustment |
| 杯子 / 餐具 | ceramic contact, faint liquid movement, utensil clink |
| 门窗 | latch click, hinge movement, change in room tone |
| 雨景 | rain on glass or awning, wet footsteps, distant traffic |
| 室内静场 | low room tone, ventilation hum, subtle breath |
| 户外风 | wind through leaves, hair and clothing rustle |

写成同步关系，而不是音效清单：

```text
As the cup touches the table, a soft ceramic click lands exactly with the hand movement; quiet café room tone continues underneath.
```

所有镜头最终追加：

```text
No background music. Preserve synchronized diegetic sound effects and natural ambience.
```
