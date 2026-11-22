# F1：Fejér–Lorentz 点态和零点和不等式

**状态：** 代数/Fourier 步骤可直接核查；需要 `F̃_N` 由非负实权重的绝对可和指数和平方定义。

对任意 `Y≥1`, `u∈ℝ`, 有

\[
\left(\frac{\sin(Yu/2)}{Yu/2}\right)^2\le \frac{20}{16+u^2}.
\]

当 `|u|≤2`，左边至多 1，右边至少 1；当 `|u|>2`，左边至多 `4/(Y²u²)≤4/u²≤20/(16+u²)`。

使用频率为 `y` 的 Fourier 变换：

\[
\int_{-Y}^Y(1-|y|/Y)e^{-iyu}\,dy
=Y\operatorname{sinc}^2(Yu/2),
\]
\[
\int_\mathbb R e^{-4|y|}e^{-iyu}\,dy=\frac{8}{16+u^2}.
\]

因此第一积分不超过 `(5/2)Y` 倍第二积分（两式因核为偶而均是实数）。

若 `F̃_N(y)=C_N\sum_χ|\sum_γ a_{χ,γ}e^{-iyLγ}|²` 且 `C_N≥0, a_{χ,γ}≥0`, `Σ_γ a_{χ,γ}<∞`，把上述不等式取 `u=L(γ−γ')`，乘 `C_N a_{χ,γ}a_{χ,γ'}` 后求和，得

\[
\boxed{\int_0^Y(1-y/Y)\widetilde F_N(y)\,dy
\le \tfrac52Y\int_0^\infty e^{-4y}\widetilde F_N(y)\,dy.}
\]

**历史说明：** 旧否证企图用候选密度 `y` 导出矛盾；修正为 `min(y,1)` 后不再矛盾。因此本不等式保留，但不证明最弱 S 失败。
