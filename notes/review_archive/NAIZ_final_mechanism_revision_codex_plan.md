# NAIZ 项目最终取长补短建议：给 Codex / Claude Code 的执行版

> 目的：本文件整合 GPT、Claude Code 与当前项目 notes 的 review，形成一个可以直接交给 Codex 执行的最终修订方案。核心任务不是重写论文正文，而是更新项目 notes、README、变量定义、实证假设和实证设计，使项目从“NAIZ 单一政策评估”升级为“AI 产业政策叠加、地方竞争与创新质量”的可发表研究。

---

## 0. 最终结论

当前项目不应写成：

> NAIZ 导致重复建设和内卷浪费。

这条因果链太强，也不符合政策事实。NAIZ 本身是工信部国家人工智能创新应用先导区，主要是国家级 AI 应用和产业落地平台，并不等同于算力券、模型券、智算中心建设，也不能被直接解释为重复建设的政策原因。

最终建议改写为：

> 本文不将 NAIZ 视为重复建设的单一原因，而将其视为地方政府进入 AI 产业政策竞赛的制度性入口。NAIZ 可能通过应用场景开放、AI 企业集聚、人才匹配、算力可得性和知识溢出提升本地 AI 创新质量；但在地方政府竞争和多重政策叠加条件下，NAIZ 城市以及其周边竞争城市可能进一步叠加算力券、模型券、智算中心等供给侧政策工具。当算力供给扩张超过本地 AI 企业、AI 人才、AI 收入、应用场景和研发能力能够吸收的需求基础时，政策效果可能从集聚效率转向供需错配、重复建设和创新质量边际收益下降。

简言之，论文主线应从：

```text
NAIZ → 重复建设 → 创新质量下降
```

改为：

```text
NAIZ 作为制度入口
→ 地方政府 AI 政策响应增强
→ 算力供给侧政策叠加
→ 算力供给相对 AI 需求基础过剩
→ NAIZ 的创新质量促进效应被削弱
→ 该效应在空间竞争和企业异质性中进一步体现
```

---

## 1. 对 GPT / Codex 和 Claude Code review 的取舍

### 1.1 应保留 GPT / Codex 的部分

GPT / Codex 的核心判断是正确的：

1. **不能把 NAIZ 写成重复建设的唯一原因。**
2. **NAIZ 应定位为制度入口、政策信号或政策竞赛平台。**
3. **重复建设来自 NAIZ 与其他 AI、数字经济和算力政策叠加后的地方竞争。**
4. **必须区分 `NAIZ_it`、`AI_ExperimentZone_it`、`ComputeSubsidy_it`、`ComputeCapacity_it`。**
5. **政策文本相似度不能单独解释为低效率竞争，只能作为机制或稳健性证据。**
6. **空间计量应服务于区分邻近溢出与邻近竞争，而不是技术堆砌。**

这些判断与当前项目 notes 的方向一致，应写入 `01_项目定位.md`、`03_理论框架.md`、`04_实证假设.md` 和 `05_变量与数据.md`。

### 1.2 应保留 Claude Code 的部分

Claude Code 的关键贡献是指出 GPT / Codex 初始方案中的几个技术问题，其中最重要的是：

1. **`PolicyStack_it` 不能包含 `NAIZ_it` 后再与 `NAIZ_it` 交互。**  
   如果 `PolicyStack_it = NAIZ_it + AI_ExperimentZone_it + ...`，那么 `NAIZ_it × PolicyStack_it` 包含 `NAIZ_it²`，会带来严重的自我指涉和多重共线性问题。

2. **政策叠加不能只用政策数量衡量。**  
   更重要的是“算力供给相对本地 AI 需求是否过剩”。因此应构造 `ComputeStack_it` 和 `SupplyExcess_it`。

3. **企业层面异质性值得加入。**  
   城市层面创新质量可能掩盖分配效应。大型在位 AI 企业可能更容易获得算力补贴和基础设施服务，中小企业可能承担人才、算力和竞争压力，导致创新质量损失集中于中小企业。

这些内容应保留，但作为“增强版本”而非一开始就强行写成所有贡献。

### 1.3 应降级或暂不采用 Claude Code 的部分

Claude Code 的一些建议太重，不宜作为主方案：

