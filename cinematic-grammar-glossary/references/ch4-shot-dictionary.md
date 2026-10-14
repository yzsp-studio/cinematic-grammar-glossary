# 第四章｜镜头类型完整字典（Camera Movement & Shot Dictionary）

> **核心原则**：每种镜头类型必须标注「画面起点 → 画面终点」，杜绝"推镜头"三个字了事。  
> **运动原则**：所有镜头运动必须有**缓入缓出**（Ease In/Out），避免线性运动；优先**弧线路径**。

## 4.1 基础运镜七式

| 镜头类型 | 英文术语 | 物理定义 | 画面起点→终点模板 | Seedance提示词写法 |
| ----- | --- | --- | --- | --- |
| **推** | Push In / Dolly In | 摄影机沿光轴向前移动 | 起：全景人物居中1/3 → 终：特写面部占画面80% | `Slow Dolly In from full-body framing to tight face close-up over Xs` |
| **拉** | Pull Out / Dolly Out | 摄影机沿光轴后退 | 起：特写眼睛 → 终：全景暴露整个环境 | `Dolly Out from ECU on eyes to wide shot revealing entire room` |
| **摇** | Pan (水平) / Tilt (垂直) | 机位不动，镜头水平/垂直转动 | 起：A角色面部 → 经过空间 → 终：B角色面部 | `Pan Right from [A] across 3m of space to [B] at constant speed` |
| **移** | Tracking / Lateral Dolly | 摄影机平行于被摄体横向移动 | 起：左侧遮挡 → 终：右侧完整暴露角色 | `Lateral tracking shot moving left-to-right, parallax revealing character` |
| **跟** | Following Shot | 摄影机跟随运动主体保持恒定距离 | 起：角色背影 → 保持构图 → 终：角色停步转身 | `Following shot maintaining MS on character's back, Xs walk + turn` |
| **升** | Crane Up / Boom Up | 摄影机垂直上升 | 起：低角度仰拍面部 → 终：俯瞰全场 | `Crane Up from low-angle CU at knee level to high-angle WS overhead` |
| **降** | Crane Down / Boom Down | 摄影机垂直下降 | 起：俯瞰全场 → 终：平视/仰视角色 | `Crane Down from bird's-eye WS to eye-level MS, landing on character` |

## 4.2 高阶运镜五式

| 镜头类型 | 英文术语 | 物理定义 | 画面起点→终点模板 | Seedance提示词写法 |
| --- | --- | --- | --- | --- |
| **甩** | Whip Pan / Swish Pan | 极速水平摆动，画面拉成运动模糊 | 起：A的动作 → 模糊0.2s → 终：B的反应 | `Whip Pan from [A]'s action across 0.2s motion blur to [B]'s face` |
| **环绕** | Orbit / Arc Shot | 摄影机绕被摄体做圆弧运动 | 起：角色正面 → 经过侧面 → 终：3/4背面或回到正面 | `360° Orbit around character at chest height, 1 full revolution in Xs` |
| **推轨** | Dolly Track | 沿预设轨道做长距离线性运动 | 起：空间A入口 → 穿越走廊 → 终：空间B终点 | `Dolly Track shot through corridor, 10m travel distance, eye-level` |
| **斯坦尼康跟拍** | Steadicam Follow | 手持稳定器浮动跟拍，略带呼吸感 | 起：跟随背部 → 保持2m距离 → 终：角色转身reveal | `Steadicam follow at 2m behind, subtle float oscillation ±1°, MS framing` |
| **主观渐显** | POV Reveal | 第一人称视角逐步清晰化 | 起：全模糊/黑屏 → 逐步对焦 → 终：看清面前的人/物 | `POV shot: start 100% defocused blur → rack focus over 2s to sharp [target]` |

## 4.3 希区柯克变焦（推轨变焦 / Vertigo Effect）

**权威来源**：阿尔弗雷德·希区柯克在《迷魂记》中发明，电影史上最具表现力的镜头之一

**核心定义**：摄影机向前推轨的同时向后变焦，保持主体大小不变，背景空间产生扭曲效果。

| 参数 | 说明 |
| --- | --- |
| 摄影机 | 向前匀速推轨 |
| 镜头 | 同时匀速向后变焦 |
| 效果 | 主体大小不变，背景向四周扩散或收缩 |
| 时长 | 通常2-3秒 |
| 情绪 | 震惊、恐惧、眩晕、世界崩塌、空间扭曲 |

