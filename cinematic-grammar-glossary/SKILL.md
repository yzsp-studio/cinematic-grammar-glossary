---
name: cinematic-grammar-glossary
description: |
  cinematic-grammar-glossary知识库（v3.2 章节拆分版）。覆盖叙事、构图、布光、镜头、视角、
  场面调度、剪辑节奏、演技体系、导演技能共 9 章（含 4 章迁移标记）+
  AI 修正清单 + 制作自查清单，约 380 项专业术语。
  FACS表情/微动作/呼吸/眼神已迁移至 `video-prompt-craft` 和 `character-body-language` Skill。
  作为「知识底座」被其他 Skill（如 video-prompt-craft、分镜生成、短剧创作等）或 agent 按需引用。
  当用户需要查询影视专业术语、理解镜头语言、设计场面调度、
  构建分镜提示词、排查 AI 视频通病时触发。
  触发词包括：影视语法、电影术语、镜头语言、场面调度术语、剪辑节奏、
  蒙太奇、构图法则、布光术语、演技技能、导演技能、AI视频修正、制作自查、
  film grammar、cinematic terminology、acting direction、
  mise-en-scène、montage、Stanislavski、method acting、shot dictionary。
summary-cn: 影视语法术语体系，9章380项专业知识底座（章节拆分版）
summary-en: Film grammar terminology system — 9 chapters, 380 professional terms as knowledge base (split-chapter)
version: 3.2.0
tags: [Knowledge, Film, Video, Acting, Directing]
tags-cn: [视频, 影视知识, 演技, 导演]
trigger-words:
  - 影视语法
  - 电影术语
  - 镜头语言
  - 场面调度术语
  - 剪辑节奏
  - 蒙太奇
  - 构图法则
  - 布光术语
  - 演技技能
  - 导演技能
  - AI视频修正
  - 制作自查
  - film grammar
  - cinematic terminology
  - acting direction
  - mise-en-scène
  - method acting
  - shot dictionary
  - Stanislavski
author: yzsp-ai
repository: https://github.com/yzsp-ai
---


# cinematic-grammar-glossary · 知识库 Skill

当用户需要影视专业术语支持——编写分镜表、设计场面调度、构建视频提示词、
排查 AI 视频通病、理解镜头语言——按下方流程提供精确的术语和参数。

> **注意**：FACS 表情、微动作、呼吸控制、眼神表演相关内容已迁移至
> `video-prompt-craft` 和 `character-body-language` Skill，本 Skill 不再覆盖。

## 知识库结构

知识库已拆分为独立章节文件，存放在 `references/` 目录下。
按需加载对应章节文件，**每次最多加载 3 个文件**。

### 章节索引（独立文件）

| 章节 | 文件 | 核心内容 | 术语数 |
|------|------|---------|--------|
| **第1章 叙事手法** | `ch1-narrative-techniques.md` | 4基础+10时间+20结构+15修辞+16蒙太奇 | ~65 |
| **第2章 构图与轴线** | `ch2-composition-axis.md` | 180°轴线+越轴法+三分法+黄金分割 | ~12 |
| **第3章 布光体系** | `ch3-lighting-basics.md` | 三点布光+情绪光型+光线类型（详细方案→epic-cinematic-lighting） | ~21 |
| **第4章 镜头字典** | `ch4-shot-dictionary.md` | 景别+角度+运镜+焦段+构图+转场+铁律 | ~90 |
| **第5章 叙事视角** | `ch5-narrative-perspective.md` | 5基础+5第一+5第二+8第三+10特殊 | ~33 |
| ~~第6章~~ | — | *已迁移* → `video-prompt-craft` | — |
| **第7章 场面调度** | `ch7-mise-en-scene.md` | 11演员+5综合+空间+人际距离 | ~30 |
| **第8章 剪辑节奏** | `ch8-editing-rhythm.md` | 4档位+10类型+节奏模板 | ~20 |
| ~~第9章~~ | — | *已迁移* → `character-body-language` | — |
| ~~第10章~~ | — | *已迁移* → `video-prompt-craft` | — |
| ~~第11章~~ | — | *已迁移* → `video-prompt-craft` | — |
| **第12章 演技技能** | `ch12-acting-system.md` | 斯坦尼6术+方法派5术+4派塑造 | ~30 |
| **第13章 导演技能** | `ch13-directing-system.md` | 5维度分析+5指导法+风格模板 | ~15 |
| **附录A AI修正** | `appendix-a-ai-corrections.md` | 6类18条AI视频通病修正 | 18 |
| **附录B 制作自查** | `appendix-b-checklist.md` | 4类26条可勾选清单 | 26 |
| **附录C 统计指南** | `appendix-c-stats-guide.md` | 术语统计+使用指南 | — |