1. **不要把干部锦标赛写成标题级主理论。**  
   干部锦标赛可以作为解释地方政府为何追逐 AI、算力和可见绩效指标的制度背景，但不能替代本文的主理论。本文主理论仍应是“地理集中 vs. 地理扩散”“地点导向产业政策”“政策叠加与地方竞争”。

2. **不要把 spatial RDD 写成主识别。**  
   NAIZ 城市与非 NAIZ 城市的边界不是随机断点，空间 RDD 的识别前提很难成立。

3. **不要把 Bartik IV 写成主识别。**  
   若工具变量由 AI 专利存量、重点大学数量、城市等级等预测 NAIZ 获批，排除限制很难成立，因为这些变量本身直接影响 AI 创新质量。

4. **不要把 IV mediation 写成主设计。**  
   以 `NAIZ_it × ComputeStack_it` 作为 `SupplyExcess_it` 的工具变量很可能不满足排除限制，因为该交互项可能通过人才、企业集聚、财政关注、政策资源配置等渠道直接影响创新质量。

5. **不要把合成控制法替代所有 DID。**  
   可以做 generalized synthetic control 或 synthetic DID 作为稳健性，但主文仍应使用多期 DID / stacked DID / Sun-Abraham / Callaway-Sant’Anna。

---

## 2. 最终论文定位

### 2.1 一句话定位

> 本文研究国家人工智能创新应用先导区（NAIZ）是否提升城市 AI 创新质量，并进一步检验在多重 AI / 数字 / 算力政策叠加与地方竞争下，算力供给侧扩张是否因超出本地 AI 需求基础而削弱 NAIZ 的创新质量效应。

### 2.2 更经济学化的定位

> 本文将 NAIZ 视为一种 AI 领域的地点导向产业政策，研究其在集聚效率、政策叠加和地方竞争之间的权衡。不同于仅检验政策平均效应的既有研究，本文关注当多个城市同时围绕 AI、算力券、模型券和智算中心展开供给侧政策竞争时，政策效果是否由创新促进转向供需错配和边际效率损失。

### 2.3 推荐标题

#### 中文标题，稳妥版

> 人工智能产业政策叠加、地方竞争与创新质量：来自国家人工智能创新应用先导区的证据

#### 中文标题，突出算力版

> 人工智能产业政策叠加、算力供给错配与创新质量：来自国家人工智能创新应用先导区的证据

#### 英文标题，稳妥版

> AI Industrial Policy Layering, Local Competition, and Innovation Quality: Evidence from China’s National AI Application Zones

#### 英文标题，突出算力版

> AI Compute Policy Layering, Supply-Side Excess, and Innovation Quality: Evidence from China’s National AI Application Zones

### 2.4 不建议使用的标题

不要使用：

```text
National AI Innovation Zones and Wasteful Duplication
```

原因：

1. 因果过强。
2. 暗示 NAIZ 本身导致浪费。
3. 没有体现多重政策叠加。
4. 审稿人容易质疑政策事实。

---

## 3. 最终理论框架

### 3.1 核心张力：地理集中 vs. 地理扩散

本文理论框架仍以“地理集中 vs. 地理扩散”为主。

| 策略 | 收益 | 代价 |
|---|---|---|
| 地理集中 | 规模经济、AI 人才集聚、知识溢出、智算中心利用率提高、高质量创新 | 区域不平等和 AI 可及性差异可能扩大 |
| 地理扩散 | 扩大 AI 技术可及性、降低区域不平等、促进更多城市参与 AI 应用 | 同质化布局、重复建设、低利用率、算力补贴竞争、创新质量边际收益下降 |

理论关键不是简单的“效率 vs. 公平”，而是：

> 在中国地方政府竞争语境下，地理扩散可能从“扩大技术可及性”转化为“竞争驱动的同质化供给侧扩张”。

### 3.2 正向机制

NAIZ 可能通过以下渠道提高 AI 创新质量：

1. **应用场景开放**：地方政府开放政务、制造、交通、医疗、金融等 AI 应用场景，提升 AI 技术商业化和反馈学习。
2. **AI 企业集聚**：政策身份提高城市对 AI 企业的吸引力，形成产业集聚。
3. **人才匹配**：AI 人才市场变厚，企业更容易匹配算法工程师、数据科学家和 AI 应用人才。
4. **算力可得性提高**：算力券、模型券、智算中心等降低 AI 训练、推理和应用成本。
5. **知识溢出**：AI 创新具有强互动性，地理集聚促进知识扩散和高质量专利形成。

