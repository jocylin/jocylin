# 以太坊的商业模式：完整现金流、收入与 ETH 价值捕获

> **研究日期：2026-08-21（HKT）**  
> **数据快照：约 11:52 HKT；金额默认 USD**  
> **研究目的：** 回答三个问题——Ethereum 到底卖什么、钱最终去了哪里、生态成功如何（或为何不能）转化成 ETH 价值。  
> **重要口径：** Ethereum 不是公司，ETH 不是股票。本报告分别核算协议、验证者、L2、应用与 ETH 持有者，避免把同一笔钱重复记为“收入”。

---

## 一、结论先行

### 1. Ethereum 的商业本质

Ethereum 是一个开放的数字结算经济体，出售四种相互绑定的服务：

1. **Execution / blockspace**：执行交易与智能合约；
2. **Ordering**：交易排序和确定性 inclusion；
3. **Data availability**：向 rollup 出售 blobspace；
4. **Settlement + finality**：以 PoS 抵押资本为状态和资产提供最终结算。

它更像一个**不留公司利润、把一部分收费直接销毁、再用新发行购买安全的数字经济体**，而不是传统收费公路公司。

### 2. “Ethereum 收入”至少有四种不同口径

| 口径 | 2026-08-21 应如何定义 | 谁真正受益 |
|---|---|---|
| **用户总网络费** | execution base fee + priority fee + blob fee | burn + 验证者/区块生产链 |
| **严格协议现金收入** | 协议 treasury 实际收到并可支配的现金 | **约等于 0**；base/blob fee 没有进入公司账户 |
| **Supply-reduction proxy** | 被销毁的 execution base fee + blob base fee；数据商常称 holder revenue | 所有 ETH 持有人，表现为供给减少，而非现金分红 |
| **Validator revenue** | 共识层 rewards + self-build tips/direct MEV **或** external builder payment | 承担质押、运维、流动性及 slashing 风险的验证者 |

**因此，“Ethereum 年收入多少”没有先定义口径，就不是一个完整问题。**

### 3. 当前最重要的事实：生态价值很大，但 ETH 的 fee capture 很薄