**经典案例**：《迷魂记》恐高发作 / 《大白鲨》警长发现鲨鱼 / 《盗梦空间》梦境崩塌

**Seedance写法**：`Dolly Zoom (Vertigo Effect): dolly in + zoom out simultaneously, subject size constant, background warps`

**反向变体**：摄影机向后拉 + 向前推焦 → 产生相反效果（空间收缩感）

**⚠️ AI视频专项修正**：AI无法自动生成希区柯克变焦，必须后期制作或在提示词中精确描述

## 4.4 剪辑型镜头八式

| 镜头类型 | 英文术语 | 定义 | 画面起→终 | Seedance/剪辑标注 |
| --- | --- | --- | --- | --- |
| **主观视角** | POV | 完全模拟角色眼睛所见 | 起：角色视线焦点 → 终：视线移动至新目标 | `POV from [character]'s eyes: gaze fixed on [A], saccade to [B] at Xs` |
| **匹配剪辑** | Match Cut | 前后镜头构图/动作/形状精确匹配 | 起：A时空特写 → 切 → 终：B时空相同构图特写 | `[MATCH CUT: A→B] shape-match on [element], color shift [A]→[B]` |
| **交叉剪辑** | Cross-Cutting | 两个空间交替切换，节奏渐快 | 起：空间A的4s → 空间B的4s → 加速 | `[CROSS-CUT: A↔B] rhythm 4s→3s→2s→1s, converge at climax` |
| **慢镜头** | Slow Motion | 降速至0.25x-0.5x放大关键动作 | 起：动作起势 → 终：力量到达点 | `Speed Ramp 1x→0.3x at impact point, hold 0.3x for Xs, resume 1x` |
| **快切** | Quick Cuts | 单镜头 ≤0.5s连续快速剪辑 | 每个0.3-0.5s镜头独立起→终 | `[QUICK CUTS: 0.3s each] shot1=[action] / shot2=[reaction] / ...` |
| **特写蒙太奇** | Detail Montage | 连续特写并列，强调细节/情绪积累 | 每个特写锁定一个局部 | `[DETAIL MONTAGE] CU1=finger / CU2=ink numbers / CU3=...` |
| **空镜转场** | Establishing/Cutaway | 无人物环境空镜实现时空跳转 | 起：前场景残余情绪 → 终：新场景确立 | `[CUTAWAY TRANSITION] empty shot: [object], Xs, mood=[emotion]` |
| **定格** | Freeze Frame | 动态画面突然冻结为静帧 | 起：角色运动中 → 冻结瞬间 | `[FREEZE FRAME at Xs] hold on [action peak] for Xs` |

## 4.5 焦距与景深镜头（8种）

| 镜头类型 | 定义 | 画面起→终 | Seedance写法 |
| --- | --- | --- | --- |
| **跟焦**(前→后) Rack Focus | 焦点从前景转移至背景 | 起：前景清晰/背景虚 → 终：前景虚/背景清晰 | `Rack focus from foreground [A] sharp to background [B] sharp over Xs` |
| **跟焦**(后→前) | 焦点从背景转移至前景 | 起：背景清晰 → 终：前景清晰 | `Rack focus from background to foreground` |
| **失焦** Defocus | 从清晰逐渐变模糊 | 起：画面锐利 → 终：全面失焦 | `Gradual defocus from sharp to 100% bokeh blur over Xs` |
| **虚焦→实焦** Focus Pull | 从模糊逐渐变清晰 | 起：100%失焦 → 终：画面锐利 | `Focus pull from total blur to crisp focus on [target] over Xs` |
| **浅景深** Shallow DOF | f/1.4-f/2.8极窄景深 | 仅主体清晰，前后奶油状bokeh | `Shallow DOF f/1.8, subject razor-sharp, background creamy bokeh` |
| **深景深** Deep Focus | f/8-f/22全画面清晰 | 前景中景背景全部锐利 | `Deep focus f/11, all planes sharp from 1m to infinity` |
| **推轨变焦** Vertigo/Dolly Zoom | 推轨同时反方向变焦 | 起：正常透视 → 终：人物不变但背景扭曲 | 见4.3希区柯克变焦 |
| **焦点堆叠** Focus Stacking | 同时保持前景和背景清晰 | 全景深锐利 | `Focus stacking: all planes sharp from macro foreground to background` |

## 4.6 景别精确标准（ASC/北电）