### 3.3 负向机制

NAIZ 的负向效应不是来自 NAIZ 本身，而是来自地方政策执行中的供给侧叠加和同质化竞争：

1. **政策信号放大**：NAIZ 批复提升 AI 作为地方产业政策重点的显著性。
2. **地方政策跟进**：地方政府可能通过算力券、模型券、智算中心、AI 产业基金和示范项目快速表态。
3. **周边政策模仿**：相邻城市或同等级城市担心在 AI 竞赛中落后，跟进类似政策工具。
4. **供需错配**：算力供给增长快于本地 AI 企业、AI 人才、AI 收入和真实应用场景需求。
5. **创新质量下降或边际效应减弱**：企业更多响应补贴资格、政策口径和建设规模指标，而非高质量原创创新。

### 3.4 干部锦标赛的定位

干部锦标赛可以作为制度背景，但不宜成为主标题和唯一理论。建议写成：

> 在地方政府竞争和可见绩效指标压力下，AI、算力中心、智算中心和政策文件数量等可观察指标可能成为地方政府展示政策响应能力的工具。这一制度环境有助于解释为什么地方政府可能采用相似的 AI 供给侧政策，即使这些政策未必与本地 AI 需求基础完全匹配。

也就是说：

- 可以用干部锦标赛解释“为什么政策叠加会发生”；
- 不要把干部锦标赛写成论文唯一理论；
- 不要在没有官员数据时把干部晋升竞争写成核心实证贡献。

---

## 4. 最终假设体系

### H1：NAIZ 的本地创新质量效应

> **H1**：作为国家级 AI 应用政策平台，NAIZ 通过应用场景开放、AI 企业集聚、人才匹配、算力可得性和知识溢出，提高本地 AI 创新质量。

预期：`NAIZ_it` 的系数为正。

### H2：NAIZ 与算力供给侧政策叠加

> **H2**：NAIZ 获批后，地方政府更可能出台算力券、模型券、智算中心等供给侧政策工具；该效应在周边城市 AI 政策竞争更强时更明显。

预期：`NAIZ_it` 对 `ComputeStack_it`、`ComputeSubsidy_it`、`ComputeCapacity_it` 有正向影响。

### H3：供需错配削弱创新质量效应

> **H3**：在算力供给相对本地 AI 需求基础更高、供需错配更严重的城市中，NAIZ 对 AI 创新质量的促进效应被削弱。

预期：`NAIZ_it × SupplyExcess_it` 或 `NAIZ_it × ComputeStack_it` 的系数为负。

### H4：空间竞争削弱溢出效应

> **H4**：NAIZ 可能对周边城市产生知识溢出，但当周边城市也采取相似算力供给侧政策时，正向溢出会被企业、人才和算力需求竞争削弱。

预期：`W_NAIZ_it` 可能为正，但 `W_ComputeStack_it` 或 `NAIZ_it × W_ComputeStack_it` 会削弱本地或周边创新质量。

### H5：企业层面分配效应

> **H5**：算力供给侧叠加造成的创新质量损失主要集中在中小企业、融资约束企业和非核心 AI 企业；大型在位 AI 企业可能因更强政策资源获取能力而部分受益。

预期：负向效应在中小企业、民营企业、融资约束企业、非 AI 核心企业中更明显。

### 假设排序建议

主文中建议保留 H1-H4。H5 根据数据可得性决定是否进入主文。若企业层面数据匹配不充分，H5 可作为扩展分析或未来工作，不应写进摘要主贡献。

---

## 5. 最终变量体系

### 5.1 必须分开编码的政策变量

