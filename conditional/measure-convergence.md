# 主定理 W1：固定高斯窗零点对关联的条件性测度极限

- **对应仓库路径**：`conditional/measure-convergence.md`
- **状态**：在修正闭合版 Lemma 1、Lemma 2、Lemma 3 下严格成立（条件于 $\mathrm{GRH}(2p)$ 及 $\|T_{2p}\| = o(\log p)$）

---

## 1. 定理陈述

**定理 W1.** 设沿全部充分大的奇素数 $p$ 成立 $\mathrm{GRH}(2p)$ 及 $\|T_{2p}\| = o(\log p)$。记 $L = \log(2p)$，并在 $[0, \infty)$ 上定义一对有限非负 Borel 测度：
$$\mathrm{d}\mu_p(y) := e^{-3y}\widetilde{F}_{2p}(y)\,\mathbf{1}_{y > 2\pi/\sqrt{L}}\,\mathrm{d}y, \qquad \mathrm{d}\nu_p(y) := e^{-3y}\widetilde{F}_{2p}(y)\,\mathbf{1}_{y \ge 0}\,\mathrm{d}y.$$
则当 $p \to \infty$ 时：

1. **有限测度弱收敛**：
   $$\mu_p \;\Longrightarrow\; e^{-3y}\min(y, 1)\,\mathrm{d}y, \qquad \nu_p \;\Longrightarrow\; \frac{1}{2}\delta_0 + e^{-3y}\min(y, 1)\,\mathrm{d}y.$$
2. **去掉指数倾斜后的局部弱收敛**：对任意紧支连续函数 $f \in C_c([0, \infty))$，有
   $$\lim_{p \to \infty} \int_{2\pi/\sqrt{L}}^\infty f(y)\widetilde{F}_{2p}(y)\,\mathrm{d}y = \int_0^\infty f(y)\min(y, 1)\,\mathrm{d}y,$$
   $$\lim_{p \to \infty} \int_0^\infty f(y)\widetilde{F}_{2p}(y)\,\mathrm{d}y = \frac{1}{2}f(0) + \int_0^\infty f(y)\min(y, 1)\,\mathrm{d}y.$$

---

## 2. 完整证明

1. **有限非负性**：对每个固定 $p$，因 $N(T, \chi) \ll T\log(p(2+T))$ 而 $\psi(\gamma) = \pi^{-1/4}e^{-\gamma^2/2}$ 超指数衰减，故 $\sum_{\gamma_\chi}\psi(\gamma_\chi) < \infty$，从而 $\widetilde{F}_{2p}(y)$ 在 $\mathbb{R}$ 上非负、连续且一致有界。由于 $e^{-3y} \in L^1([0, \infty))$，$\mu_p$ 与 $\nu_p$ 均为 $[0, \infty)$ 上的有限非负 Borel 测度。

2. **Laplace 变换在 $\lambda > -1$ 上的逐点收敛**：对任意固定 $\lambda > -1$，令 $c := \frac{\lambda + 3}{2} > 1$（满足 $2c = \lambda + 3$）。在 $\mathrm{GRH}(2p)$ 与 $\|T_{2p}\| = o(L)$ 下：
   - 由 **Lemma 1** 得 $\frac{M_{2p}(c)}{L^2} = \frac{1 - e^{-2c}}{4c^2} + o_c(1)$；
   - 由 **Lemma 2** 得 $\left|\frac{\sqrt{M_{2p}(c)}}{L} - \left(\int_{2\pi/\sqrt{L}}^\infty e^{-2cy}\widetilde{F}_{2p}(y)\,\mathrm{d}y\right)^{1/2}\right| \ll_c \frac{1}{\log L}$。

   合并两者并直接计算 $\int_0^\infty e^{-2cy}\min(y, 1)\,\mathrm{d}y = \int_0^1 ye^{-2cy}\,\mathrm{d}y + \int_1^\infty e^{-2cy}\,\mathrm{d}y = \frac{1 - e^{-2c}}{4c^2}$，即得对一切 $\lambda > -1$：
   $$\mathcal{L}\mu_p(\lambda) := \int_0^\infty e^{-\lambda y}\,\mathrm{d}\mu_p(y) = \int_{2\pi/\sqrt{L}}^\infty e^{-2cy}\widetilde{F}_{2p}(y)\,\mathrm{d}y \longrightarrow \frac{1 - e^{-2c}}{4c^2} = \int_0^\infty e^{-\lambda y}\,e^{-3y}\min(y, 1)\,\mathrm{d}y =: \mathcal{L}\mu(\lambda).$$

