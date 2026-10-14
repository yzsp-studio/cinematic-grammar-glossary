# 附录A｜AI视频专项修正清单（全章汇总）

> 将散布在各章中的所有"⚠️ AI视频专项修正"要点集中于此，方便Skill开发者一站式查阅。

## A.1 构图与轴线

| 编号 | 问题 | 修正方案 |
| --- | --- | --- |
| A-01 | AI不理解180°轴线→对切镜头人物方向跳变 | 在提示词中显式指定人物屏幕方位：`Character A screen-left facing right, Character B screen-right facing left` |
| A-02 | 越轴后观众空间感混乱 | 若必须越轴，插入中性角度过渡镜头（正面/俯瞰/特写） |
| A-03 | 三分法构图时主体偏移到死角 | 明确写 `subject placed at upper-right third intersection` 而非 "off-center" |

## A.2 布光

| 编号 | 问题 | 修正方案 |
| --- | --- | --- |
| A-04 | AI默认均匀平光→无戏剧性 | 必须指定光型+光比：`Rembrandt lighting, key-to-fill ratio 4:1, shadow on camera-left cheek` |
| A-05 | 情绪光源缺失 | 用emotion-lighting表对照：恐惧=底光，悬疑=侧光窄角，温情=柔光低比 |

## A.3 镜头运动

| 编号 | 问题 | 修正方案 |
| --- | --- | --- |
| A-06 | 运镜缺乏缓入缓出→机械感 | 写 `camera pushes in with ease-in over 0.5s → steady → ease-out over 0.3s` |
| A-07 | 弧形运动变成直线平移 | 写 `camera arcs 90° around subject on a curved path` 而非 `camera moves around` |
| A-08 | 希区柯克变焦被忽略 | 同时写推拉+反向变焦：`dolly in + zoom out simultaneously — background warps while subject size stays constant` |

## A.4 场面调度

| 编号 | 问题 | 修正方案 |
| --- | --- | --- |
| A-12 | 多人场景中闲置角色呆立不动 | 为每个可见角色写独立的idle动作：`Background character B fidgets with sleeve; C glances toward door` |
| A-13 | 人际距离不匹配情感关系 | 显式写距离：`characters stand 40cm apart (intimate zone)` 而非 "standing close" |

## A.5 表演指导

| 编号 | 问题 | 修正方案 |
| --- | --- | --- |
| A-22 | 所有反应瞬间发生→缺乏"反应时间" | 注入延迟：`0.3s delay before reaction — processes information then responds` |
| A-23 | 表演缺乏层次(直接从A到B) | 写分阶段表演：`Phase 1(0-0.5s): shock freeze → Phase 2(0.5-1.5s): trembling begins → Phase 3(1.5-3s): tears form` |
| A-24 | 背景角色的反应与主角完全同步 | 为背景角色设定独立的反应延迟和幅度 |

## A.6 通用铁律

| 编号 | 铁律 | 说明 |
| --- | --- | --- |
| A-25 | **禁用情绪形容词作为唯一指令** | "sad""angry""happy"只能作为辅助标签，必须搭配肌肉级/动作级描述 |
| A-26 | **每个可见角色必须有独立指令** | 不能只写主角动作，其他人默认→会呆立 |
| A-27 | **时间码精确到0.1s** | 微表情/眼神/呼吸变化必须标注起止时间 |
| A-28 | **物理真实五禁** | 禁浮空、禁穿模、禁断肢、禁液态衣料、禁静止头发 |
| A-29 | **反AI呆板核心公式** | 延迟+不对称+不完美 = 真实感 |