| 变量 | 定义 | 角色 |
|---|---|---|
| `NAIZ_it` | 城市在工信部 NAIZ 批复当年及之后取 1 | 主处理变量 |
| `AI_ExperimentZone_it` | 城市在科技部 AI 试验区批复当年及之后取 1 | 最高优先级混淆政策控制 |
| `ComputeSubsidy_it` | 城市出台算力券、模型券或算力补贴政策后取 1，或按补贴强度连续编码 | 机制变量 |
| `ComputeCapacity_it` | 智算中心、超算中心、数据中心规模、建设时间或算力能力 | 算力供给变量 |
| `ModelVoucher_it` | 模型券政策变量 | 算力/模型支持工具 |
| `ComputingVoucher_it` | 算力券政策变量 | 算力支持工具 |
| `SmartComputingCenter_it` | 智算中心建设变量 | 算力基础设施 |
| `FTZ_CityZone_it` | 城市内实际设有自贸区片区后取 1 | 同期政策控制 |
| `DigitalPilot_it` | 数字经济试验区或数字经济政策变量 | 同期政策控制 |
| `InnovCity_it` | 创新型城市变量 | 长期创新基础控制 |
| `HighTechZone_i` | 国家高新区变量或高新区数量 | 长期创新平台控制 |

### 5.2 不推荐的变量构造

不要使用以下变量作为交互项：

```text
PolicyStack_it = NAIZ_it
               + AI_ExperimentZone_it
               + DigitalPilot_it
               + FTZ_CityZone_it
               + InnovCity_it
               + ComputeSubsidy_it
               + ComputeCapacity_it
```

然后估计：

```text
Y_it = beta1 * NAIZ_it
     + beta2 * PolicyStack_it
     + beta3 * NAIZ_it * PolicyStack_it
     + ...
```

原因：

1. `PolicyStack_it` 包含 `NAIZ_it`，交互项自我指涉。
2. 系数解释混乱。
3. 容易产生多重共线性。
4. 不能区分 NAIZ 本身与后续政策叠加。

### 5.3 推荐的变量构造

#### 方案 A：非 NAIZ 政策叠加

```text
NonNAIZPolicyStack_it = AI_ExperimentZone_it
                      + DigitalPilot_it
                      + FTZ_CityZone_it
                      + InnovCity_it
                      + HighTechZone_i
```

用途：检验 NAIZ 与其他非 NAIZ 政策身份叠加时，效果是否发生变化。

#### 方案 B：算力供给侧政策叠加，推荐作为核心

```text
ComputeStack_it = ComputeSubsidy_it
                + ModelVoucher_it
                + ComputingVoucher_it
                + SmartComputingCenter_it
```

用途：检验 NAIZ 获批后，地方是否叠加算力供给侧政策，以及这种叠加是否削弱创新质量效应。

#### 方案 C：算力供给过剩指数，推荐作为最强机制变量

```text
SupplyExcess_it = ComputeSupply_it - PredictedComputeDemand_it
```

其中：

```text
PredictedComputeDemand_it = f(AIFirms_pre, AIRevenue_pre, AIPatents_pre, AITalent_pre, UniversityAI_pre, DigitalInfrastructure_pre)
```

可操作版本：

```text
ComputeSupplyIntensity_it = ComputeCapacity_it / (AIFirms_it + 1)
```

或：

```text
ComputeSupplyIntensity_it = ComputeCapacity_it / (AIPatents_pre + 1)
```

或：

```text
ComputeSupplyIntensity_it = ComputeCapacity_it / PredictedAIDemand_it
```

优先级：

1. 若有算力利用率：使用 `Underutilization_it = 1 - UtilizationRate_it`。
2. 若有城市算力规模：使用 `SupplyExcess_it` 或 `ComputeSupplyIntensity_it`。
3. 若只有政策文本：使用 `ComputeStack_it`。
4. 若只有政策数量：仅作为补充机制，不作为核心变量。

---

## 6. 最终实证架构

### Part A：基准政策效应

问题：NAIZ 是否提高 AI 创新质量？

基础模型：

```text
Y_it = beta * NAIZ_it
     + delta * AI_ExperimentZone_it
     + theta * PolicyControls_it
     + gamma * X_it
     + city FE
     + year FE
     + epsilon_it
```

建议方法：

1. 多期 DID；
2. Sun-Abraham 或 Callaway-Sant’Anna；
3. stacked DID；
4. 批次异质性；
5. leave-one-treated-city-out；
6. wild cluster bootstrap；
7. randomization inference；
8. synthetic DID 或 generalized synthetic control 作为强化稳健性。

必要控制：

- `AI_ExperimentZone_it`；
- `FTZ_CityZone_it`；
- `DigitalPilot_it` 或省份 × 年份固定效应；
- `InnovCity_it`；
- `HighTechZone_i` 或高新区数量；
- 城市经济与创新基础控制变量。

