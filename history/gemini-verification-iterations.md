# Gemini 研究轮次归档（2026-11-23）

> 这是根据聊天中粘贴内容的**重构性审查摘要**，并非完整原始 LaTeX 转录；在原文中存在显示为空的公式，不能虚构补全。

## Round 0：最弱 S 的量词等价

- 证明存在固定的缓慢增长 `h` 与 `||T_N||/𝔖(N)→0` 条件等价。
- 使用尾部上确界 `u_N` 控制 `a_N` 并同时截断 `η≤1/4`。
- 来源：原论文 Theorem 6.1（GRH 条件下），状态：CONDITIONAL。见 `verified/weak-S-quantifiers.md`。

## Round 1：原始反例机制（已推翻）

- 提议 Hardy 空间 Cauchy 边界局部化，试图证明 `||T_{2p}||≫log p`。
- 猜测 `𝒫−𝒟` 的 `log²` 主项不能被连续核 `𝒦` 消去。
- 关键错误：误录无限乘积的 `ℓ∤N` 为 `ℓ|N`，从而误判 `𝒦=O(log N)`。
- 以 GRH 下 Hadamard、Laplace 唯一性和 Fejér 核导出的“纯 GRH 否证”结论失效。

## Round 2：无外部二阶零点聚集界的 Fejér–Lorentz 方案

- 证明了普适点态 `sinc²(Yu/2)≤20/(16+u²)`。
- 由正权零点对求和得到可复用不等式。
- 但输入的 Laplace 密度 `y` 依赖失效的 `𝒦=O(log N)`；修正后失去矛盾。

## Round 3：Gemini 重写 Lemma 1

- 先尝试原始 Hardy 带 `Re s=1/L` 到 `1/8` 的双边界留数平移，分别估算 `𝒫`、`𝒟`、`𝒦`。
- 另曾尝试用 Borel–Carathéodory、Hadamard 三线定理证明右边界 `L'/L` 点态界。
- 修正 Euler 乘积后，又尝试平移到 `Re s=3/4` 以调用绝对收敛域。
- GPT 发现可用原论文 Proposition 5.4 再生核估计替代繁复围道；该替代证明必须仍然审核精确常数和连续核的高斯加权误差。

## Round 4：Gemini 重写 Lemma 2 + Lemma 3

- 使用 Hadamard 实部展开、Selberg 条件下的零点区间计数，构造 Gaussian 加权的 Poisson 零点和。
- 运用 Fourier/Plancherel，把均方转换成零点对关联形式因子的 Laplace 积分。
- 修复旧稿中奇特征正交被误写成 Kronecker δ 的问题，使用 `x_p²<p−1` 排除 `m≡−n` 和 `mn≡±1`。
- 提供误差预算 `||E_χ||₂≪ L/log L+c√L`、零频质量 `1/2`。
- 状态：PENDING，需要独立逐行审计，特别是显式公式、Gamma、Gaussian 尾项与系数。

## Round 5：转向分支 2

- 已不再坚持旧 GRH 否证。
- 新目标：在 GRH + `||T_{2p}||=o(log p)` 条件下建立**固定高斯窗、奇特征平均**的零点对关联测度收敛。
- 新目标不应被误称完整 GUE；应与 2026 年固定模数 Dirichlet 零点对关联文献仔细比较。