[事实] 过去 30 个完整 UTC 日，Ethereum L1 用户支付约 **$8.167M** 网络费；DeFiLlama 估算其中约 **$1.974M** 被销毁，差额 **$6.193M** 是 priority-fee residual，而非审计级 validator revenue；链下 MEV 另计。过去 365 日，网络费约 **$230.1M**、burn estimate 约 **$78.0M**。[DeFiLlama fees](https://api.llama.fi/summary/fees/ethereum?dataType=dailyFees) / [revenue](https://api.llama.fi/summary/fees/ethereum?dataType=dailyRevenue)

[事实] Ultrasound.money 的 rolling 30 日年化口径为：扣除 penalties 后的共识层净发行（net CL issuance）约 **1.060M ETH/年**、fee burn **13.12K ETH/年**、净供给增加约 **1.047M ETH/年**，供应增速 **+0.8586%/年**。当前 net CL issuance 约为 burn 的 **80.85 倍**。[Gauge rates](https://ultrasound.money/api/v2/fees/gauge-rates)

[判断] 这意味着当前 ETH 价格无法靠 fee burn 的“类股票现金流”解释。ETH 约 **$284B** 的市值主要依赖：

- 货币与储备溢价；
- 结算、抵押与安全资本需求；
- 流动性、标准与 credible neutrality 的网络效应；
- 未来区块空间重新稀缺的期权价值。

### 4. L2 成功不自动等于 ETH 成功

[事实] Growthepie 的 2026-07-21 至 08-19 可复现窗口中，严格选取 fees、rent、txcount 三条序列均完整的 23 条 Ethereum L2 后，用户付费约 **$6.129M**，向 L1 支付的 gross rent 约 **$50.75K**，即 **observed gross L1 rent ratio 约 0.828%**。余下约 99.17% 不是净利润，而是 L2 在支付 prover、sequencer、节点、alt-DA、激励、返利等成本前未支付给 L1 的 gross spread。[Fees](https://api.growthepie.com/v1/export/fees.json) / [rent](https://api.growthepie.com/v1/export/rent_paid.json)

[判断] 当前商业模式对用户、L2 sequencer、应用和验证者更友好，对被动 ETH 持有人的直接 fee capture 较弱。**多头必须证明的是“生态使用量增长 → ETH 需求或 burn 增长”的桥，而不是只展示 TPS、TVL 或稳定币规模。**

---

## 二、Ethereum 的商业模式画布

| 维度 | 内容 |
|---|---|
| **产品** | L1 execution、交易排序、blob DA、状态结算、finality、抗审查与可退出性 |
| **客户** | L1 用户与应用；L2/rollup operator 是最重要的批发客户；机构、稳定币与 RWA 发行方是间接客户 |
| **计价/支付资产** | ETH。账户抽象或 paymaster 可以遮蔽用户感知，但最终协议 payer 仍需支付 ETH |
| **定价方式** | execution gas 与 blob gas 两个动态市场；base fee 随拥堵调整，priority fee 争取排序 |
| **供应商** | validators、full nodes、builders、searchers、relays、客户端与核心开发者 |
| **资本** | 质押 ETH 是可罚没的安全抵押；硬件、带宽、运维是实际资源成本 |
| **收入分配** | execution/blob base fee 销毁；priority fee 与 proposer MEV 给区块生产链；发行给验证者 |
| **治理目标** | 链下多方协调，不以股东利润最大化为唯一目标；ETH 数量不是公司式投票权，[官方治理说明](https://ethereum.org/governance/) |
| **护城河** | 安全、流动性、EVM 标准、应用/资产网络、credible neutrality、长期可验证与退出 |

核心矛盾是：

> **Ethereum 需要把区块空间做得足够便宜以扩大采用，但 ETH 持有人又需要付费需求最终超过容量扩张，才能形成持续 burn。**

收入恒等式仍然是：

**协议收费 = 单位价格 × 付费使用量。**

TPS 增长只代表数量；如果扩容令单位价格下降更快，总收费仍会下跌。

---

## 三、一张完整现金流地图

### 1. 总览

    L1 用户
      ├─ 转账/交易本金 ─────────────→ 交易对手、合约或桥（不是收入）
      ├─ 应用费 ───────────────────→ LP、lender、应用 treasury、issuer（不是 L1 收入）
      ├─ execution base fee ───────→ 销毁（全体 ETH 的供给价值捕获）
      ├─ priority fee ─────────────→ proposer / pool / builder 经济链
      └─ MEV 损失或 side payment ─→ searcher → builder → proposer，分配取决于订单流结构

    L2 用户
      ├─ L2 execution / operator fee → sequencer / L2 fee vault
      ├─ L2 MEV ───────────────────→ sequencer、searcher、builder 或用户返利
      └─ 分摊的 L1 DA/settlement ──→ L1 execution/blob fee
                                         ├─ base/blob fee → 销毁
                                         └─ priority fee → L1 proposer

    Ethereum 协议
      └─ 共识层新发行 ETH ─────────→ validators（安全预算；对全体持有人是稀释性分配）

    Validators
      ├─ 运维/硬件/带宽/托管/池费 ─→ 服务商
      └─ penalty/slashing ─────────→ 部分无对手方扣减，部分奖励举报者/提议者

### 2. L1 用户的一笔交易

用户总经济支出：

**User outflow = principal + app fee + execution fee + explicit side payment / MEV loss**

其中：

- **Principal**：转账本金、swap input、bridge deposit、抵押物，只是资产转移；
- **App fee**：DEX fee、借贷 spread、NFT royalty、bridge fee，属于应用、LP、lender 或发行人；
- **Execution fee**：base fee + priority fee；
- **MEV loss**：例如 sandwich、抢跑或清算相关价值转移，不一定体现在标准 gas fee。

EIP-1559 下：

**Execution fee = gas used × base fee + gas used × effective priority price**

- execution base fee 被销毁；
- priority fee 给 execution payload 的 fee recipient；
- max fee 只是上限，不是实际收费；
- reverted transaction 的状态会回滚，但已消耗 gas 仍需支付。

协议依据：[EIP-1559](https://eips.ethereum.org/EIPS/eip-1559) / [Ethereum gas 文档](https://ethereum.org/developers/docs/gas/)

### 3. L2 用户的一笔交易

典型账单必须把网络费与应用费分开：

**L2 network fee = L2 execution/sequencing + allocated L1 DA/settlement + proof cost allocation + operator markup/risk buffer**

**Total L2 user outflow = principal + L2 network fee + app fee + MEV loss**

L2 operator 的经济贡献：

**L2 contribution = observable L2 network fees + separately observed non-overlapping MEV − L1 posting cost − proof cost − sequencer/prover/node OPEX − incentives/rebates**

Ethereum L1 只能捕获其中实际支付给 L1 的部分：

1. batch/proof/state update 交易的 execution base fee；
2. execution priority fee；
3. blob base fee；
4. 其他明确支付给 L1 proposer 的排序价值。

Growthepie 的 `fees_paid` 是用户支付的 **network fee**，不含 app fee；部分链的 network fee 可能已包含 Timeboost 等 inclusion-prioritization revenue，因此不能再机械叠加 sequencer MEV。**L2 用户总收费、L2 sequencer MEV 和 L2 operator fee 不能全部记成 Ethereum 收入。**

### 4. Blob / DA 现金流

Blob 交易同时面对两个独立市场：

**Blob fee = blob gas × blob base fee**

**Type-3 transaction total L1 fee = blob fee + ordinary execution base fee + ordinary execution priority fee**

- blob base fee 全部销毁；
- blob 没有独立 priority fee；
- inclusion 激励来自普通 execution tip 或 builder/MEV 支付；
- blob fee 与 execution fee 都是 L2 posting cost 的组成，不应再和 L1 总费重复相加。

协议依据：[EIP-4844](https://eips.ethereum.org/EIPS/eip-4844)。Fusaka 的 PeerDAS/BPO 扩大了 blob 供给，[EIP-7918](https://eips.ethereum.org/EIPS/eip-7918) 则给 blob 价格增加与 execution cost 相关的 reserve mechanism；它防止价格信号完全塌缩，但不保证高额垄断租金。

### 5. MEV / builder 现金流

MEV 是排序权产生的经济租，不是协议正式开出的统一账单：

**Searcher profit = gross opportunity − gas − builder payment − failed transaction cost − infrastructure**

**Builder profit = 去重后的 execution-payload value − proposer bid − infrastructure**

其中 execution-payload value 可能来自 tips、searcher order flow 与 builder 自有 MEV；这些来源会互相重叠，不能机械相加。

对 proposer：

- 本地建块时，收入可表现为 tips + 直接 MEV；
- 使用外部 builder 时，winning builder bid 往往已包含 tips、searcher bids 与 builder 自有 MEV。

**不能再把 payload tips 与 builder bid 机械相加，否则会 double count。**  
MEV 的真实分配还受到 private order flow、返利和链下支付影响，公开链上数据无法完整还原。[Ethereum MEV 说明](https://ethereum.org/developers/docs/mev)

---

## 四、所有重要现金流的会计归属

| 事件 | 付款方 | 收款方/去向 | 应记在哪本账 | 对 ETH 的意义 |
|---|---|---|---|---|
| L1 转账、swap、bridge 本金 | 用户 | 对手方/合约/桥 | 资产流量，不是收入 | 无直接供给影响 |
| DEX、借贷、NFT、RWA 应用费 | 用户 | LP、lender、应用、issuer、custodian | 应用收入 | 只通过其产生的 gas 间接影响 ETH |
| Execution base fee | L1 用户/L2 poster | 销毁 | supply-reduction proxy | 直接减少 ETH 供给 |
| Priority fee | L1 用户/L2 poster | proposer / pool / builder 链 | validator/区块生产收入 | 不减少供给，是现有 ETH 转移 |
| Blob base fee | L2 poster | 销毁 | supply-reduction proxy | 直接减少 ETH 供给 |
| L2 execution/operator fee | L2 用户 | sequencer / L2 vault | L2 收入 | 不自动进入 L1 |
| L2 sequencer MEV | 用户/套利机会 | sequencer/searcher/builder | L2 排序经济 | 只有明确回流 L1 的部分与 ETH staker 有关 |
| 共识层发行 | 协议 | validators | 安全预算/validator 收入 | 增加供给，对未质押者构成稀释 |
| Staking deposit | staker | staking system | 资产锁定 | 不是收入，不减少总供给 |
| Withdrawal | staking system | staker 地址 | 本金解锁/既有奖励兑现 | 不应在提现时再次计算发行 |
| Penalty/slashing | validator | 无对手方扣减及部分 reporter/proposer credit | 安全惩罚 | 只有净无对手方扣减才减少供给 |
| LST/pool commission | staker | staking provider | 服务商收入 | 不是 Ethereum 协议收入 |
| Restaking/AVS reward | AVS/外部协议 | restaker/operator | 外部服务收入 | 不是 Ethereum 收入，并引入额外风险 |
| Stablecoin 储备利息 | 国债/银行资产 | stablecoin issuer | 发行人收入 | Ethereum 只捕获相关链上 gas |
| RPC、wallet、custody、paymaster 费 | 用户/应用 | 服务商 | 生态服务收入 | 不是 L1 收入 |
| Ethereum Foundation 捐赠/资产收益 | 捐赠者/资产 | Foundation | 独立组织资金 | 与协议 fee revenue 分开 |

---

## 五、四本账：谁真正赚钱？

### A. Protocol ledger

严格企业会计口径：

- retained fee revenue：**约 0**
- base/blob fees：直接销毁
- 没有向 ETH holder 承诺股息、清算权或 residual claim

Token economics 口径：

- gross network fees = base burn + blob burn + priority fees
- supply-reduction proxy（数据商常称 holder revenue）= base burn + blob burn
- holder monetary accrual proxy = burn − net CL issuance = − net supply change

最后一项是供给变化代理，不是 GAAP profit、现金分红或公司回购；没有 treasury asset、residual claim 或现金账户可领取。

### B. Validator P&L

**Validator operating income before OPEX = consensus balance rewards − penalties + execution-payload proceeds + service income**

其中 execution-payload proceeds 必须按区块二选一：

- **self-build**：priority fees + 直接捕获且已去重的 MEV；
- **external builder**：builder payment；该 payment 通常已包含 payload tips 与 MEV，不能再加 priority fees。

减去：

- 服务器、硬件折旧、电力、带宽、云、监控；
- client / relay /地域冗余；
- staking pool、custody、insurance、tax；
- financing 与 32–2,048 ETH 工作资本的机会成本；
- downtime、missed rewards、penalty 与 slashing 尾部损失。

共识层 rewards 是验证者的名义收入，但对全体 ETH 持有人合并来看主要是内部稀释性转移。staking provider commission 通常只是从客户奖励中抽取的服务费，在 validator + staker 合并账中也要抵销。[PoS rewards and penalties](https://ethereum.org/developers/docs/consensus-mechanisms/pos/rewards-and-penalties/)

### C. L2 P&L

**L2 gross economics = observable network fees + separately observed non-overlapping MEV − L1 rent − prover/sequencer/node cost − incentives/rebates**

L1 rent 是 Ethereum 收入桥，但只是一项 COGS。L2 还能保留：

- L2 base fee；
- priority fee；
- operator fee；
- sequencer spread；
- 在多数 centralized-sequencer 架构下主要停留于 L2、但份额无法可靠量化的排序经济；
- wallet、bridge 与应用入口关系。

所以 L2 既是 Ethereum 的客户，也是渠道商，更可能成为经济层面的竞争者。

### D. Application / issuer P&L

稳定币、DEX、借贷、RWA、NFT 与钱包可以建立很好的商业模式，但这些利润不属于 Ethereum：

- 稳定币 issuer 赚 reserve yield；
- DEX 的 fee 给 LP、协议或 front-end；
- 借贷利息给 lender、reserve 或协议；
- RWA 管理、发行、托管费给对应机构；
- Ethereum 只捕获它们为使用 L1/L2 settlement 实际支付的费用，以及由此形成的 ETH 货币/抵押需求。

### E. 可观察、不可观察与外部补贴

“协议 treasury 收入约 0”不等于网络运行成本约 0。Ethereum 的完整经济账还必须承认三层观测边界：

| 层级 | 当前能看到什么 | 不能据此推出什么 |
|---|---|---|
| **直接可观察** | L1 gross fees、burn estimate、CL balance delta、L2 network fees、gross L1 rent | 不能直接推出 validator、L2 或 ETH holder 净利润 |
| **部分可观察** | priority fees、部分 builder payments、staking commission、公开 sequencer fee vault | private order flow、链下 builder payment、rebate、全量 MEV、validator/L2 OPEX 仍不完整 |
| **协议外部资助** | EF/生态 grants、客户端团队、研究、公共 RPC/relay、无协议补偿的 full nodes | 这些成本不是 protocol P&L 的 0，却也不能凭公开 dashboard 汇总为一张审计级损益表 |

因此，本报告所称“完整现金流”是**归属框架完整**，不是声称每条链下现金流都已被精确量化。无法观察的部分明确留空，不用残差伪装成利润。

---

## 六、截至 2026-08-21 的经营仪表盘

### 1. 资产与安全资本

| 指标 | 当前值 | 说明/来源 |
|---|---:|---|
| ETH 价格 | **$2,346.20** | 2026-08-21 11:58 HKT，[CoinGecko](https://api.coingecko.com/api/v3/coins/ethereum?localization=false&tickers=false&market_data=true&community_data=false&developer_data=false&sparkline=false) |
| 数据商市值 | **$283.17B** | CoinGecko；按其 120.682M circulating supply 计算 |
| 协议状态供应量 | **121.971M ETH** | [Ultrasound.money supply series](https://ultrasound.money/api/v2/fees/supply-over-time)；同价隐含 network value 约 $286.17B，不与数据商口径静默混用 |
| 有效质押余额 | **42.324M ETH** | [Beaconcha.in proxy](https://launchpad.ethereum.org/.netlify/functions/beaconchain-api?path=epoch%2Flatest&url=https%3A%2F%2Fmainnet.beaconcha.in) 与 [Ultrasound.money](https://ultrasound.money/api/v2/fees/effective-balance-sum) 基本一致 |
| 有效质押占比 | **34.700%** | 以 121.971M 协议状态供应量为分母 |
| Validator indices | **901,918** | 近实时 epoch 快照；Pectra 后 validator index 不再等于固定 32 ETH |
| 31 日平均 staking APR | **2.6348%** | CL 2.5377% + EL 0.0972%；最近完整 Beacon 日为 2.8343%，不等于无风险收益，[Launchpad ethstore](https://launchpad.ethereum.org/.netlify/functions/beaconchain-api?path=ethstore%2Flatest&url=https%3A%2F%2Fmainnet.beaconcha.in) |

### 2. L1 网络费与价值分配

以下均为截至 2026-08-20 UTC 的完整自然日窗口，而非截至抓取秒的 rolling window：

| 窗口 | 用户总网络费 | Base/blob burn estimate | Priority-fee residual | Burn 占总费 |
|---|---:|---:|---:|---:|
| 30 日 | **$8.167M** | **$1.974M** | **$6.193M** | **24.2%** |
| 90 日 | **$26.747M** | **$6.781M** | **$19.967M** | **25.4%** |
| 365 日 | **$230.050M** | **$77.974M** | **$152.076M** | **33.9%** |

来源：[DeFiLlama Ethereum fee adapter](https://github.com/DefiLlama/dimension-adapters/blob/master/fees/ethereum)。该 adapter 以区块内最低 `effective_gas_price` 近似 execution base fee，而不是逐区块直接读取审计级 base-fee 序列；因此 burn 是估算，`gross fee − burn` 只是 priority-fee residual。若区块没有零 tip 交易，burn 可能被高估、residual 被低估；链下 MEV 也未包含。

同一 2026-07-22 至 08-20 UTC 窗口，Etherscan 记录约 **69.18M** 笔 L1 交易，gross network fee 粗略平均约 **$0.118/tx**。[Etherscan tx CSV](https://etherscan.io/chart/tx?output=csv) 这只是混合交易类型的平均数，不代表复杂合约调用的边际成本。

### 3. 货币政策

| 指标 | 30 日年化 run-rate |
|---|---:|
| Net CL issuance（已扣 penalties） | **1,060,369 ETH/年** |
| Base/blob burn | **13,116 ETH/年** |
| Net supply change | **+1,047,254 ETH/年** |
| Supply growth | **+0.8586%/年** |
| Net CL issuance / burn | **80.85×** |

按当前 $2,346.20 标记：

- 年化 net CL issuance 约 **$2.488B**；
- 年化 burn 约 **$30.77M**；
- 年化 net supply increase 约 **$2.457B**。

Ultrasound 对 rolling 30 日 burn 按每日价格路径计值后年化约 **$25.37M**；DeFiLlama adapter 的 burn estimate 年化约 **$24.02M**；两者又都不同于用当前 spot price 重估 ETH run-rate 得出的 **$30.77M**。差异来自 burn 估算方法与价格路径，三者不可混作同一口径。

**结论：当前不是净通缩状态。** “ETH 永远通缩”并不是协议保证，而是 fee demand 与 issuance 的动态结果。

### 4. L2 单位经济

在截至 2026-08-19 的 30 日完整窗口，严格取三条指标序列均完整的 23 条 L2：

| 指标 | 数值 |
|---|---:|
| 跟踪 L2 交易数 | **772.1M** |
| L2 用户费 | **$6.129M** |
| 支付给 L1 的 rent | **$50.75K** |
| Observed gross L1 rent ratio | **0.828%** |
| 平均 L2 用户费 | **$0.00794/tx** |
| 平均 L1 rent | **$0.000066/tx** |
| 2026-08-19 L2/L1 交易数 | **11.85×** |

来源：[Growthepie tx count](https://api.growthepie.com/v1/export/txcount.json)、[fees](https://api.growthepie.com/v1/export/fees.json)、[rent](https://api.growthepie.com/v1/export/rent_paid.json)。排除 Ethereum mainnet、Polygon PoS、fee 序列缺失的 Fraxtal，以及 rent 序列停在 2026-06-12 的 zkSync Era。Robinhood 与 Base 合计占 matched fees **86.53%**，所以该比率也受链组合影响；11.85× 的当日 L2/L1 交易数只用于 activity 比较，采用 Growthepie 全跟踪集合，不与上述 23 链单位经济分母混用。

这说明 rollup 扩容在用户体验上成功，但当前 **observed gross L1 rent / observed L2 network fee** 很低。它不是协议设定的 revenue share，也不是被动 ETH holder capture：$50.75K 还要拆成 burn 与 proposer proceeds，且 L1 rent 已包含在 L1 总网络费内，不能再与 $8.167M 相加。

### 5. 生态需求指标：规模很大，但不是收入

| 指标 | 当前/最近完整窗口 | ETH 价值含义 |
|---|---:|---|
| Ethereum L1 USD stablecoins | **$146.94B** | 强结算/流动性网络，但 issuer 的国债利息不归 ETH，[DefiLlama](https://stablecoins.llama.fi/stablecoinchains) |
| Ethereum DeFi TVL | **约 $47.35B** | 抵押与流动性需求；TVL 不是协议资产或收入，[DefiLlama chains](https://api.llama.fi/v2/chains) |
| Ethereum DEX volume，30 日 | **$26.23B** | 代表应用活动；不能与 gas fee 相加，[DefiLlama DEX](https://api.llama.fi/overview/dexs/ethereum?excludeTotalDataChart=false&excludeTotalDataChartBreakdown=true&dataType=dailyVolume) |
| L2 value secured | **$29.36B** | 22 个 rollups + 6 个 validiums/optimiums；Ethereum 作为结算/安全锚的需求指标，[L2BEAT](https://l2beat.com/layer2s/tvs?tab=rollups) |
| L2 对 blob 数据占比，rolling 1Y | **97.37%** | Rollup 是 blobspace 核心客户；不代表 blob rent 已经很高，[L2BEAT](https://l2beat.com/data-availability/throughput) |

数据源在 stablecoin、TVL 与 supply 的资产覆盖、桥接及重复计算方法上并不完全一致。本报告只在同一数据源内部做趋势和比例，不把不同 endpoint 伪装成单一会计真值。

---

## 七、从采用到 ETH 价值：哪里能捕获，哪里会漏掉？

| 活动 | 创造的价值 | 主要经济捕获者 | ETH 能捕获什么 |
|---|---|---|---|
| L1 transfer/contract call | 即时执行、结算、可组合性 | validators/builders + 全体 holders | base burn、tips、MEV |
| Stablecoin | 美元结算与全球流动性 | issuer、银行/国债资产、支付渠道 | gas、抵押/流动性需求、网络溢价 |
| DEX/DeFi | 交易、杠杆、借贷、清算 | LP、lender、protocol、front-end、MEV 链 | 相关 gas burn/tips；ETH collateral demand |
| L2 | 低成本执行与规模化 | sequencer、prover、L2 operator、apps | blob/execution rent、L1 finality、潜在 ETH 储备需求 |
| RWA/tokenization | 资产发行、登记、转让 | issuer、manager、custodian、broker | gas、settlement 与可信中立溢价 |
| Staking | 网络安全与 finality | validators、pools、LST providers | ETH 作为可罚没资本；tips/builder payments 是 non-issuance proposer proceeds |
| MEV | 套利、清算、排序；也可能损害用户 | searcher、builder、proposer、order-flow owner | proposer 收入；被动 holder 不直接获得 MEV |

### Ethereum/ETH 的六条价值通道

#### 1. Fee burn：最机械、最可验证

L1 execution 与 blob 的 base fee 被销毁，直接减少 supply。它是最机械的 **supply sink**，但不是公司 buyback：

- 不是现金 dividend；
- 没有公司利润账户；
- 若 issuance 更高，净货币收益仍为负；
- 扩容会压低单位价格，必须由更多付费需求补偿。

#### 2. Gas 与 working capital

所有 L1 协议级费用最终以 ETH 支付。Paymaster 可以让用户只看到 USDC，但幕后 payer 仍要持有/购买 ETH。

不过 gas 的货币需求取决于周转率：如果钱包、sequencer 与做市商高效管理库存，同样交易量只需很少 working balance。

#### 3. PoS collateral

ETH 是网络安全资本。质押需求锁定大量 ETH 并创造对 ETH 的结构性用途。

但锁定不等于销毁；LST 又会恢复流动性。因此估值不能把全部质押量直接当作永久供给减少。

#### 4. DeFi/L2 collateral 与 reserve asset

如果 ETH 是 DeFi、L2 treasury、bridge、stablecoin 与机构链上资产的默认 collateral/reserve，它可能获得货币溢价；这个通道可能主导价格，却最难量化，不能作为填补 fee 缺口的 residual plug。

#### 5. Network and standards premium

安全、流动性、EVM tooling、资产与应用密度、长期中立性降低了迁移与协调成本。Ethereum 提供 canonical commitment、近期 DA 与 L1 finality；但长期状态恢复和退出保证仍取决于每个 L2 的数据保留、proof、bridge、upgrade keys 与 sequencer trust model，不能一概而论。

#### 6. Future congestion option

当付费需求持续超过 execution/blob target，EIP-1559 会提高价格并增强 burn。持有 ETH 相当于持有对未来网络稀缺性的期权。

风险是 Ethereum 路线图持续扩容。若 capacity growth 长期快于 paid demand，这个期权不会兑现。

---

## 八、价值框架与反向门槛：这不是目标价

当前 burn 以 ETH 计量；若先用当前 ETH 价格把它换成美元、再乘一个倍数反推 ETH 价值，会把待求价格重新当作输入，形成循环论证。因此本报告不把 burn 做成伪 DCF，也不输出 fair value 或 price target。

### 1. Supply yield：最硬的无价格口径

以 121.971M ETH 协议状态供应量为分母：

- gross burn yield = 13,116 / 121.971M = **0.01075%/年**；
- net CL issuance yield 约 **0.8694%/年**；
- holder monetary accrual yield = burn − net CL issuance = **−0.8586%/年**。

要让供给仅仅达到净零，年化 burn 就须从约 13.1K ETH 升至 **1.060M ETH**，即当前的 **80.85×**。这是比“美元 burn × 任意倍数”更有意义的第一道反向门槛。

仅作敏感性诊断：若有人坚持用 30× gross burn shortcut 去解释 CoinGecko 的 $283.17B 市值，隐含年 burn 约 **$9.44B / 4.02M ETH / 协议供应量的 3.30%**，约为当前 burn 的 **307×**。这不是 fair value——它没有增长率、折现率或 terminal assumption，只说明当前 fee regime 无法独立解释市场价格。

### 2. Staking carry：拆掉“名义 APR 幻觉”

ETH.STORE 的 31 日平均 realized staking APR 约 **2.635%**，其中 CL 2.538%、可观察 EL priority-fee component 0.097%。该口径不含完整 builder bids、direct MEV 或链下支付，因此不是 validator all-in return。扣除当前 **0.8586%** 的全网供应增长，质押者相对总供应的份额增速约：

**2.635% − 0.8586% = 1.78%**

这还没有扣：

- validator/pool OPEX；
- slashing 与 smart-contract 风险；
- 流动性和退出风险；
- ETH 本金波动；
- 税务与托管成本。

质押者最直接的基准是**持有未质押 ETH**，因为 2.635% 是 ETH-denominated return。同期美国 3 个月国债收益率约 **3.86%**（2026-08-18），[FRED DGS3MO](https://fred.stlouisfed.org/graph/fredgraph.csv?id=DGS3MO)，只能作为 USD 机会成本背景，不能与 staking APR 直接横比；若要比较 USD-hedged return，还必须扣掉 hedge/basis、融资、托管和税务成本。

更重要的是，staking 收益中：

- issuance 是持有人之间的再分配；
- priority fee、builder payment 与 direct MEV 是 non-issuance proposer proceeds，但在合并 ETH 经济体内仍可能只是 transactor/searcher 向 proposer 的价值转移，不自动等于外部现金流。

### 3. Monetary premium：不是答案，而是待证明的 residual

ETH 的价值通道可以画成一张 map，但不能机械相加成 SOTP：

- **fee supply sink**：execution/blob burn；
- **validator economics**：CL rewards、non-issuance proposer proceeds 减真实成本；
- **monetary/collateral demand**：gas、储备、抵押、质押安全资本；
- **platform option**：未来 L1/L2 互操作、排序回流与更多付费需求。

同一枚 ETH 可能同时出现在 TVL、LST、restaking、bridge 与 treasury 中；burn、staking 与 monetary premium 又相互作用，因此不能重复资本化。当前 fee supply yield 很低，市场价格显然主要在交易货币性、安全性、网络效应与未来稀缺性的预期；**这个 residual 不是估值证据，恰恰是多头必须用未来数据证明的部分。**

所以 reverse diagnostic 应回答：未来 burn 何时追上 net CL issuance？observed gross L1 rent ratio 能否改善？ETH 在抵押/储备中的去重份额能否维持？在这些变量没有可验证预测前，本报告只给价值捕获框架，不伪造单点估值。

### 4. ETH 最合适的资产分类

ETH 同时具有：

- 商品：是购买 execution/DA/security 的生产投入；
- 货币：是原生 gas、结算与抵押资产；
- 资本资产：质押后参与生产并获得 fee/MEV；
- 供应机制：付费使用会消耗 ETH，但这只是 supply sink，不是公司回购。

但它没有：

- 法定 residual claim；
- 董事会、清算权或股息承诺；
- 按持币比例进行协议治理的股东投票；
- 固定票息、到期日和面值赎回。

因此最准确的简称是：

> **ETH 是具有 fee burn 与 productive staking 的货币商品，而不是 Ethereum 的股票。**

---

## 九、Bull / Base / Bear：真正需要押注什么

以下只是经营状态机，不是 price target、概率加权估值或交易建议。数据不足以诚实地给出后者。

| 情景 | 经营路径 | 需要看到的指标 | ETH 价值来源 |
|---|---|---|---|
| **Bear** | L2/应用增长，但单位 DA 与 execution 价格贴近 floor；sequencer、issuer、apps 保留经济价值 | burn / net CL issuance 长期低于 10%；observed gross L1 rent ratio 低于 1%；ETH collateral 份额下降 | 只剩有限安全/结算溢价，fee thesis 失效 |
| **Base** | 容量扩张继续压价，生态规模增长；ETH 保持主要安全与抵押资产 | burn / net CL issuance 回升至 20–50%；stablecoin/RWA/L2 使用增长；ETH reserve share 稳定 | 主要靠 monetary premium，fee burn 是辅助 |
| **Bull** | 原生 blob 与 L1 blockspace 持续接近 target；Ethereum 成为全球中立结算与默认 collateral | burn ≥ net CL issuance；排序经济出现可验证回流；ETH collateral 与 treasury adoption 上升 | supply contraction + non-issuance proposer proceeds + 强货币溢价共同驱动 |

### 最强反方，不是“Ethereum 会消失”

最值得认真对待的空头论证是：

> **Ethereum 可以在技术上非常成功、承载大量 stablecoin/RWA/L2，却把经济利润留给 L2 sequencer、应用、发行人和 MEV 中间商；L1 只成为低价 DA/settlement 公共设施，ETH 则成为高周转率 gas token。**

这正是为什么“生态繁荣”与“token value capture”必须分两张表。

---

## 十、主要风险与可证伪条件

### 1. Scaling paradox

PeerDAS、BPO 和更高 gas limit 增加供给、改善 UX，却可能使单位 fee 与 burn 下降。规模战略只有在 paid demand 增长快于 capacity 时才兑现。

### 2. L2 value leakage

L2 保留 execution fee、operator fee 与 customer relationship；在多数 centralized-sequencer 架构下，排序经济主要停留于 L2，但公开数据无法可靠量化具体份额。当前 observed gross L1 rent ratio 不到 1%；based/shared sequencing 能否形成可验证回流仍未证明。

### 3. DA competition

Rollup 可以选择 Celestia、EigenDA、Avail 或 validium 模式，但切换会改变 DA 安全假设，项目也可能从 rollup 被重新归类为 validium/optimium/other，并非无成本替代。Ethereum 原生 DA 的安全溢价若不被市场付费，blobspace 会接近商品化。

### 4. Stablecoin replaces ETH as money

稳定币更适合计价和支付；gas abstraction 又降低终端用户持有 ETH 的需要。ETH 必须守住 collateral、reserve 与 security capital，而不只是后台 gas。

### 5. MEV / staking centralization

LST、staking pool、builder、private order flow 和云基础设施可能跨层集中，导致审查、单点故障与经济租外流。

### 6. Governance–holder objective mismatch

Ethereum 治理优先可信中立、低费与公共基础设施并不错误，但这些目标不等于最大化 ETH holder cash flow。持有人也没有公司式权利阻止 fee routing 或 issuance 政策改变。

### 7. Security、regulatory 与 discount-rate risk

客户端 bug、finality 事故、争议性 social rollback、slashing、staking/稳定币监管与更高无风险利率，都会压缩货币和风险溢价。

### 建议采用的 Kill Conditions

以下是研究者设定的 operational thresholds，并非协议事实；每项都写明当前 baseline 与 breach rule：

1. **Burn coverage**：当前 burn / net CL issuance = **1.237%**；若同口径 trailing-12M 连续 12 个月低于 10%，同时 L2 tx 或 Ethereum stablecoin supply 同比增长超过 25%，判为采用未转化成供给捕获；
2. **Observed gross L1 rent**：当前 23-chain matched ratio = **0.828%**；若固定 cohort/字段后连续 8 个季度低于 1%，且无可验证 sequencing/MEV 回流，判为 L2 rent bridge 失效；
3. **原生 DA moat**：当前 L2 blob bytes rolling-1Y share = **97.37%**；若同一 L2 universe 连续 12 个月低于 50%，判为原生 DA 主导地位失效；
4. **货币性**：目前没有可信、去重后的生态 collateral/reserve share baseline，故暂不启用“跌破 25%”这类伪精确 kill condition；先建立资产集合、分母与去重规则；
5. **生产性收益**：当前质押者供应份额增速约 1.78%、尚未扣成本；若扣 OPEX、流动性与 slashing 风险后相对未质押 ETH 的增量收益连续 12 个月为负，判为 staking economics 失效；
6. **稀缺性政策**：当前 supply growth = **+0.8586%**；若 rolling-24M 连续高于 1%，又没有可验证的 cost-of-corruption / value-at-risk 改善，判为安全预算未产生相称价值；
7. **可信中立**：出现 finalized invalid state、持续系统性审查，或必须依赖高度争议的 social rollback 才能恢复；
8. **先扩容后变现**：以当前 BPO2 14/21 blob 参数为 baseline，未来 8 个季度 paid demand、burn coverage 与已定义的 ETH collateral share 均无改善。

---

## 十一、每月应追踪的 10 个指标

1. Execution base burn、blob burn 与 priority fees；
2. Burn / net CL issuance、net supply growth；
3. L1 gross fee / market cap 与 burn / market cap；
4. Blob target utilization、每 blob 平均价格、L2 rent；
5. Observed gross L1 rent ratio，并拆出 passive-holder burn、validator proceeds 与可测 sequencing/MEV；
6. L1 与 L2 交易数、但同时看单位 fee，避免只看 TPS；
7. ETH 在 DeFi、L2 treasury、RWA/stablecoin collateral 中的去重份额；
8. Native Ethereum DA 与外部 DA 的数据字节份额；
9. Staking APR 的 issuance、tips、MEV、cost 拆分及验证者集中度；
10. Stablecoin、DEX、RWA、开发者和应用活动相对 Solana/其他结算层的份额。

其中最关键的三个：

> **Observed gross L1 rent ratio、burn / net CL issuance、ETH 的 collateral/reserve share。**

---

## 十二、最终研究判断

1. **Ethereum 的“商业模式”成立。** 它有真实客户、真实产品、真实收费、真实供应商和安全资本。
2. **但这不是公司商业模式。** 协议不保留利润，收费在 burn、validators、builders 与 sequencers 之间分配。
3. **当前 fee capture 很弱。** 30 日 run-rate 下，按 spot 标记的年化 burn 约 $30.77M，而数据商市值约 $283.17B；net CL issuance 约为 burn 的 80.85 倍。
4. **L2 是增长引擎，也是价值泄漏风险点。** 当前 23-chain observed gross L1 rent ratio 约 0.828%，且其中还要拆 burn 与 proposer proceeds；L2 TPS 增长本身不构成 ETH 多头证据。
5. **ETH 的主要价值不是当前现金流，而是货币商品属性。** 它必须继续成为 gas、staking collateral、DeFi/L2 reserve 和全球中立结算资产。
6. **真正的多头条件：** 付费需求增长快于 execution/blob 容量，burn 最终追上 issuance，同时 ETH 的抵押与储备份额不被 stablecoin、BTC 或其他链取代。

一句话收束：

> **Ethereum 已经证明自己能创造生态价值；尚未完全证明的是，它能把足够多的生态价值稳定地捕获回 ETH。**

---

## 附录 A：核心公式与防重复规则

### 供应变化

**ΔSupply = consensus-layer balance delta（rewards − penalty debits）− execution base burn − blob burn**

Deposit、withdrawal、bridge lock、普通 transfer 均不改变合并经济供给。

### ETH 持有人货币收益代理

**Net monetary accrual = execution/base burn + blob burn − net CL issuance**

正数代表收缩，负数代表稀释；它不是现金 dividend。

### 质押者供应份额调整收益

**Relative staking yield ≈ nominal staking APR − net supply growth − OPEX/risk costs**

### L1 capture ratio

**L1 capture ratio = L2 支付的 L1 fee + 明确返还 L1 的 sequencing/MEV ÷ L2 用户费及 sequencer MEV**

### 十条防重复规则

1. gas fee 已包含 burn，不能二次相加；
2. issuance 是 validator 收入，但不是全体 ETH 持有者的外部收入；
3. L2 rent 已包含在 L1 gross fees 中；
4. L1 DA cost 通常已包含在 L2 user fee 中；
5. TVL、stablecoin supply、DEX volume、交易额不是收入；
6. builder bid 经常已包含 tips/MEV，不能再次加 tips；
7. staking lock 不是 burn；
8. withdrawal 不是新发行，奖励在 balance credit 时已发生；
9. restaking/AVS reward 不是 Ethereum 收入；
10. 同一 ETH 在 LST、restaking、bridge、TVL 中必须去重。

---

## 附录 B：数据口径与来源

### 口径说明

- **市场估值口径：** 使用 CoinGecko $2,346.20 价格、120.682M circulating supply 与 $283.168B 市值；
- **货币政策趋势：** 使用 Ultrasound.money 同一序列内部变化。其协议状态序列约 121.971M ETH，比 CoinGecko circulating supply 高约 1.289M ETH（1.07%），同价隐含 network value 约 $286.169B。差异主要来自 consensus issuance accounting，故不静默混用；有效质押占比与所有 supply yield 均以协议状态供应量为分母；
- **美元费用：** DeFiLlama 按每日价格换算；spot-marked burn 使用当前 ETH 价格，二者会因价格路径产生差异；
- **L2：** Growthepie 30 日完整窗口截至 2026-08-19，排除 Ethereum mainnet 和 Polygon PoS；
- **MEV：** 公开链上与 relay 数据无法观察全部 private order flow、返利及链下支付，报告只将其单列，不伪造全量数值；
- **动态数据：** 所有 dashboard 数字均会变化，应以趋势和同口径比例为主。

### 协议与一手资料

- [EIP-1559：execution fee market 与 base fee burn](https://eips.ethereum.org/EIPS/eip-1559)
- [EIP-4844：blob transaction 与 blob fee burn](https://eips.ethereum.org/EIPS/eip-4844)
- [EIP-7918：blob base fee reserve mechanism](https://eips.ethereum.org/EIPS/eip-7918)
- [Ethereum gas 文档](https://ethereum.org/developers/docs/gas/)
- [Ethereum PoS rewards and penalties](https://ethereum.org/developers/docs/consensus-mechanisms/pos/rewards-and-penalties/)
- [Ethereum MEV 文档](https://ethereum.org/developers/docs/mev)
- [Ethereum governance](https://ethereum.org/governance/)
- [Pectra roadmap](https://ethereum.org/roadmap/pectra/)
- [Fusaka roadmap](https://ethereum.org/roadmap/fusaka/)

### 数据源

- [CoinGecko Ethereum API](https://api.coingecko.com/api/v3/coins/ethereum?localization=false&tickers=false&market_data=true&community_data=false&developer_data=false&sparkline=false)
- [Etherscan ETH supply](https://etherscan.io/stat/supply)
- [Ultrasound.money gauge rates](https://ultrasound.money/api/v2/fees/gauge-rates)
- [Ultrasound.money burn sums](https://ultrasound.money/api/v2/fees/burn-sums)
- [Ultrasound.money supply over time](https://ultrasound.money/api/v2/fees/supply-over-time)
- [DeFiLlama Ethereum fees](https://api.llama.fi/summary/fees/ethereum?dataType=dailyFees)
- [DeFiLlama Ethereum burn/revenue](https://api.llama.fi/summary/fees/ethereum?dataType=dailyRevenue)
- [DefiLlama stablecoins by chain](https://stablecoins.llama.fi/stablecoinchains)
- [Growthepie data API docs](https://docs.growthepie.com/)
- [L2BEAT](https://l2beat.com/)
- [FRED 3-month Treasury](https://fred.stlouisfed.org/graph/fredgraph.csv?id=DGS3MO)