### Part B：政策叠加第一阶段

问题：NAIZ 是否伴随地方算力供给侧政策叠加？

模型：

```text
ComputeStack_it = beta * NAIZ_it
                + delta * AI_ExperimentZone_it
                + theta * PolicyControls_it
                + gamma * X_it
                + city FE
                + year FE
                + epsilon_it
```

或：

```text
ComputeCapacity_it = beta * NAIZ_it
                   + delta * AI_ExperimentZone_it
                   + theta * PolicyControls_it
                   + gamma * X_it
                   + city FE
                   + year FE
                   + epsilon_it
```

注意：

- 算力券和模型券很多可能在 2022 年以后出现，应允许滞后。
- 建议使用 `NAIZ_it` 的 1-3 年滞后项检验政策跟进。
- 这一部分不是中介 IV，而是机制证据。

### Part C：核心机制，供给侧叠加是否削弱创新质量

模型 1：ComputeStack 交互

```text
Y_it = beta1 * NAIZ_it
     + beta2 * ComputeStack_it
     + beta3 * NAIZ_it * ComputeStack_it
     + delta * AI_ExperimentZone_it
     + theta * PolicyControls_it
     + gamma * X_it
     + city FE
     + year FE
     + epsilon_it
```

预期：

```text
beta1 > 0, beta3 < 0
```

解释：

> NAIZ 平均上可能提高 AI 创新质量，但当城市叠加更多算力供给侧政策时，NAIZ 的边际创新质量效应下降。

模型 2：SupplyExcess 交互

```text
Y_it = beta1 * NAIZ_it
     + beta2 * SupplyExcess_it
     + beta3 * NAIZ_it * SupplyExcess_it
     + delta * AI_ExperimentZone_it
     + theta * PolicyControls_it
     + gamma * X_it
     + city FE
     + year FE
     + epsilon_it
```

预期：

```text
beta3 < 0
```

解释：

> 在算力供给相对 AI 需求基础更高的城市中，NAIZ 的创新质量促进效应更弱，说明政策叠加可能带来供需错配和边际效率损失。

### Part D：空间竞争与空间溢出

空间模型应采用 SLX / 空间暴露 DID，不建议把 SDM 作为主模型。

基准空间模型：

```text
Y_it = beta * NAIZ_it
     + theta * W_NAIZ_it
     + phi * W_ComputeStack_it
     + mu * NAIZ_it * W_ComputeStack_it
     + delta * AI_ExperimentZone_it
     + eta * W_AI_ExperimentZone_it
     + gamma * X_it
     + city FE
     + year FE
     + epsilon_it
```

其中：

- `W_NAIZ_it`：邻近 NAIZ 暴露；
- `W_ComputeStack_it`：周边算力供给侧政策暴露；
- `W_AI_ExperimentZone_it`：周边科技部 AI 试验区暴露；
- `W` 基准使用纯地理距离矩阵或固定距离带。

权重矩阵优先级：

1. 200/300 km 内反距离矩阵；
2. 100/200/300/500 km 距离带；
3. k 近邻矩阵；
4. 同省矩阵；
5. 地理距离 × 政策前产业相似度；
6. 地理距离 × 政策文本相似度。

注意：

- 基准权重必须使用相对外生的地理权重。
- 复合权重矩阵只能作为机制或稳健性。
- 政策文本相似度不能作为基准空间矩阵。

### Part E：企业层面分配效应

若数据允许，应加入企业层面分析。

企业层面模型：

```text
Y_fict = beta1 * NAIZ_ct
       + beta2 * ComputeStack_ct
       + beta3 * NAIZ_ct * ComputeStack_ct
       + gamma * FirmControls_fct
       + firm FE
       + industry-year FE
       + epsilon_fict
```

异质性：

1. 企业规模：大型企业 vs. 中小企业；
2. 所有制：国企 vs. 民企；
3. 融资约束：高 SA/KZ/WW 指数 vs. 低融资约束；
4. AI 基础：政策前 AI 专利企业 vs. 非 AI 专利企业；
5. 行业属性：AI 核心行业 vs. AI 应用行业 vs. 非 AI 行业。

预期：

