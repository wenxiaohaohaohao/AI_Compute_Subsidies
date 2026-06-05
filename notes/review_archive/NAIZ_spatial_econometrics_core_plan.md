# NAIZ 项目空间计量方案：核心建议、变量构造与 notes 更新指令

> 用途：交给 Claude Code / Codex review 后，基于本文件更新项目 notes。  
> 适用项目：NAIZ、AI 算力补贴、地方同质化竞争与创新质量。  
> 核心结论：**空间计量需要做，但不要把 SDM 作为主模型。主空间设计应采用“空间暴露 DID / SLX”，SDM 作为稳健性或补充。**

---

## 0. 一句话结论

这个项目需要空间计量，但空间计量不应成为技术堆砌。

最合适的主线是：

> **基准模型仍然是多期 DID / 事件研究；空间部分用“空间暴露 DID / SLX”检验两个核心问题：一是 NAIZ 是否对邻近城市有知识溢出，二是邻近城市同质化布局是否削弱本地 NAIZ 的创新质量效应。SDM 可以作为稳健性或补充，不建议一开始作为主模型。**

原因是：项目的核心问题不是一般意义上的“空间相关”，而是一个明确的政策经济学问题：

> **NAIZ 是地点导向型政策；算力补贴和智算中心既可能产生邻近知识溢出，也可能产生邻近竞争和资源争夺。**

因此，空间计量的意义不是“模型更高级”，而是为了区分：

1. 本地 NAIZ 政策效应；
2. 周边 NAIZ 的知识溢出；
3. 周边同质化算力补贴竞争；
4. 空间资源错配或虹吸效应。

---

## 1. 为什么这个项目需要空间计量？

### 1.1 普通 DID 的隐含假设

普通 DID 通常隐含一个强假设：

> 一个城市是否被设为 NAIZ，只影响这个城市自己，不影响其他城市。

这就是通常所说的 **SUTVA / no interference assumption**，即不同单位之间没有处理干扰。

但这个项目的问题本身不满足这个假设。NAIZ 和 AI 算力补贴天然具有跨城市影响。

| 空间机制 | 在本项目中的含义 | 对普通 DID 的威胁 |
|---|---|---|
| 知识溢出 | NAIZ 城市的 AI 企业、人才、专利知识可能扩散到周边城市 | 对照组被污染，导致 DID 系数低估或误估 |
| 资源竞争 | 邻近城市同时发算力券、建智算中心、抢企业和人才 | 本地政策效应被周边竞争削弱 |
| 政策模仿 | 地方政府互相学习/模仿算力补贴政策 | 政策变量不再是孤立冲击 |
| 空间再分配 | NAIZ 可能把企业、人才、算力需求从周边城市吸走 | 本地效应不等于全国净效应 |

所以不能只问：

```text
NAIZ_it 是否影响 Y_it？
```

还要问：

```text
邻近城市的 NAIZ_jt 是否影响 Y_it？
邻近城市的算力补贴竞争是否削弱本地 NAIZ_it 的影响？
```

这就是空间计量在本项目中的必要性。

---

## 2. 空间计量的经济学意义

空间计量不是一个技术装饰，而是把论文从普通政策评估推进到 **空间政策评估**。

### 2.1 对应地点导向政策文献：本地效应不等于全国净效应

Kline and Moretti 关于地点导向政策的研究提醒我们：一个政策可能对受支持地区产生正向本地效应，但这不等于它在全国层面创造了净增量。部分本地增长可能来自其他地区的企业、劳动力或投资转移。

换到本项目：

> NAIZ 可能显著提高本地 AI 专利质量，但这不一定意味着全国 AI 创新质量提升。它可能只是把企业、人才和算力需求从周边城市吸引到 NAIZ 城市。

空间计量可以区分几种情形：

| 估计结果 | 政策含义 |
|---|---|
| 本地效应为正，邻近溢出也为正 | NAIZ 可能创造区域创新净增量 |
| 本地效应为正，邻近效应为负 | 可能存在虹吸效应或空间挤出 |
| 本地效应为正，但竞争越强效果越弱 | NAIZ 有效，但被同质化竞争稀释 |
| 本地效应不显著，邻近效应显著 | NAIZ 更像区域公共品，而不是单纯本地政策 |

### 2.2 对应最优空间政策文献：集中与扩散之间存在权衡