| 景别 | 英文 | 精确画面范围 | 叙事功能 | 情绪表达 |
| --- | --- | --- | --- | --- |
| **大远景** | Extreme Wide Shot | 地平线→人物成为一个点 | 展示环境、建立时空关系 | 宏大、孤独、渺小 |
| **远景** | Wide/Long Shot | 环境全景→人物占画面1/10 | 展示人物与环境关系 | 疏离、客观 |
| **全景** | Full Shot | 头顶上方10cm→脚底下方10cm | 展示人物整体动作和位置关系 | 完整、客观 |
| **中全景** | Medium Full Shot | 头顶→膝盖 | 展示上半身动作和对话 | 自然、交流 |
| **中景** | Medium Shot | 头顶→腰部 | 展示动作和表情的结合 | 互动、参与 |
| **中近景** | Medium Close-up | 头顶→胸部 | 展示表情和细微动作 | 亲密、关注 |
| **近景** | Close Shot | 头顶→肩部 | 展示面部表情 | 情感、内心 |
| **特写** | Close-up | 额头→下巴 | 强调人物情绪 | 强烈、冲击 |
| **大特写** | Big Close-up | 眉毛→鼻子 | 强调眼神+眉间肌肉 | 极致、紧张 |
| **极端特写(眼)** | ECU | 仅包含眼睛 | 强调瞳孔反应 | 悬疑、震撼 |
| **极端特写(唇)** | ECU | 仅包含嘴唇 | 唇部微颤/抿合 | 情感压抑 |
| **极端特写(手指)** | ECU | 仅包含手指 | 手部微动作 | 心理泄漏 |
| **极端特写(泪滴)** | ECU | 仅包含一滴眼泪 | 情感的物理化 | 悲伤凝缩 |

**景别叙事规律**：景别逐渐推进 = 情绪逐渐增强；景别逐渐拉远 = 情绪逐渐减弱

**⚠️ AI视频专项修正**：AI经常使用不恰当的景别，如用全景展示表情、用特写展示动作  
**常见错误**：景别跳跃过大；该用特写时用全景；该用全景时用特写

## 4.7 角度与透视镜头

| 角度类型 | 精确参数 | 心理效应 | 适用场景 |
| --- | --- | --- | --- |
| **上帝视角** God's Eye | 极高处垂直向下90° | 全知/客观/宿命/渺小 | 展示全局/悲剧结局 |
| **鸟瞰** Bird's Eye | 从45°高空向下 | 宏大/壮观/渺小 | 城市/自然景观 |
| **大俯拍** High Angle 60° | 高于人物视线60° | 压抑/弱小/无助 | 受害者/失败者 |
| **俯拍** High Angle 30° | 高于人物视线30° | 客观/冷静/优越 | 观察者/上级 |
| **平视** Eye Level | 与人物视线齐平 | 平等/自然/真实 | 日常对话/默认 |
| **仰拍** Low Angle 30° | 低于人物视线30° | 高大/强大/权威 | 英雄/领袖 |
| **大仰拍** Low Angle 60° | 低于人物视线60° | 神圣/不可战胜/恐怖 | 神/怪物/反派 |
| **荷兰角** Dutch Angle 15° | 倾斜15° | 不安/紧张/混乱 | 危险/失衡 |
| **极端倾斜** Dutch Angle 45° | 倾斜45° | 疯狂/混乱/崩溃 | 精神崩溃/疯狂 |

**⚠️ AI视频专项修正**：AI经常使用平视镜头，导致画面平淡缺乏情绪  
**高级技巧**：同一场景中改变镜头角度可表现人物地位变化（对峙→一方被压制→角度翻转）

### 镜头焦距与心理对应

| 焦距 | 透视效果 | 心理暗示 | 适用场景 |
| --- | --- | --- | --- |
| 鱼眼 180° | 极端畸变 | 梦境/幻觉/疯狂 | 意识扭曲入口 |
| 超广角 14-24mm | 空间夸张/近大远小 | 孤独/开阔/压迫 | 大殿/庭院空间感 |
| 广角 24-35mm | 轻微透视变形 | 自然环境+人物关系 | 场景确立镜头 |
| 标准 50mm | 最接近人眼 | 客观/真实/自然 | 纪实感段落 |
| 中长焦 85mm | 轻微压缩 | 亲密/柔美/情感 | 情感对话/人像特写 |
| 长焦 135-200mm | 明显压缩/背景扁平 | 窥视/疏离/压迫 | 远距离观察 |
| 超长焦 200mm+ | 极端压缩 | 监视/跟踪/距离感 | 冷眼旁观 |