- 大型在位企业更可能受益；
- 中小企业、融资约束企业和非核心 AI 企业更可能受损；
- 这能揭示城市层面汇总结果无法识别的分配效应。

---

## 7. 结果变量建议

### 7.1 主结果变量

主结果应尽量使用 AI 创新质量，而不是专利数量。

| 变量 | 定义 | 优先级 |
|---|---|---|
| `AI_PatNovelty` | AI 专利新颖性，可基于技术组合新颖性、CPC 分散度或文本新颖性 | 高 |
| `AI_PatCite` | 标准化前向被引次数 | 高，但需处理右侧截尾 |
| `AI_PatGrant` | AI 发明专利授权数 | 中高 |
| `AI_PatOrig` | AI 专利原创性，基于后向引用来源分散度 | 中 |
| `AI_PatGen` | AI 专利一般性，基于被不同技术领域引用广度 | 中，但截尾风险高 |
| `BreakthroughAI` | 高被引或突破性 AI 专利 | 高，但样本可能较少 |

### 7.2 对照结果变量

必须设计对照结果：

1. 非 AI 专利；
2. 全量专利；
3. 外观设计专利；
4. 低质量专利；
5. 非技术密集行业专利；
6. 非 AI 部门 TFP。

用途：排除“城市整体创新趋势提升”或“泛数字政策冲击”。

### 7.3 样本期约束

不能机械使用 2014-2025。

建议：

| 因变量 | 推荐样本期 |
|---|---|
| AI 专利申请量 | 可尝试 2014-2024/2025 |
| AI 专利授权量 | 需考虑授权滞后 |
| AI 专利被引质量 | 若用 3 年前向引用窗口，可能只能到 2021/2022 |
| AI 专利新颖性 | 可到较近年份，但需处理公开和授权滞后 |
| 年报 AI 词频 | 取决于年报覆盖，通常可到 2023/2024 |
| 招聘数据 | 取决于 EPS 或第三方数据 |
| 企业 TFP | 取决于 CSMAR、工企库或税收调查数据 |

---

## 8. 识别风险与应对

### 8.1 处理组少

NAIZ 只有 11 个先导区，城市面板口径约 12 个城市单元。需要：

1. leave-one-treated-city-out；
2. wild cluster bootstrap；
3. randomization inference；
4. 批次分组；
5. 剔除北京、上海、深圳、杭州等超级城市；
6. 剔除直辖市、省会、副省级城市稳健性。

### 8.2 选择性进入

NAIZ 城市本来就是 AI 基础较强城市。需要：

1. 事件研究和预趋势；
2. 政策前 AI 专利趋势匹配；
3. PSM + DID 作为补充；
4. generalized synthetic control 或 synthetic DID；
5. 加入城市线性趋势或省份 × 年份固定效应，视结果稳定性决定。

### 8.3 多重政策叠加

必须控制：

1. 科技部 AI 试验区；
2. 自贸区城市片区变量；
3. 数字经济试验区；
4. 创新型城市；
5. 国家高新区；
6. 省份 × 年份固定效应。

尤其要强调：科技部 AI 试验区是最高优先级混淆政策，必须构造 `AI_ExperimentZone_it`。

### 8.4 NAIZ 不等于算力补贴

论文中必须明确：

> NAIZ 是主政策入口；算力券、模型券、智算中心是地方后续配套政策或政策叠加工具。二者不能混用。

因此：

- `NAIZ_it` 是主处理变量；
- `ComputeSubsidy_it` 是机制变量；
- `ComputeCapacity_it` 是供给变量；
- `SupplyExcess_it` 是重复建设/供需错配代理变量。

### 8.5 空间干扰

普通 DID 的 no-spillover / SUTVA 假设可能不成立。需要：

1. `W_NAIZ_it`；
2. `W_ComputeStack_it`；
3. 距离带宽；
4. donut 检验；
5. 空间 placebo；
6. 高空间暴露城市 vs. 低空间暴露城市的预趋势检验。

---

## 9. 写作中必须避免的表述

### 9.1 不要写

> NAIZ 导致地方重复建设。

改成：

> NAIZ 作为国家级 AI 应用政策平台，可能强化地方政府围绕 AI 产业和算力基础设施的政策响应；在多重政策叠加和相邻城市竞争条件下，这种响应可能表现为同质化供给侧布局和算力供需错配。