Fajgelbaum and Gaubert 的最优空间政策框架强调，空间政策是否有效取决于：

1. 地点间生产率差异；
2. 空间溢出的福利价值；
3. 企业和劳动者的空间分选；
4. 政策对不同地区资源配置的影响。

换到本项目：

- 如果 AI 创新溢出主要集中在高生产率城市，那么过度分散算力补贴可能降低效率；
- 如果 AI 技术可以通过邻近扩散带动非 AI 部门 TFP，那么一定程度的地理扩散也可能有政策价值；
- 如果地方政府同质化布局智算中心，导致重复建设和利用率下降，则扩散可能产生效率损失。

这正好对应项目的理论张力：

> 地理集中带来规模经济、人才匹配和知识溢出；地理扩散降低区域不平等但可能引发同质化竞争和重复建设。

### 2.3 对应知识溢出文献：AI 创新天然具有空间衰减

Jaffe, Trajtenberg and Henderson 使用专利引用研究知识溢出的地理本地化；Audretsch and Feldman 将创新地理集中与 R&D 溢出联系起来；Duranton and Puga 将城市集聚机制分解为 sharing、matching、learning。

AI 算力和 NAIZ 机制可以对应为：

| 集聚机制 | 在 AI / 算力政策中的含义 |
|---|---|
| Sharing | 智算中心、GPU 集群、公共算力平台具有高固定成本，集中部署有利于提高利用率 |
| Matching | AI 人才、算法工程师、数据科学家和企业需求在大城市更容易匹配 |
| Learning | AI 模型应用、算法优化、场景落地具有隐性知识，依赖企业间交流和人才流动 |

因此，空间计量可以检验：

> NAIZ 的知识溢出是否存在？如果存在，距离多远后衰减？这种溢出是否会被邻近城市之间的同质化竞争抵消？

---

## 3. 最核心的实证建议：主模型用空间暴露 DID / SLX

### 3.1 推荐主空间模型

推荐主空间模型：

```text
Y_it = α_i + λ_t + β NAIZ_it + θ W_NAIZ_it + γ X_it + δ W_X_it + ε_it
```

其中：

| 符号 | 含义 |
|---|---|
| `Y_it` | 城市 i 在年份 t 的结果变量，例如 AI 专利质量、非 AI 部门 TFP |
| `NAIZ_it` | 城市 i 是否已获批 NAIZ |
| `W_NAIZ_it` | 邻近城市 NAIZ 暴露度，即周边城市 NAIZ 状态的空间加权平均 |
| `X_it` | 城市控制变量 |
| `W_X_it` | 邻近城市控制变量的空间加权值 |
| `α_i` | 城市固定效应 |
| `λ_t` | 年份固定效应 |
| `ε_it` | 误差项 |

这个模型本质上是 **SLX model / spatially lagged X model**，也可以理解为 **空间暴露 DID**。

### 3.2 为什么不用 SDM 作为主模型？

SDM 的形式是：

```text
Y_it = ρ W Y_it + β NAIZ_it + θ W_NAIZ_it + γ X_it + δ W_X_it + α_i + λ_t + ε_it
```

它比 SLX 多了 `W Y_it`，即邻近城市结果变量的空间滞后。

问题在于：

1. `W Y_it` 很难做因果解释；
2. 邻近城市的 AI 专利质量和本城市 AI 专利质量可能同时受共同省级政策、共同产业周期、共同人才流动、共同宏观冲击影响；
3. 加入 `W Y_it` 后，系数本身不再等于简单边际效应，需要报告直接效应、间接效应和总效应；
4. 对博士论文或期刊论文来说，如果主识别目标是 NAIZ 的政策效应，SDM 容易被审稿人认为是“模型复杂但识别不清”。

因此，推荐排序如下：

| 模型 | 是否建议作为主模型 | 原因 |
|---|---|---|
| 普通 DID | 是，作为基准 | 识别本地 NAIZ 效应 |
| 空间暴露 DID / SLX | 是，作为主空间模型 | 直接检验邻近 NAIZ 暴露和竞争 |
| SDM | 否，作为稳健性 | 可分解直接、间接、总效应，但解释更复杂 |
| SAR / SEM | 否，作为诊断或补充 | 更偏空间相关修正，不直接对应理论机制 |

---

## 4. 空间权重矩阵怎么构造？

### 4.1 基准权重矩阵：纯地理距离矩阵

