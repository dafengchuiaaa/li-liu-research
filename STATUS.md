# 命题状态表（2026-11-23）

`VERIFIED` = 对特定明确陈述有独立可重检的证明；`CONDITIONAL` = 依赖论文定理/额外假设；`PENDING` = 关键解析估计尚未彻底核实；`INVALIDATED` = 旧推导中已定位致命错误。

| ID | 命题或构造 | 状态 | 依据/限制 |
|---|---|---|---|
| A1 | 预先固定 `h→∞` 的最弱 S 与 `||T_N||/𝔖(N)→0` 等价 | CONDITIONAL | 假设 GRH + Li–Liu Theorem 6.1 双向对应；纯量词部分已有明确构造 |
| E1 | `P_N(w)` 是 `ℓ∤N` 的无限 Euler 乘积 | SOURCE CHECK | 与原论文 (2.11) 对照；严禁使用有限乘积 |
| E2 | `H_{2p}(0)=1` 且 `𝔖(2p)P_{2p}(2c/L)~L/(2c)` | VERIFIED (代数/局部解析) | [`verified/euler-product.md`](verified/euler-product.md) |
| K1 | 连续核对角高斯均值的 `-e^{-2c}L²/(4c²)+O_c(L)` | CONDITIONAL / REVIEW | 主项由 E2 导出；必须独立核对 Gamma 加权余项与原核的精确系数 |
| L1 | `||T_{2p}||=o(L)` 蕴含 `M_{2p}(c)/L²→(1-e^{-2c})/(4c²)` | CONDITIONAL / REVIEW | 可望用 Li–Liu Proposition 5.4 点值估计；需核对原文常数及 K1 |
| L2 | `M_N(c)/L²` 与高频零点形式因子 Laplace 积分相差 `o(1)` | PENDING | Hadamard、Selberg 短区间计数、奇特征正交、交换子估计、傅里叶常数 |
| L3 | 低频质量 `∫₀^{2π/√L} F̃_N = 1/2+O(L^{-1/2})` | PENDING | 依赖显式公式低频均方，需独立复查 |
| F1 | Fejér–Lorentz 非负核不等式 | VERIFIED（在规定正权零点和定义下） | [`verified/fejer-lorentz.md`](verified/fejer-lorentz.md) |
| W1 | 倾斜有限测度 Laplace 极限推出弱收敛 | CONDITIONAL | 一旦 L1–L3 及变换归一化成立，可用有限正测度连续性定理 |
| X1 | 纯 Dirichlet GRH 推出 `liminf ||T_{2p}||/log p>0` | INVALIDATED | 错用有限乘积导致 K 核主项错误；[`invalidated/grh-disproof.md`](invalidated/grh-disproof.md) |
| R-LEAN | 原仓库 7 个离散 Lean 定理 | EXTERNAL VERIFIED CLAIM | GitHub README 报告 Lean 4.12.0 编译通过；此次只读源码，未重新运行编译器 |

## 下一步待办

1. 确认 Li–Liu Proposition 5.4 精确再生核不等式及 Hardy 内积的系数。
2. 对连续核在 `s=c/L+it` 的加权余项给出真正的 `O_c(L)` 控制。
3. 审计 Lemma 2/3：显式公式符号、`2π` 因子、高斯尾项、`m≡-n` 与 `mn≡±1 mod p`。
4. 若成立，才陈述 **针对固定高斯权重与奇特征平均** 的有限测度弱收敛，且不得误称完整 GUE。

## 状态维护规则

任何命题提升至 VERIFIED，必须存储：逐字定义与假设、可定位的论文来源/独立证明、依赖引理、审查者、版本日期。发现新错误要保留原错误版本在 `invalidated/`，不要静默覆盖。