### 9.2 不要写

> 算力补贴是 NAIZ 的政策内容。

改成：

> 算力券、模型券和智算中心建设并不等同于 NAIZ 本身，而是地方政府在 NAIZ、科技部 AI 试验区、数字经济政策和产业招商压力下形成的配套政策工具。

### 9.3 不要写

> 政策文本相似度说明低效率竞争。

改成：

> 政策文本相似度本身既可能反映政策学习，也可能反映中央政策扩散；只有当其与地理邻近、产业结构相似、算力补贴趋同和 AI 企业/人才竞争同时出现时，才更接近同质化竞争。

### 9.4 不要写

> 本文证明 AI 算力补贴造成浪费。

改成：

> 本文提供证据表明，在地方政策叠加和周边竞争条件下，算力供给侧扩张可能削弱 NAIZ 的创新质量促进效应，反映出 AI 产业政策从集聚效率转向供需错配的潜在风险。

---

## 10. 需要 Codex 更新的 notes 文件

### 10.1 更新 `01_项目定位.md`

需要加入：

1. NAIZ 是制度入口，不是重复建设唯一原因。
2. 核心问题从“NAIZ 是否有效”升级为“政策叠加与地方竞争如何影响 AI 创新质量”。
3. 加入 `ComputeStack_it` 和 `SupplyExcess_it` 的概念。
4. 将企业层面分配效应写为增强贡献，而非立即作为主贡献。

建议替换的一句话：

> 本文研究工信部国家人工智能创新应用先导区（NAIZ）是否提升城市 AI 创新质量，并进一步检验在地方政府竞争和多重政策叠加下，算力券、模型券、智算中心等供给侧政策扩张是否因超出本地 AI 需求基础而削弱 NAIZ 的创新质量效应。

### 10.2 更新 `03_理论框架.md`

需要加入：

1. “政策信号放大 → 地方政策跟进 → 算力供给侧叠加 → 供需错配”的机制链。
2. 干部锦标赛作为制度背景，不作为主理论标题。
3. 区分正向机制和负向机制。
4. 将“重复建设”定义为“算力供给相对 AI 需求基础过剩”，而非单纯政策数量增加。

### 10.3 更新 `04_实证假设.md`

需要将原 H1-H3 调整为 H1-H5：

1. H1：NAIZ 的本地创新质量效应。
2. H2：NAIZ 是否导致算力供给侧政策叠加。
3. H3：供需错配是否削弱创新质量效应。
4. H4：空间竞争是否削弱溢出效应。
5. H5：企业层面分配效应。

其中 H5 可标注为“若企业层面数据可得，则作为扩展假设”。

### 10.4 更新 `05_变量与数据.md`

需要加入：

1. `ComputeStack_it`；
2. `NonNAIZPolicyStack_it`；
3. `SupplyExcess_it`；
4. `PredictedComputeDemand_it`；
5. `W_ComputeStack_it`；
6. `W_SupplyExcess_it`；
7. 企业层面异质性变量。

并明确禁止将包含 `NAIZ_it` 的 `PolicyStack_it` 与 `NAIZ_it` 交互。

### 10.5 更新 `06_空间计量方案.md`

需要加入：

1. `W_ComputeStack_it` 和 `W_SupplyExcess_it`。
2. 空间竞争不仅是周边 NAIZ 数量，也包括周边算力供给侧政策暴露。
3. 基准空间权重仍使用纯地理距离矩阵。
4. 复合权重矩阵、政策文本相似度、产业相似度只作为机制或稳健性。
5. SDM 仍只作为稳健性，不作为主因果识别。

### 10.6 更新 `07_待办与未确认事项.md`

需要新增任务：

- [ ] 构造 `ComputeStack_it`，包括算力券、模型券、智算中心等供给侧政策工具。
- [ ] 构造 `NonNAIZPolicyStack_it`，不包含 `NAIZ_it`。
- [ ] 明确禁止使用包含 `NAIZ_it` 的 `PolicyStack_it` 与 `NAIZ_it` 交互。
- [ ] 收集或代理城市算力供给规模，用于构造 `ComputeCapacity_it`。
- [ ] 构造 `PredictedComputeDemand_it`，可基于政策前 AI 企业数、AI 专利、AI 招聘、高校 AI 资源、数字基础设施。
- [ ] 构造 `SupplyExcess_it` 或 `ComputeSupplyIntensity_it`。
- [ ] 检查算力券和模型券政策推出时间，允许 NAIZ 后 1-3 年滞后。
- [ ] 若企业层面数据可得，构造企业规模、所有制、融资约束、政策前 AI 基础等异质性变量。