基准建议使用 **纯地理距离矩阵**，而不是政策相似度矩阵。

设城市 i 和城市 j 的球面距离为 `dist_ij`。设置距离阈值 R，例如 300 km：

```text
w_ij = 1(dist_ij ≤ R) / N_i
w_ii = 0
```

其中 `N_i` 是城市 i 在 R 公里内的邻近城市数量。

也可以使用反距离权重：

```text
w_ij = (1 / dist_ij) / Σ_j (1 / dist_ij),  if dist_ij ≤ R
w_ij = 0,                                  if dist_ij > R
w_ii = 0
```

### 4.2 为什么基准使用地理距离？

因为地理距离相对外生。政策文本相似度、产业结构相似度、算力券强度都可能内生：

- AI 基础强的城市更可能出台相似政策；
- AI 基础强的城市也更可能产生高质量专利；
- 产业结构相似可能反映长期发展路径，而不是政策竞争本身；
- 政策文本相似可能是政策学习，也可能是同质化竞争。

因此，基准模型应使用相对外生的地理距离矩阵；政策相似度和产业相似度矩阵适合放在机制检验或稳健性部分。

### 4.3 推荐矩阵清单

| 权重矩阵 | 用途 | 是否作为基准 |
|---|---|---|
| 300 km 内反距离矩阵 | 基准空间暴露 | 是 |
| 100 km、200 km、500 km 距离带 | 检验空间衰减 | 稳健性 |
| k 近邻矩阵 | 避免东西部城市密度差异 | 稳健性 |
| Queen 邻接矩阵 | 空间自相关基准 | 诊断或稳健性 |
| 同省矩阵 | 检验省内政策竞争 | H2 补充 |
| 地理距离 × 产业相似度 | 检验产业竞争机制 | H2 机制 |
| 地理距离 × 政策文本相似度 | 检验算力补贴同质化 | H2 机制 |
| 复合矩阵 | 综合稳健性 | 不建议作为主模型 |

---

## 5. 关键变量怎么构造？

### 5.1 本地 NAIZ 处理变量

```text
NAIZ_it = 1{city i 在 t 年或之前获批 NAIZ}
```

注意事项：

1. 济南—青岛联合体在城市 panel 中应分别给济南和青岛赋值；
2. 上海浦东新区若数据是上海市口径，应说明按上海市处理；
3. 天津滨海新区若数据是天津市口径，应说明按天津市处理；
4. 稳健性中可以剔除直辖市或只保留明确地级市样本。

### 5.2 邻近 NAIZ 暴露变量

```text
W_NAIZ_it = Σ_j w_ij NAIZ_jt
```

解释：

> `W_NAIZ_it` 越高，说明城市 i 周边已经有越多 NAIZ 城市，或者距离更近的 NAIZ 城市权重更高。

例子：

- 如果合肥附近南京、杭州、上海都已获批 NAIZ，则合肥的 `W_NAIZ_it` 较高；
- 如果一个西部城市周边 300 km 内没有 NAIZ，则 `W_NAIZ_it = 0`。

这个变量用于 H3，也可以用于检验普通 DID 的对照组是否被空间溢出污染。

### 5.3 空间竞争强度变量

H2 的核心不是简单的 `W_NAIZ_it`，而是：

```text
Comp_it = Σ_j w^comp_ij NAIZ_jt
```

其中 `w^comp_ij` 不仅表示距离，还要反映“竞争相关性”。

#### 5.3.1 地理竞争

```text
Comp_geo_it = Σ_j w^geo_ij NAIZ_jt
```

解释：

> 周边 NAIZ 越多，竞争越强。

优点：外生性较好。  
缺点：不能区分知识溢出和竞争。

#### 5.3.2 地理 × 产业相似

```text
SimIndustry_ij = cosine(IndustryShare_i, IndustryShare_j)

w^comp_ij = w^geo_ij × SimIndustry_ij

Comp_ind_it = Σ_j w^comp_ij NAIZ_jt
```

解释：

> 如果两个城市距离近，而且 AI/ICT 产业结构相似，那么它们更可能争夺同一批企业、人才和算力需求。

注意：产业结构相似度应使用政策前数据构造，例如 2015—2018 年平均值，以降低内生性。

#### 5.3.3 地理 × 算力补贴政策相似

```text
PolicySim_ij,t = cosine(TextVector_i,t, TextVector_j,t)
```