---

## STEP 0: 识别查询意图

用户请求到达后，判断属于以下哪种使用模式：

### 模式 A：术语查询
用户问"XX是什么""XX怎么用""XX和YY的区别"
→ 定位到对应章节 → 加载该章节 → 直接回答

### 模式 B：提示词构建辅助
用户在编写分镜/视频提示词时需要专业术语支撑
→ 根据场景类型加载相关章节（通常需要多章联动）
→ 输出可直接嵌入提示词的术语和参数

### 模式 C：AI视频质量排查
用户说"表演不自然""表情呆板""运镜机械"等
→ 加载附录A（AI修正清单）+ 相关章节
→ 输出具体修正方案

### 模式 D：项目前期规划
用户在策划阶段需要建立风格锚点
→ 加载第13章（导演风格模板）+ 相关章节
→ 输出填写后的风格锚点文档

---

## STEP 1: 精确加载章节

根据 STEP 0 的意图判断，从 `references/` 目录加载对应章节文件。

**加载方法**：使用 `hub_read` 直接读取 `references/<章节文件名>.md`，每个章节是独立文件，无需 offset/limit。

### 常用场景 → 章节映射

| 用户场景 | 需要加载的章节 |
|---------|-------------|
| 写角色表演提示词 | 第12章(演技) + `video-prompt-craft`(表情/眼神/呼吸) + `character-body-language`(肢体) |
| 设计分镜/镜头 | 第4章(镜头字典) + 第7章(调度) + 第8章(剪辑) |
| 构建场景光影 | 第3章(布光基础术语) + `epic-cinematic-lighting` Skill(完整方案) + 第2章(构图) |
| 叙事结构设计 | 第1章(叙事) + 第5章(视角) |
| AI视频质量排查 | 附录A(修正清单) + 相关章节 |
| 项目风格规划 | 第13章(导演) + 第3章(布光) + 第8章(剪辑) |
| 生成前最终检查 | 附录B(制作自查清单) |

**规则**：
- 单次最多加载 3 个章节（避免上下文溢出）
- 优先加载与用户问题最直接相关的章节
- 如果需要 >3 章节，分批加载，先解决核心问题

---

## STEP 2: 输出专业术语和参数

根据加载的章节内容，为用户提供：

### 对于提示词构建（模式 B）

输出格式：
```
【术语】具体术语名（英文）
【定义】一句话定义
【AI提示词写法】可直接复制到提示词中的英文描述
【注意】AI常见错误 + 修正方案（来自附录A）
```

### 对于质量排查（模式 C）

输出格式：
```
【问题】用户描述的问题
【诊断】对应附录A编号 + 根因分析
【修正方案】具体的提示词修改建议
【验证】修改后应该看到的效果
```

### 对于术语查询（模式 A）

直接引用知识库中的表格和定义，保持原始结构。

---

## STEP 3: 联动其他 Skill（可选）

当用户的需求超出纯知识查询范围时，建议联动：

| 需求 | 推荐 Skill |
|------|-----------|
| 需要生成视频提示词（含表情/眼神/呼吸） | → `video-prompt-craft` Skill |
| 需要角色肢体语言/步态设计 | → `character-body-language` Skill |
| 需要生成分镜故事板 | → storyboard / character-scene-storyboard Skill |
| 需要创作短剧剧本 | → short-drama Skill |
| 需要角色卡/三视图 | → film-assets / film-shot Skill |
| 需要 MV 分镜 | → mv-creator Skill |