---

## 11. 推荐 README 最终段落

建议将以下段落加入 README 或项目定位文件：

> 本文不将工信部国家人工智能创新应用先导区（NAIZ）视为重复建设的单一原因，而将其视为地方 AI 产业政策竞赛的制度性入口。NAIZ 的政策目标是通过应用场景开放、企业集聚、人才匹配和算力可得性提升 AI 创新质量；但在地方政府竞争和多重政策叠加条件下，NAIZ 可能伴随后续算力券、模型券、智算中心等供给侧政策工具的密集采用。当这些供给侧政策扩张超过本地 AI 企业、AI 人才、AI 收入和应用场景能够吸收的需求基础时，政策效果可能从集聚效率转向供需错配和重复建设。本文的核心问题是：NAIZ 是否提高 AI 创新质量；NAIZ 是否诱发或伴随地方算力供给侧政策叠加；这种供给侧叠加是否通过本地和周边城市竞争削弱 NAIZ 的创新质量效应；以及这种影响是否在企业层面表现出大型在位企业受益、中小企业受损的分配格局。

---

## 12. 最终执行优先级

### 第一优先级：必须做

1. 改写项目定位。
2. 严格区分 NAIZ 与科技部 AI 试验区。
3. 分开编码 `NAIZ_it`、`AI_ExperimentZone_it`、`ComputeSubsidy_it`、`ComputeCapacity_it`。
4. 构造 `ComputeStack_it`。
5. 避免 `PolicyStack_it` 自我指涉。
6. 以 AI 专利质量为主结果。
7. 做多期 DID 与事件研究。
8. 控制其他同期政策。

### 第二优先级：强烈建议做

1. 构造 `SupplyExcess_it` 或 `ComputeSupplyIntensity_it`。
2. 做 NAIZ 对 `ComputeStack_it` 的第一阶段机制检验。
3. 做 `NAIZ_it × ComputeStack_it` 或 `NAIZ_it × SupplyExcess_it` 的核心机制检验。
4. 做空间暴露 DID：`W_NAIZ_it`、`W_ComputeStack_it`。
5. 做 leave-one-treated-city-out 和 randomization inference。
6. 做 synthetic DID 或 generalized synthetic control。

### 第三优先级：有数据再做

1. 企业层面分配效应。
2. 算力利用率或服务对象数据。
3. 政策文本 NLP 分类为供给侧 vs. 需求侧。
4. 官员锦标赛相关异质性。
5. 非 AI 部门 TFP 空间溢出。

---

## 13. 最终对 Codex 的操作指令

请 Codex 按以下规则修改 notes：

1. **不要写论文正文。** 只更新项目 notes、变量表、假设表和实证设计方案。
2. **保留 NAIZ 作为主处理变量，但重新解释为制度入口。**
3. **不要把 NAIZ 写成重复建设的直接原因。**
4. **新增 `ComputeStack_it` 和 `SupplyExcess_it`，并写清楚构造逻辑。**
5. **删除或替换所有包含 `NAIZ_it` 的 `PolicyStack_it × NAIZ_it` 设定。**
6. **把政策文本相似度降级为机制或稳健性检验。**
7. **空间计量继续以 SLX / 空间暴露 DID 为主，SDM 只作为稳健性。**
8. **企业层面分析写为可选增强模块，不要在数据未确认前写成主贡献。**
9. **所有政策事实仍需保留“待核验”状态，尤其是 NAIZ 批复文件、科技部 AI 试验区、算力券、模型券和智算中心。**
10. **更新后的 notes 应避免因果过强措辞，统一使用“可能”“表明”“削弱边际效应”“供需错配风险”等审慎表述。**

---

## 14. 最终一句话

> 最终版本不是“NAIZ 导致内卷浪费”的论文，而是“NAIZ 作为 AI 地点导向产业政策，在地方政策叠加和算力供给侧竞争中如何从集聚效率走向供需错配，并进而影响创新质量”的论文。