或者：

```text
PolicySim_ij,t = 1 - |SubsidyRate_i,t - SubsidyRate_j,t|
```

进一步构造：

```text
w^comp_ij,t = w^geo_ij × PolicySim_ij,t

Comp_policy_it = Σ_j w^comp_ij,t NAIZ_jt
```

解释：

> 如果邻近城市的算力券补贴比例、补贴上限、对象、使用场景、模型券规则高度相似，则政策竞争或政策模仿更强。

优点：最贴近“同质化算力补贴竞争”。  
缺点：内生性最强，不建议作为基准，只适合机制检验。

### 5.4 空间算力补贴暴露变量

如果能系统编码算力券、模型券和智算中心政策，可以构造：

```text
ComputeSubsidy_it = 1{city i 在 t 年有算力券/模型券/算力补贴政策}
```

然后构造：

```text
W_ComputeSubsidy_it = Σ_j w_ij ComputeSubsidy_jt
```

解释：

> 周边城市算力补贴政策越密集，本城市面对的政策竞争或区域算力供给环境越强。

这个变量可以用于 H2，也可以用于 H3 的机制讨论。

---

## 6. H2：同质化竞争效应怎么估计？

### 6.1 核心问题

H2 要回答：

> 当周边 NAIZ 或周边算力补贴竞争更强时，本地 NAIZ 对 AI 创新质量的促进效应是否变弱？

### 6.2 推荐模型

```text
Y_it = α_i + λ_t 
     + β NAIZ_it
     + μ NAIZ_it × Comp_it
     + γ X_it
     + ε_it
```

其中：

| 系数 | 解释 |
|---|---|
| `β` | 当竞争强度为 0 时，NAIZ 对本地 AI 创新质量的影响 |
| `μ` | 竞争强度对 NAIZ 效应的调节作用 |
| 预期 | `β > 0`, `μ < 0` |

如果 `μ < 0`，说明：

> NAIZ 本身可能促进 AI 创新质量，但当周边城市也在同质化布局 AI 算力补贴和智算中心时，政策效果会被削弱。

### 6.3 H2 变量替换顺序

建议按以下顺序替换 `Comp_it`：

| 顺序 | 竞争变量 | 作用 |
|---|---|---|
| 1 | `Comp_geo_it` | 最简单、最外生的邻近 NAIZ 密度 |
| 2 | `Comp_ind_it` | 产业结构相似下的竞争 |
| 3 | `W_ComputeSubsidy_it` | 周边算力补贴政策密度 |
| 4 | `Comp_policy_it` | 政策文本/补贴标准相似度 |

不建议把所有交互项一次性放入主回归。主文应保持简洁，机制部分逐步替换。

---

## 7. H3：知识溢出效应怎么估计？

### 7.1 核心问题

H3 要回答：

> NAIZ 城市是否对周边非 NAIZ 城市的非 AI 部门 TFP 产生正向溢出？

### 7.2 推荐模型一：全样本 SLX

```text
NonAI_TFP_it = α_i + λ_t
             + β NAIZ_it
             + θ W_NAIZ_it
             + γ X_it
             + ε_it
```

其中：

| 系数 | 解释 |
|---|---|
| `β` | 本地 NAIZ 对本地非 AI 部门 TFP 的影响 |
| `θ` | 邻近 NAIZ 对本地非 AI 部门 TFP 的空间溢出 |

### 7.3 推荐模型二：仅非 NAIZ 城市样本

更干净的 H3 设定是只保留非 NAIZ 城市：

```text
NonAI_TFP_it = α_i + λ_t
             + θ W_NAIZ_it
             + γ X_it
             + ε_it
```

解释：

> 一个非 NAIZ 城市靠近 NAIZ 城市以后，非 AI 部门企业 TFP 是否提高？

系数解释：

| `θ` 符号 | 含义 |
|---|---|
| `θ > 0` | 邻近 NAIZ 对非 NAIZ 城市产生正向 TFP 溢出 |
| `θ = 0` | 没有明显空间溢出 |
| `θ < 0` | 可能存在虹吸效应或资源挤出 |

### 7.4 距离衰减检验

把 `W_NAIZ_it` 拆成不同距离带：

```text
W_NAIZ_0_100_it
W_NAIZ_100_200_it
W_NAIZ_200_300_it
W_NAIZ_300_500_it
```

回归：

