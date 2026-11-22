# W1：固定高斯窗零点对关联的条件性测度极限

**状态：CONDITIONAL，依赖 L1、L2、L3。** 不是已证单模 p 全范围 GUE 对关联。

假设 GRH 与对所有固定 `c>1` 成立的两项极限：

\[
M_{2p}(c)/L^2\longrightarrow(1-e^{-2c})/(4c^2),
\]
\[
M_{2p}(c)/L^2-\int_{2\pi/\sqrt L}^\infty e^{-2cy}\widetilde F_{2p}(y)\,dy\longrightarrow0.
\]

则因

\[
\int_0^\infty e^{-2cy}\min(y,1)\,dy=(1-e^{-2c})/(4c^2),
\]

定义有限非负测度

\[
d\mu_p(y)=e^{-3y}\widetilde F_{2p}(y)\mathbf 1_{y>2\pi/\sqrt L}\,dy.
\]

对任意 `t≥0` 取 `c=(t+3)/2>1`，Laplace 变换收敛到 `∫e^{-ty} e^{-3y}min(y,1)dy`。特别在 `t=0` 质量收敛，适用有限正测度 Laplace 连续性定理，可得

\[
\mu_p\Rightarrow e^{-3y}\min(y,1)\,dy.
\]

进而对紧支连续 `f` 可将指数倾斜移除，得到截断形式因子测度的局部弱收敛。不能据此断言形式因子的逐点收敛，也不能直接等同于其他窗口函数或全体特征的完整 GUE。

**前提审计：** `μ_p` 为有限测度须核实 `F̃_p(y)` 以 `p` 固定时的有界性；当零点 Gaussian 权重绝对可和时可以直接证明。
