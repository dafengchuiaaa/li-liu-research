# L1：修正后的 Lemma 1（建议简证）

**状态：CONDITIONAL / 待核对原文。** Gemini 曾提供多次复杂的双边界围道证明；GPT 后建议直接用 Li–Liu 原论文 **Proposition 5.4** 的再生核点值估计。此处归档的是待正式核对出处与精确常数的**简证路线**，并非已完成的独立形式化证明。

记 `N=2p`、`L=log(2p)`、`α_N=1/L`、`β=1/8`、`c>1` 固定，`s=c/L+it`。令

\[
M_N(c)=\int_\mathbb R w(t)\mathscr P_N(c/L+it,c/L-it)\,dt,
\quad w(t)=e^{-t^2}/\sqrt\pi.
\]

如原文 Proposition 5.4 的精确版本为

\[
|\mathscr E_N(s,\bar z)|\le
\frac{\|T_N\|\,|1+s|\,|1+z|}{8\sqrt{d_N(s)d_N(z)}},
\quad d_N(s)=\min(\Re s-\alpha_N,\beta-\Re s),
\]

则当 `L` 充分大，`d_N(s)=(c−1)/L`，得

\[
\left|\int w(t)\mathscr E_N(s,\bar s)\,dt\right|
\le \frac{L\|T_N\|}{8(c-1)}\big((1+c/L)^2+\tfrac12\big).
\]

配合算术核分解 `𝔈=𝔓−𝔇−𝔎`、`𝔇_N(2c/L)=L²/(4c²)+O(1)` 和高斯加权连续核的待审计估计

\[
\int w(t)\mathscr K_{2p}(s,\bar s)\,dt
=-\frac{e^{-2c}L^2}{4c^2}+O_c(L),
\]

即可推出

\[
\left|M_{2p}(c)-\frac{1-e^{-2c}}{4c^2}L^2\right|
\ll_c L\|T_{2p}\|+L.
\]

特别 `||T_{2p}||=o(L)` 蕴含 `M_{2p}(c)/L²→(1−e^{-2c})/(4c²)`。无需任何先验均方上界。

**下一轮审查项：** (1) Prop 5.4 精确系数和定义；(2) `H_{2p}(u)` 的局部一致控制；(3) `𝒳₁` 的带权 `O_c(L)` 误差；(4) 导子 p 与模 2p 的影响。