```text
NonAI_TFP_it = α_i + λ_t
             + θ1 W_NAIZ_0_100_it
             + θ2 W_NAIZ_100_200_it
             + θ3 W_NAIZ_200_300_it
             + θ4 W_NAIZ_300_500_it
             + γ X_it
             + ε_it
```

理论预期：

```text
θ1 > θ2 > θ3 > θ4
```

或者至少：

```text
θ1, θ2 显著为正；
θ3 变弱；
θ4 不显著。
```

这对应知识溢出的地理衰减逻辑。

---

## 8. SDM 什么时候用？

### 8.1 SDM 模型

```text
Y_it = ρ W Y_it
     + β NAIZ_it
     + θ W_NAIZ_it
     + γ X_it
     + δ W_X_it
     + α_i + λ_t + ε_it
```

其中：

| 符号 | 含义 |
|---|---|
| `W Y_it` | 邻近城市结果变量的空间加权平均 |
| `ρ` | 结果变量的空间依赖程度 |
| `W_NAIZ_it` | 邻近 NAIZ 暴露 |
| `W_X_it` | 邻近控制变量 |

### 8.2 SDM 的解释要求

如果使用 SDM，不能只解释 `β`、`θ` 和 `ρ`。必须报告：

1. 直接效应；
2. 间接效应；
3. 总效应。

因为在有 `W Y_it` 的模型中，一个城市的政策冲击可能通过空间反馈影响其他城市，再反过来影响自身。系数本身不等于简单边际效应。

### 8.3 SDM 的定位

SDM 应用于：

| 用途 | 是否适合 |
|---|---|
| 空间相关诊断 | 适合 |
| 直接效应、间接效应、总效应分解 | 适合 |
| 主因果识别 | 不建议 |
| 稳健性检验 | 适合 |

---

## 9. 最小可执行版本

建议把空间部分做成四层，不要一开始堆模型。

### 第一层：基准 DID

```text
Y_it = α_i + λ_t + β NAIZ_it + γ X_it + ε_it
```

回答：

> NAIZ 是否提高本地 AI 专利质量？

对应 H1。

### 第二层：空间暴露 DID / SLX

```text
Y_it = α_i + λ_t + β NAIZ_it + θ W_NAIZ_it + γ X_it + δ W_X_it + ε_it
```

回答：

> 邻近 NAIZ 是否影响本城市结果？普通 DID 的 no-spillover 假设是否站得住？

对应 H3 和空间溢出检验。

### 第三层：竞争调节模型

```text
Y_it = α_i + λ_t
     + β NAIZ_it
     + μ NAIZ_it × Comp_it
     + γ X_it
     + ε_it
```

回答：

> 周边同质化竞争是否削弱 NAIZ 的创新质量效应？

对应 H2。

### 第四层：SDM 稳健性

```text
Y_it = ρ W Y_it
     + β NAIZ_it
     + θ W_NAIZ_it
     + γ X_it
     + δ W_X_it
     + α_i + λ_t + ε_it
```

回答：

> 在更一般的空间依赖结构下，直接效应、间接效应和总效应是否仍然成立？

对应稳健性分析。

---

## 10. 必须做哪些检验？

### 10.1 平行趋势检验

不仅要检验 `NAIZ_it` 的平行趋势，也要检验 `W_NAIZ_it` 的空间暴露趋势。

也就是说，不只是画：

```text
treated city vs control city
```

还要画：

```text
high exposure city vs low exposure city
```

否则 H3 的空间溢出可能只是高暴露城市原本趋势更好。

### 10.2 空间自相关检验

可以报告：

```text
Moran's I for Y_it
Moran's I for baseline residuals
```

如果因变量或残差存在明显空间相关，说明空间模型有必要。

但注意：即使 Moran’s I 不显著，H2 和 H3 仍然可以做。因为本项目的空间变量不是单纯为了纠正残差相关，而是直接对应理论机制。

### 10.3 权重矩阵稳健性

至少做：

| 稳健性 | 目的 |
|---|---|
| 100 km / 200 km / 300 km / 500 km | 检验空间衰减 |
| 反距离矩阵 | 基准 |
| k 近邻矩阵 | 避免东西部城市密度差异 |
| 同省矩阵 | 检验省内竞争 |
| 产业相似矩阵 | 检验 H2 机制 |
| 政策文本相似矩阵 | 检验同质化补贴竞争 |

