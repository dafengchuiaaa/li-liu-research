# Lemma 3：零频质量集中（修正闭合版）

- **对应仓库路径**：`needs-review/lemma3-low-frequency.md`（修正后可升格至 `conditional/`）
- **状态**：已独立核验全部常数、偶性折半、变量替换与误差项；直接复用 Lemma 2 中已证的低频显式公式均方界 (2.6)，仅假设 $\mathrm{GRH}(2p)$（**无需** $\|T_{2p}\| = o(L)$）。

---

## 1. 命题陈述

沿用 Lemma 2 中的记号：$N = 2p$，$L = \log(2p)$，$\psi(t) = \pi^{-1/4}e^{-t^2/2}$，
$$\widetilde{F}_{2p}(y) = \frac{2\pi}{L}\,\mathbb{E}_{\chi \in X_p^-}\left|\sum_{\gamma_\chi} \psi(\gamma_\chi)e^{-iyL\gamma_\chi}\right|^2.$$

**Lemma 3.** 在 $\mathrm{GRH}(2p)$ 下，当 $p \to \infty$ 时有
$$\int_0^{2\pi/\sqrt{L}} \widetilde{F}_{2p}(y)\,\mathrm{d}y = \frac{1}{2} + O\!\left(L^{-1/2}\right).$$

---

## 2. 完整证明

由 $\widetilde{F}_{2p}(-y) = \widetilde{F}_{2p}(y)$ 为偶函数，先折半展开至对称区间 $[-2\pi/\sqrt{L}, 2\pi/\sqrt{L}]$，再作变量替换 $y = \frac{2\pi}{L}\xi$（$\mathrm{d}y = \frac{2\pi}{L}\,\mathrm{d}\xi$，$|y| \le \frac{2\pi}{\sqrt{L}} \iff |\xi| \le \sqrt{L}$）：
$$\begin{aligned}
\int_0^{2\pi/\sqrt{L}} \widetilde{F}_{2p}(y)\,\mathrm{d}y
&= \frac{1}{2}\int_{-2\pi/\sqrt{L}}^{2\pi/\sqrt{L}} \widetilde{F}_{2p}(y)\,\mathrm{d}y \\
&= \frac{1}{2} \cdot \frac{2\pi}{L} \cdot \frac{2\pi}{L}\,\mathbb{E}_{\chi \in X_p^-}\int_{|\xi| \le \sqrt{L}} |S_\chi(\xi)|^2\,\mathrm{d}\xi \\
&= \frac{2\pi^2}{L^2}\,\mathbb{E}_{\chi \in X_p^-}\int_{|\xi| \le \sqrt{L}} \left|\frac{\log(p/\pi)}{2\pi}\widehat{\psi}(\xi) + R_\chi(\xi)\right|^2\mathrm{d}\xi,
\end{aligned}$$
其中 $S_\chi(\xi) = \frac{\log(p/\pi)}{2\pi}\widehat{\psi}(\xi) + R_\chi(\xi)$ 为 Lemma 2 式 (2.5) 的 Weil–Guinand 显式公式。

逐项核查展开后的三部分：

1. **主项**：
   $$\frac{2\pi^2}{L^2} \cdot \frac{(\log(p/\pi))^2}{4\pi^2}\int_{|\xi| \le \sqrt{L}} |\widehat{\psi}(\xi)|^2\,\mathrm{d}\xi = \frac{1}{2}\left(\frac{\log(p/\pi)}{\log(2p)}\right)^2\left(1 - \int_{|\xi| > \sqrt{L}} |\widehat{\psi}(\xi)|^2\,\mathrm{d}\xi\right).$$
   因 $\frac{\log(p/\pi)}{\log(2p)} = 1 - \frac{\log(2\pi)}{L} = 1 + O(L^{-1})$，且 $\int_{|\xi| > \sqrt{L}} |\widehat{\psi}(\xi)|^2\,\mathrm{d}\xi = 2\sqrt{\pi}\int_{|\xi| > \sqrt{L}} e^{-4\pi^2\xi^2}\,\mathrm{d}\xi = O(e^{-4\pi^2 L})$，故主项等于
   $$\frac{1}{2} + O\!\left(\frac{1}{L}\right).$$

2. **余项平方**：由 Lemma 2 式 (2.6) 已证的 $\mathbb{E}_{\chi \in X_p^-}\int_{|\xi| \le \sqrt{L}} |R_\chi(\xi)|^2\,\mathrm{d}\xi = O(L)$，得
   $$\frac{2\pi^2}{L^2}\,\mathbb{E}_{\chi \in X_p^-}\int_{|\xi| \le \sqrt{L}} |R_\chi(\xi)|^2\,\mathrm{d}\xi = O\!\left(\frac{1}{L}\right).$$

3. **交叉项**：对主项与余项应用 Cauchy–Schwarz 不等式，绝对值不超过
   $$2\left(\frac{1}{2} + O(L^{-1})\right)^{1/2} \cdot O(L^{-1/2}) = O\!\left(L^{-1/2}\right).$$

合并三项即得
$$\int_0^{2\pi/\sqrt{L}} \widetilde{F}_{2p}(y)\,\mathrm{d}y = \frac{1}{2} + O\!\left(L^{-1/2}\right). \qquad \square$$

---

## 3. 在主定理中的精确角色

- 截断测度 $\mathrm{d}\mu_p(y) = e^{-3y}\widetilde{F}_{2p}(y)\mathbf{1}_{y > 2\pi/\sqrt{L}}\,\mathrm{d}y$ 的弱收敛**不依赖** Lemma 3（仅需 Lemma 1 + Lemma 2）。
- Lemma 3 的作用是将低频区间 $[0, 2\pi/\sqrt{L}]$ 补回：对任意 $h \in C_b([0, \infty))$，它在 $y=0$ 处连续，故 $e^{-3y}\widetilde{F}_{2p}(y)\mathbf{1}_{0 \le y \le 2\pi/\sqrt{L}}\,\mathrm{d}y \Rightarrow \frac{1}{2}\delta_0$，从而使**未截断**测度 $\mathrm{d}\nu_p(y) = e^{-3y}\widetilde{F}_{2p}(y)\mathbf{1}_{y \ge 0}\,\mathrm{d}y$ 收敛至完整的（折叠到半轴上的）斜坡–平台加原点质量测度 $\frac{1}{2}\delta_0 + e^{-3y}\min(y, 1)\,\mathrm{d}y$。