## 4.8 构图与关系镜头（9种）

| 镜头类型 | 定义 | 画面构成 | 适用场景 |
| --- | --- | --- | --- |
| **过肩镜头** OTS | 一人肩膀前景虚+另一人脸清晰 | 肩膀占画面1/3 | 对话标配 |
| **双人过肩** | 两人同时可见的过肩 | 两人各占画面侧 | 双人对话 |
| **正反打** Shot-Reverse-Shot | 严格遵守180°轴线的对切 | A面→B面交替 | 对话标配 |
| **越轴** Crossing the Line | 故意打破180°轴线 | 空间关系突然错乱 | 精神崩溃/空间扭曲 |
| **双人镜头** Two-Shot | 同框包含两个主要人物 | 两人同时可见 | 对立/对话 |
| **群像镜头** Group Shot | 5人以上同框 | 全部人物关系展示 | 议事/群戏 |
| **视线匹配** Eyeline Match | 前镜头角色看→后镜头角色所见 | A看→cut→A所见之物 | 揭示注视对象 |
| **动作匹配** Action Match | 动作在剪辑点无缝衔接 | A景别动作→cut→B景别同一动作继续 | 动作无缝接续 |
| **形状匹配** Graphic Match | 前后画面形状/构图对应 | 圆形→圆形/线条→线条 | 匹配转场 |

## 4.9 转场完整体系（13种）

| 转场类型 | 定义 | 适用场景 | Seedance/剪辑标注 |
| --- | --- | --- | --- |
| **硬切** Hard Cut | 直接切换无过渡 | 95%默认剪辑 | `[CUT]` |
| **淡入** Fade In | 从黑屏渐变为画面 | 集头/大段落起始 | `[FADE IN from black, Xs]` |
| **淡出** Fade Out | 从画面渐变为黑屏 | 集尾/大段落结束 | `[FADE OUT to black, Xs]` |
| **叠化** Dissolve | A画面与B画面交叉融合 | 时间流逝/梦境过渡 | `[DISSOLVE A→B, Xs]` |
| **白闪** White Flash | 瞬间白屏再切下一镜 | 爆炸/闪光/记忆闪回 | `[WHITE FLASH 0.1s → next shot]` |
| **黑闪** Black Flash | 瞬间黑屏再切下一镜 | 晕厥/打击/时间跳跃 | `[BLACK FLASH 0.1s → next shot]` |
| **甩转场** Whip Transition | 通过甩镜头运动模糊转场 | 同一空间快速切换对象 | `[WHIP TRANSITION 0.2s blur → next]` |
| **匹配转场** Match Transition | 匹配动作/形状/色彩无缝转场 | 时空转换的优雅连接 | `[MATCH CUT: A→B, match on eye/shape]` |
| **跳切** Jump Cut | 同一镜头内的时间跳跃 | 强调时间省略/焦躁感 | `[JUMP CUT: skip Xs]` |
| **声音桥** Sound Bridge | 下一场景声音先于画面出现 | 预示下一场景 | `[SOUND BRIDGE: B's dialogue starts over A's image]` |
| **音乐桥** Music Bridge | 音乐贯穿两个场景转换 | 情绪延续跨场景 | `[MUSIC BRIDGE: BGM continues across scenes]` |
| **划像转场** Wipe | 新画面从一侧推入 | 风格化/复古/漫画感 | `[WIPE: left-to-right / diagonal]` |
| **插入转场** Insert Cut | 插入细节镜头再切回 | 强调关键道具/时间标记 | `[INSERT: detail shot of [object], Xs]` |

## 4.10 镜头使用铁律

```
【起终点强制标注规则】
每次使用任何镜头类型，分镜表和视频提示词必须完整标注：
  镜头类型 + 起点画面描述 + 运动过程 + 终点画面描述 + 持续时间

✅ 正确示例：
  "推镜头：起于角色全身站立于门槛处（占画面1/3居中）→ 
   匀速推进2.5s → 终于面部特写（双眼占画面横向60%），
   景深从f/4渐变至f/1.8"

❌ 错误示例：
  "推镜头对准角色"（无起点、无终点、无持续时间、无速度）

【运动铁律】
1. 所有镜头运动必须有缓入缓出（Ease In/Out），禁止线性运动
2. 优先弧线路径，直线运动需明确标注
3. 运动速度必须标注（匀速/加速/减速/Speed Ramp）
```