### 10.4 Donut 检验

可以剔除最近邻城市，例如剔除 0—100 km 内城市，只保留 100—300 km：

```text
W_NAIZ_100_300_it
```

目的：

> 排除极近距离城市之间的行政边界、通勤圈、同城化因素。

### 10.5 安慰剂检验

可以做三类 placebo：

| Placebo | 做法 |
|---|---|
| 时间安慰剂 | 把 NAIZ 批复时间提前 2—3 年 |
| 空间安慰剂 | 随机打乱 NAIZ 城市位置 |
| 非相关结果变量 | 用与 AI 无关的低技术专利或非技术指标 |

---

## 11. 参考文献建议

### 11.1 理论基础文献

| 文献 | 用途 |
|---|---|
| Duranton and Puga (2004), *Micro-foundations of urban agglomeration economies* | sharing、matching、learning，解释 AI 算力和人才集聚 |
| Jaffe, Trajtenberg and Henderson (1993), *Geographic localization of knowledge spillovers as evidenced by patent citations* | 专利引用和知识溢出的地理本地化 |
| Audretsch and Feldman (1996), *R&D spillovers and the geography of innovation and production* | R&D 溢出与创新地理集中 |
| Kline and Moretti (2014), *People, Places, and Public Policy: Some Simple Welfare Economics of Local Economic Development Programs* | 地点导向政策的本地效应与全国福利 |
| Fajgelbaum and Gaubert (2020), *Optimal Spatial Policies, Geography, and Sorting* | 最优空间政策、溢出、空间分选 |

### 11.2 计量方法文献

| 文献 | 用途 |
|---|---|
| Delgado and Florax (2015), spatial DID related work | 空间 DID：自身处理和邻近处理同时影响结果 |
| Butts (2021/2024), difference-in-differences with spatial spillovers | DID 中空间溢出导致传统估计偏误 |
| LeSage and Pace (2009), *Introduction to Spatial Econometrics* | 空间计量中的直接、间接、总效应 |
| Elhorst (2014), *Spatial Econometrics: From Cross-Sectional Data to Spatial Panels* | 空间面板模型、SAR/SEM/SDM/SLX 的系统框架 |
| Chagas, Azzoni and Almeida (2016), space-time DID related approach | 空间 DID 和溢出处理的应用参照 |

---

## 12. 建议写进项目 plan 的表述

可以将空间计量部分写成：

> 本文首先使用多期 DID 估计 NAIZ 对本地 AI 创新质量的直接影响；随后构造基于地理距离的空间暴露变量，检验邻近 NAIZ 对本地创新质量和非 AI 部门 TFP 的间接影响；进一步结合产业结构相似度、同省 NAIZ 密度和算力券政策文本相似度，构造城市间同质化竞争强度，检验地方算力补贴竞争是否削弱 NAIZ 的创新促进效应。方法上，主空间模型采用 SLX / 空间暴露 DID，因为该设定能够直接对应“邻近政策暴露”和“邻近竞争压力”两个理论机制；SDM 作为稳健性检验，用于报告直接效应、间接效应和总效应分解。

---

## 13. 对 Claude Code / Codex 的明确更新指令

### 13.1 更新 `06_空间计量方案.md`

把原来“基准空间模型使用 SDM”的表述改为：

> 主空间模型采用 SLX / 空间暴露 DID；SDM 作为稳健性或补充模型。

新增结构：

1. 为什么普通 DID 存在 no-spillover 问题；
2. 主空间模型：SLX / 空间暴露 DID；
3. H2 竞争模型：`NAIZ_it × Comp_it`；
4. H3 溢出模型：`W_NAIZ_it`；
5. SDM 只作为稳健性；
6. 权重矩阵优先级：地理距离为基准，政策相似度为机制检验。

### 13.2 更新 `03_理论框架.md`

增加核心判断：

> 空间计量不是为了处理一般空间相关，而是为了识别 NAIZ 的邻近溢出与同质化竞争两种相反空间外部性。

在“地理集中 vs. 地理扩散”中补充：

| 空间外部性 | 理论含义 |
|---|---|
| 正向溢出 | AI 知识、人才流动、企业协作、非 AI 部门 TFP 提升 |
| 负向竞争 | 算力券趋同、智算中心重复建设、AI 企业和人才争夺、利用率下降 |

### 13.3 更新 `04_实证假设.md`