3. **紧性与有限测度弱收敛（$\mu_p \Rightarrow \mu$）**：
   - **总质量一致有界**：取 $\lambda = 0$（$c = 3/2 > 1$），$\mu_p([0, \infty)) = \mathcal{L}\mu_p(0) \to \mathcal{L}\mu(0) < \infty$。
   - **一致紧性**：取 $\lambda = -1/2$（$c = 5/4 > 1$），对任意 $R > 0$，
     $$\mu_p([R, \infty)) = \int_R^\infty e^{-3y}\widetilde{F}_{2p}(y)\mathbf{1}_{y > 2\pi/\sqrt{L}}\,\mathrm{d}y \le e^{-R/2}\mathcal{L}\mu_p(-1/2) \ll e^{-R/2} \xrightarrow{R \to \infty} 0 \quad (\text{对 } p \text{ 一致}).$$
   - 由 Prokhorov 定理，$\{\mu_p\}$ 相对紧。若 $\mu_{p_k} \Rightarrow \widetilde{\mu}$ 为任意弱收敛子列，则对所有 $\lambda \ge 0$ 有 $\mathcal{L}\widetilde{\mu}(\lambda) = \lim_{k\to\infty}\mathcal{L}\mu_{p_k}(\lambda) = \mathcal{L}\mu(\lambda)$。由 $[0, \infty)$ 上有限 Borel 测度 Laplace 变换的唯一性（Stone–Weierstrass 定理），必有 $\widetilde{\mu} = \mu$，故整列弱收敛 $\mu_p \Rightarrow \mu$。

4. **局部弱收敛与未截断测度（$\nu_p \Rightarrow \frac{1}{2}\delta_0 + \mu$）**：
   - 对任意 $f \in C_c([0, \infty))$，令 $g(y) := e^{3y}f(y) \in C_c([0, \infty)) \subset C_b([0, \infty))$，由 $\mu_p \Rightarrow \mu$ 立即得 $\int_{2\pi/\sqrt{L}}^\infty f(y)\widetilde{F}_{2p}(y)\,\mathrm{d}y = \int_0^\infty g\,\mathrm{d}\mu_p \to \int_0^\infty g\,\mathrm{d}\mu = \int_0^\infty f(y)\min(y, 1)\,\mathrm{d}y$。
   - 对任意 $h \in C_b([0, \infty))$，令 $\omega_h(\delta) := \sup_{0 \le y \le \delta}|h(y)e^{-3y} - h(0)| \to 0$（$\delta \to 0^+$）。由 **Lemma 3** 得
     $$\left|\int_0^{2\pi/\sqrt{L}} h(y)e^{-3y}\widetilde{F}_{2p}(y)\,\mathrm{d}y - h(0)\int_0^{2\pi/\sqrt{L}}\widetilde{F}_{2p}(y)\,\mathrm{d}y\right| \le \omega_h\!\left(\frac{2\pi}{\sqrt{L}}\right)\left(\frac{1}{2} + O(L^{-1/2})\right) \longrightarrow 0,$$
     故 $\int_0^{2\pi/\sqrt{L}} h(y)\,\mathrm{d}(\nu_p - \mu_p)(y) \to \frac{1}{2}h(0)$。与 $\mu_p \Rightarrow \mu$ 相加即得 $\nu_p \Rightarrow \frac{1}{2}\delta_0 + \mu$，对 $f \in C_c([0, \infty))$ 同样立即推出未截断的局部弱收敛。 $\square$

---

## 3. 四个层级的严格区分及文献定位

### 四层级区分（不可混淆）
1. **有限测度弱收敛**：$\mu_p \Rightarrow e^{-3y}\min(y, 1)\,\mathrm{d}y$ 与 $\nu_p \Rightarrow \frac{1}{2}\delta_0 + e^{-3y}\min(y, 1)\,\mathrm{d}y$（已证）。
2. **去掉指数倾斜后的局部弱收敛**：对 $f \in C_c([0, \infty))$ 的积分收敛（已证）。
3. **固定高斯窗 + 模 $p$ 奇特征族形式因子**：本定理仅针对 $\psi(t) = \pi^{-1/4}e^{-t^2/2}$ 与 $X_p^-$，且为测度意义下的弱收敛，**不直接蕴含** $\widetilde{F}_{2p}(y) \to \min(y, 1)$ 的逐点或紧集一致收敛。
4. **一般 Dirichlet $L$-函数 GUE 对关联猜想**：涉及全部本原特征、任意测试窗函数及紧集一致/逐点形式因子渐近，严格强于本定理。

### 与 Travor Zihao Liu (2026) 的精确关系
在 *Pair correlation of $L$-zeros and Hooley's conjecture* (`hexagon:2611.00509v1`, 2026-11) 中，Travor Zihao Liu 固定奇素数模 $q$，对**全部** $q - 2$ 个本原特征平均，采用带限 Schwartz 窗函数 $f$（与 $W \in C_c^\infty(0, \infty)$ 成 Mellin 对偶）：
- 无条件证明了 $|\alpha| < 1$ 的斜坡（Theorem 2）；
- 证明了 $1 \le |\alpha| \le B$ 上形式因子的**一致**平台收敛等价于素数模平滑 Hooley 方差猜想（Theorem 3）。

因此，定理 W1 属于 Li–Liu 最弱谱假设 S（沿 $N = 2p$）的**独立必要条件**：它在奇特征族 + 固定高斯窗 + 弱测度意义下，跨过了无条件可达的 $y < 1$ 区域并在全体 $y > 0$ 上恢复了 $\min(y, 1)\,\mathrm{d}y$ 测度；但因缺乏偶特征族、一般带限窗函数与 $y \ge 1$ 上的一致逐点收敛，尚不能直接与 Liu (2026) Theorem 3 拼接推出 Hooley 猜想。