本 Skill 只提供知识支撑，不直接生成图片/视频/音频。

**不适用于（NOT for）**：
- ❌ 直接生成视频/图片/音频 → 用对应 agent
- ❌ 写提示词（本 Skill 只提供术语支撑，写 prompt 用 `video-prompt-craft`）
- ❌ 角色设定/分解图 → 用 `panoramic-character-breakdown` 或 `film-assets`

---

## 附录: 视觉风格速查表

供写分镜/提示词时快速选定视觉基调。一个镜头只用一种风格，混合风格直接崩。

| 风格 | 色板 | 光影 | Prompt 关键词 |
|------|------|------|-------------|
| 赛博朋克 | 霓虹粉紫蓝+暗底 | 霓虹主光+地面反射 | `cyberpunk city, neon-lit rainy street, holographic signs, wet asphalt reflections` |
| 港片夜雨 | 品红+电青+钨丝灯 | 单光源+半脸阴影 | `saturated magenta and cyan, claustrophobic interior, single neon light source` |
| IMAX 史诗 | 冷青蓝灰+低饱和 | 自然光+强对比 | `IMAX scale composition, cool teal-grey palette, practical lighting only` |
| 对称糖果色 | 粉色+芥末黄+薄荷绿 | 均匀柔光 | `Wes Anderson style, perfectly symmetrical, pastel candy palette` |
| 北欧极简 | 冷白+灰蓝+原木色 | 柔和散光 | `Nordic minimalist, vast negative space, soft overcast lighting` |
| 70s 胶片 | 暖黄橙+褪色感 | 温暖自然光+眩光 | `1970s film aesthetic, faded warm tones, heavy 35mm grain, Kodak Portra look` |
| 黑色电影 | 高对比黑白 | 硬光+戏剧投影 | `film noir, high contrast b&w, venetian blind shadow patterns` |
| 自然写实 | 自然肤色+土色调 | 自然窗光+柔和过渡 | `naturalistic lighting, handheld feel, muted earth tones` |

**按场景选风格**：
- 城市夜戏 → 赛博朋克 / 港片夜雨 / 黑色电影
- 日常生活 → 自然写实 / 北欧极简 / 70s 胶片
- 史诗大场面 → IMAX 史诗
- 童话/复古喜剧 → 对称糖果色
- 悬疑/罪案 → 黑色电影 / 港片夜雨
- 文艺/个人叙事 → 70s 胶片 / 自然写实

## 附录: 媒介风格锁

比视觉风格更基础的一层——画面是写实、动漫还是 3D。不显式锁定媒介，模型会飘。

| 媒介 | Prompt 必须显式写 | 同时排除 |
|------|-----------------|---------|
| **写实摄影** | `Medium: hyper-realistic photography. Photorealistic, live-action film still.` | `NOT anime, NOT cartoon, NOT 3D render` |
| **2D 动漫** | `Medium: 2D anime illustration style. Hand-drawn anime aesthetic.` | `NOT photoreal, NOT live-action, NOT 3D render` |
| **3D 渲染** | `Medium: stylized 3D render. CG animation style.` | `NOT photoreal, NOT anime, NOT 2D illustration` |

**使用规则**：
1. 每次 prompt 都要写——子 agent 无状态
2. 写在 prompt 顶部、紧跟主体描述之后
3. 必须同时写 NOT 排除项——单写正向不够
4. 整组分镜锁同一种媒介

---

## 知识库维护说明

- **版本**：v3.2（2026年5月）
- **体系来源**：好莱坞WGA + ASC + 斯坦尼体系 + 方法派 + 中戏/北电/上戏
- **术语总计**：~380项
- **存储结构**：每章独立文件，存放在 `references/` 目录下（ch1 ~ ch13 + appendix-a/b/c）
- **已迁移内容**：FACS表情(→video-prompt-craft) / 微动作(→character-body-language) / 呼吸(→video-prompt-craft) / 眼神(→video-prompt-craft)
- **更新方式**：修改对应章节的独立 `.md` 文件，新增章节时同步更新本文件的章节索引表