H2 改为：

```text
Y_it = α_i + λ_t
     + β NAIZ_it
     + μ NAIZ_it × Comp_it
     + γ X_it
     + ε_it
```

H3 改为：

```text
NonAI_TFP_it = α_i + λ_t
             + θ W_NAIZ_it
             + γ X_it
             + ε_it
```

并加入距离衰减版本：

```text
NonAI_TFP_it = α_i + λ_t
             + θ1 W_NAIZ_0_100_it
             + θ2 W_NAIZ_100_200_it
             + θ3 W_NAIZ_200_300_it
             + θ4 W_NAIZ_300_500_it
             + γ X_it
             + ε_it
```

### 13.4 更新 `05_变量与数据.md`

新增变量：

```text
W_NAIZ_it
Comp_geo_it
Comp_industry_it
Comp_policy_it
W_ComputeSubsidy_it
W_X_it
W_NonAI_TFP_it
W_NAIZ_0_100_it
W_NAIZ_100_200_it
W_NAIZ_200_300_it
W_NAIZ_300_500_it
```

每个变量需要写明：

1. 数据来源；
2. 空间权重矩阵；
3. 是否使用政策前数据；
4. 是否作为基准或机制变量；
5. 内生性风险。

### 13.5 更新 `02_文献综述.md`

新增空间计量和空间政策文献：

```text
Duranton and Puga (2004)
Jaffe, Trajtenberg and Henderson (1993)
Audretsch and Feldman (1996)
Kline and Moretti (2014)
Fajgelbaum and Gaubert (2020)
Delgado and Florax (2015)
Butts (2021/2024)
LeSage and Pace (2009)
Elhorst (2014)
Chagas, Azzoni and Almeida (2016)
```

在文献综述中新增一条主线：

> 空间政策评估与空间溢出文献：用于说明为什么普通 DID 不足以评估 NAIZ 这种地点导向型 AI 产业政策。

---

## 14. 最关键的判断

空间计量在这个项目中不是为了让模型更复杂，而是为了避免普通 DID 错误地把以下三类效应混在一起：

1. 本地 NAIZ 政策效应；
2. 邻近知识溢出；
3. 邻近资源竞争。

最终空间设定应简化为：

```text
Direct NAIZ effect:       NAIZ_it
Spillover effect:         W_NAIZ_it
Competition effect:       NAIZ_it × Comp_it
Distance decay:           W_NAIZ_0_100, W_NAIZ_100_200, W_NAIZ_200_300
Robustness:               SDM direct / indirect / total effects
```

这样做以后，论文的空间部分才能真正服务于核心问题：

> **AI 算力补贴到底是在创造区域创新外部性，还是在诱发地方同质化竞争和空间资源错配？**

---

## 15. 建议 Claude Code 后续执行 plan

### Step 1: 只更新 notes，不运行实证

先更新以下文件：

```text
02_文献综述.md
03_理论框架.md
04_实证假设.md
05_变量与数据.md
06_空间计量方案.md
07_待办与未确认事项.md
```

### Step 2: 生成空间变量构造 plan

新增一个脚本计划文件，例如：

```text
plans/spatial_variable_construction_plan.md
```

内容包括：

1. 城市经纬度来源；
2. 城市距离矩阵构造；
3. 反距离矩阵；
4. 距离带矩阵；
5. k 近邻矩阵；
6. 同省矩阵；
7. 产业相似矩阵；
8. 政策文本相似矩阵；
9. `W_NAIZ_it` 和 `Comp_it` 的生成逻辑。

### Step 3: 生成实证模型 plan

新增：

```text
plans/spatial_empirical_strategy_plan.md
```

包括：

1. 基准 DID；
2. 事件研究；
3. SLX / 空间暴露 DID；
4. H2 竞争调节模型；
5. H3 非 AI 部门 TFP 溢出模型；
6. SDM 稳健性；
7. Moran’s I；
8. 权重矩阵稳健性；
9. placebo；
10. donut 检验。

### Step 4: 明确不要做的事

Claude Code 不应直接做以下修改：

1. 不要把 SDM 设为主模型；
2. 不要把政策文本相似度矩阵设为基准矩阵；
3. 不要把所有空间交互项堆进一个主回归；
4. 不要在没有数据前确定最终样本期；
5. 不要把空间计量写成纯技术章节，而要和 H2/H3 理论机制对应。

