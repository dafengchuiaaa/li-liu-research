# L2：Gemini 的 Lemma 2（待独立复核）

**状态：PENDING。** 本文件按聊天贴出的两轮 Gemini 草稿重构了**论证骨架**，不是逐字论文稿。不得声称已得到严格证明。

## 定义

设 `N=2p`，`L=log(2p)`，`σ=c/L` (`c>1`)，奇本原特征集 `X_p^-` 的元素数为 `(p−1)/2`，令

\[
\psi(t)=\pi^{-1/4}e^{-t^2/2},\quad w(t)=\psi(t)^2,
\]
\[
\widetilde F_N(y)=\frac{2\pi}{L}\frac{2}{p-1}\sum_{\chi\in X_p^-}\left|\sum_{\gamma_\chi}\psi(\gamma_\chi)e^{-iyL\gamma_\chi}\right|^2.
\]

**候选 Lemma 2：**

\[
\frac{M_N(c)}{L^2}
=\int_{2\pi/\sqrt L}^\infty e^{-2cy}\widetilde F_N(y)\,dy+o_c(1).
\]

Gemini 更强版本尝试直接在平方根层面建立 `O(1/log L+c/√L)` 的误差，以避免事先假定 `M_N(c)≪L²`。

## 原草稿步骤（仅重构概要）

1. **剥离 Euler 因子 2**：诱导模 `2p` 的奇特征与本原模 `p` 的对应 `L'/L` 相差绝对值 `O(1)`；在 Hilbert 范数层面用反三角不等式。
2. **虚部消去**：分析 `((L'/L)(1/2+s,χ))² e^{(s-σ)²}/√π`；在 GRH 下把竖直线 `Re s=σ` 移到 2，得 `∫w |L'/L|² = 2∫w (Re L'/L)²+O(1)`。注意移线符号、水平边界及全 `t` 一致性。
3. **Hadamard–Poisson 表示与交换子**：`Re L'/L` 为 Poisson 零点核之和减去 `1/2 log(p/π)` 与 Gamma 项；交换权 `ψ(t)` 与 `ψ(γ)`。声称 `||E_χ||₂ ≪ L/log L + c√L`，需要 Selberg 类型 GRH 短区间计数而不只是经典零点计数的主项。
4. **显式公式低频均方**：`|ξ|≤√L` 使用 Weil–Guinand 显式公式；高斯截断 `x_p=e^{4π√L}` 并要求 `x_p²<p−1`；小素数幂段通过模 p **奇特征**正交控制 `O(L)`。
5. **Plancherel 高频**：`|ξ|>√L`，Poisson 核变换 `πe^{−2πσ|ξ|}`；变量 `ξ=Ly/(2π)` 得形式因子 Laplace 项。

## 必审的精确恒等式

模 p 奇特征平均的两条关系：

\[
\frac2{p-1}\sum_{\chi\in X_p^-}\chi(m)\bar\chi(n)
=\mathbf1_{m\equiv n\ (p)}-\mathbf1_{m\equiv -n\ (p)},
\]
\[
\frac2{p-1}\sum_{\chi\in X_p^-}\chi(m)\chi(n)
=\mathbf1_{mn\equiv1\ (p)}-\mathbf1_{mn\equiv-1\ (p)}.
\]

截断界 `x_p²<p−1` 排除相反同余和乘积同余；不能错误地把奇特征平均简单写成 `δ_{m=n}`。

## 审查重点

- 直接核对 Hadamard 实部式中的 Gamma 项及 `1/2`。
- 校对显式公式 Fourier 约定 `e^{-2π i ξt}`、`2π` 常数及 `χ(n)` / 共轭方向。
- 检查在 `t` 大时交换子尾部的 `L²` 估计、零点个数的 `p,χ,t` 一致性。
- Gamma 和 Euler 项应与主项分离，绝对不能用“标准误差”代替证明。
- 原稿一处高斯指数尾界有过强写法，后续版本修正；审计仍需独立复算。
- **暂不把这份 Lemma 2 提升到 Verified。**
