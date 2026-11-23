# Lemma 2：Hadamard–Poisson–Plancherel 等价（修正闭合版）

- **对应仓库路径**：`needs-review/lemma2-plancherel.md`（修正后可升格至 `conditional/`）
- **状态**：已独立审计并修复全部旧草稿缺口（虚部消去一致性、交换子二进环估计、精确奇特征正交、高斯尾界、$2\pi$ 归一化常数）；**不依赖任何先验均方上界**，仅假设 $\mathrm{GRH}(2p)$。

---

## 1. 记号与命题陈述

设 $p \to \infty$ 为奇素数，$N = 2p$，$L = \log(2p)$。固定 $c > 1$，记 $\sigma = c/L$。设 $X_p^-$ 为模 $p$ 的本原奇特征族（$|X_p^-| = \frac{p-1}{2}$），记均值算子 $\mathbb{E}_{\chi \in X_p^-} := \frac{2}{p-1}\sum_{\chi \in X_p^-}$。

定义高斯窗与 Fourier 变换约定：
$$\psi(t) = \pi^{-1/4}e^{-t^2/2}, \qquad w(t) = \psi(t)^2 = \pi^{-1/2}e^{-t^2}, \qquad \widehat{f}(\xi) = \int_{\mathbb{R}} f(t)e^{-2\pi i\xi t}\,\mathrm{d}t.$$
则 $\|\psi\|_2 = \|\widehat{\psi}\|_2 = 1$，且 $\widehat{\psi}(\xi) = \sqrt{2}\pi^{1/4}e^{-2\pi^2\xi^2}$。定义 Hilbert 空间
$$\mathcal{L} := L^2\!\left(X_p^- \times \mathbb{R},\, \frac{2}{p-1}\,\# \otimes \mathrm{d}t\right), \qquad \|F\|_{\mathcal{L}}^2 := \mathbb{E}_{\chi \in X_p^-}\int_{\mathbb{R}} |F(\chi, t)|^2\,\mathrm{d}t.$$

在 $\mathrm{GRH}(2p)$ 下，将 $L(s, \chi)$（$\chi \in X_p^-$）的非平凡零点记为 $\rho_\chi = \frac{1}{2} + i\gamma_\chi$（$\gamma_\chi \in \mathbb{R}$，计重数），并定义形式因子
$$\widetilde{F}_{2p}(y) := \frac{2\pi}{L}\,\mathbb{E}_{\chi \in X_p^-}\left|\sum_{\gamma_\chi} \psi(\gamma_\chi)e^{-iyL\gamma_\chi}\right|^2.$$
因 $\chi \mapsto \bar\chi$ 是 $X_p^-$ 的双射、$\{\gamma_{\bar\chi}\} = \{-\gamma_\chi\}$ 且 $\psi$ 为偶函数，$\widetilde{F}_{2p}(y)$ 为非负、偶、连续且对每个固定 $p$ 有界的函数。

**Lemma 2.** 在 $\mathrm{GRH}(2p)$ 下，对任意固定 $c > 1$，当 $p$ 充分大时有
$$\left|\frac{\sqrt{M_{2p}(c)}}{L} - \left(\int_{2\pi/\sqrt{L}}^\infty e^{-2cy}\widetilde{F}_{2p}(y)\,\mathrm{d}y\right)^{1/2}\right| \ll_c \frac{1}{\log L}.$$
特别地，只要 $M_{2p}(c) \ll_c L^2$（例如由 Lemma 1 在 $\|T_{2p}\| = O(L)$ 下给出），立即有
$$\frac{M_{2p}(c)}{L^2} = \int_{2\pi/\sqrt{L}}^\infty e^{-2cy}\widetilde{F}_{2p}(y)\,\mathrm{d}y + O_c\!\left(\frac{1}{\log L}\right).$$

---

## 2. 完整证明

### 步骤 1：剥离素数 2 的 Euler 因子

每个模 $2p$ 的奇特征 $\chi \in X_{2p}^-$ 由唯一的模 $p$ 本原奇特征 $\chi^* \in X_p^-$ 诱导，且 $L(s, \chi) = (1 - \chi^*(2)2^{-s})L(s, \chi^*)$。取对数导数得
$$\frac{L'}{L}\!\left(\frac{1}{2} + \sigma + it, \chi\right) - \frac{L'}{L}\!\left(\frac{1}{2} + \sigma + it, \chi^*\right) = \frac{\chi^*(2)\log 2}{2^{1/2 + \sigma + it} - \chi^*(2)}.$$
因 $\sigma > 0$，右端绝对值一致不超过 $\frac{\log 2}{\sqrt{2} - 1} < 2$。此后记 $g_\chi(t) := \frac{L'}{L}(\frac{1}{2}+\sigma+it, \chi)$（$\chi \in X_p^-$），由 $\mathcal{L}$ 中的反三角不等式得
$$\left|\sqrt{M_{2p}(c)} - \|\psi g\|_{\mathcal{L}}\right| \le 2. \tag{2.1}$$

### 步骤 2：虚部消去（严格移线与一致余项）

由恒等式 $|z|^2 = 2(\Re z)^2 - \Re(z^2)$，对每个 $\chi \in X_p^-$ 有
$$\int_{\mathbb{R}} w(t)|g_\chi(t)|^2\,\mathrm{d}t = 2\int_{\mathbb{R}} w(t)(\Re g_\chi(t))^2\,\mathrm{d}t - \Re J_\chi(\sigma),$$
其中令 $s = \sigma + it$（从而 $-t^2 = (s - \sigma)^2$）：
$$J_\chi(\sigma) := \int_{\mathbb{R}} \frac{e^{-t^2}}{\sqrt{\pi}}\,g_\chi(t)^2\,\mathrm{d}t = \frac{1}{i\sqrt{\pi}}\int_{\sigma - i\infty}^{\sigma + i\infty} e^{(s-\sigma)^2}\left(\frac{L'}{L}\!\left(\frac{1}{2} + s, \chi\right)\right)^2\mathrm{d}s.$$
因 $\chi \in X_p^-$ 非主特征，在 GRH 下被积函数在 $\Re s > 0$ 全纯。在带状区域 $\sigma \le \Re s \le 2$ 内，一方面 $|\frac{L'}{L}(\frac{1}{2}+s, \chi)| \ll \sigma^{-1}\log(p(2+|\Im s|))$，另一方面
$$\left|e^{(s-\sigma)^2}\right| = e^{(\Re s - \sigma)^2 - (\Im s)^2} \le e^4 e^{-(\Im s)^2}.$$
故水平边界在 $|\Im s| = T \to \infty$ 时超指数衰减至 $0$。将围道平移至 $\Re s = 2$（此处 $|\frac{L'}{L}(\frac{5}{2}+it,\chi)| \le -\frac{\zeta'}{\zeta}(\frac{5}{2}) = O(1)$），得对所有 $p, \chi \in X_p^-$ 与 $\sigma \in (0, 2)$ 一致有 $|J_\chi(\sigma)| \ll 1$。对 $\chi$ 平均并结合 (2.1)：
$$\|\psi g\|_{\mathcal{L}}^2 = 2\|\psi\Re g\|_{\mathcal{L}}^2 + O(1) \implies \left|\sqrt{M_{2p}(c)} - \sqrt{2}\|\psi\Re g\|_{\mathcal{L}}\right| = O(1). \tag{2.2}$$

### 步骤 3：Hadamard–Poisson 展开与交换子 $L^2$ 估计

对本原奇特征 $\chi \in X_p^-$（$\kappa_\chi = 1$），完备 $L$-函数 $\Lambda(s,\chi) = (p/\pi)^{(s+1)/2}\Gamma(\frac{s+1}{2})L(s,\chi)$ 的 Hadamard 乘积取实部，结合 $\Re B(\chi) = -\sum_{\rho_\chi}\Re\frac{1}{\rho_\chi}$（在 GRH 下绝对收敛）得
$$\Re g_\chi(t) = \sum_{\gamma_\chi} P_\sigma(t - \gamma_\chi) - \frac{1}{2}\log\frac{p}{\pi} - \frac{1}{2}\Re\frac{\Gamma'}{\Gamma}\!\left(\frac{3/2 + \sigma + it}{2}\right), \qquad P_\sigma(u) := \frac{\sigma}{\sigma^2 + u^2}.$$
Gamma 项绝对值 $\ll \log(2 + |t|)$，乘以 $\psi(t)$ 后在 $\mathcal{L}$ 中范数为 $O(1)$。定义
$$U_\chi(t) := \psi(t)\left(\sum_{\gamma_\chi} P_\sigma(t - \gamma_\chi) - \frac{1}{2}\log\frac{p}{\pi}\right), \qquad V_\chi(t) := \sum_{\gamma_\chi} \psi(\gamma_\chi)P_\sigma(t - \gamma_\chi) - \frac{1}{2}\left(\log\frac{p}{\pi}\right)\psi(t).$$
则 $\|\psi\Re g - U\|_{\mathcal{L}} = O(1)$。下估交换子
$$E_\chi(t) := U_\chi(t) - V_\chi(t) = \sum_{\gamma_\chi} \big(\psi(t) - \psi(\gamma_\chi)\big)P_\sigma(t - \gamma_\chi).$$

记 $n_\chi(t; h) := \#\{\gamma_\chi : |\gamma_\chi - t| \le h\}$。在 GRH 下，Littlewood–Selberg 幅角估计 $S(t, \chi) = \frac{1}{\pi}\arg L(\frac{1}{2}+it,\chi) \ll \frac{\log(p(2+|t|))}{\log\log(p(2+|t|))}$ 给出对一切 $h > 0$ 一致成立的短区间零点计数：
$$n_\chi(t; h) = \frac{h}{\pi}\log(p(2+|t|)) + O\!\left(\frac{\log(p(2+|t|))}{\log\log(p(2+|t|))}\right) \ll \left(h L + \frac{L}{\log L}\right)\left(1 + \frac{\log(2+|t|)}{L}\right).$$
取 $J := \lceil\log_2(L/c)\rceil \asymp \log L$ 使 $2^J\sigma \in [1, 2)$，将 $E_\chi(t)$ 按 $|\gamma_\chi - t|$ 拆为三段：
1. **$|\gamma_\chi - t| \le \sigma$**：因 $|\psi'(u)| = |u|\pi^{-1/4}e^{-u^2/2} \ll e^{-u^2/3}$，当 $|u - t| \le 2$ 时有 $|\psi'(u)| \ll e^{-t^2/4}$。由中值定理 $|\psi(t) - \psi(\gamma_\chi)| \ll \sigma e^{-t^2/4}$，而 $P_\sigma \le \sigma^{-1}$，故总贡献
   $$\ll e^{-t^2/4}n_\chi(t; \sigma) \ll_c \frac{L}{\log L}e^{-t^2/4}\left(1 + \frac{\log(2+|t|)}{L}\right).$$
2. **$2^{j-1}\sigma < |\gamma_\chi - t| \le 2^j\sigma$（$1 \le j \le J$）**：$|\psi(t) - \psi(\gamma_\chi)| \ll 2^j\sigma e^{-t^2/4}$，$P_\sigma \le \frac{\sigma}{(2^{j-1}\sigma)^2} = \frac{4}{2^{2j}\sigma}$，每项乘积 $\ll 2^{-j}e^{-t^2/4}$。对 $j = 1, \dots, J$ 求和：
   $$\ll e^{-t^2/4}\sum_{j=1}^J 2^{-j} n_\chi(t; 2^j\sigma) \ll e^{-t^2/4}\left(1 + \frac{\log(2+|t|)}{L}\right)\sum_{j=1}^J \left(c + 2^{-j}\frac{L}{\log L}\right) \ll_c \frac{L}{\log L}e^{-t^2/4}\left(1 + \frac{\log(2+|t|)}{L}\right).$$
3. **$|\gamma_\chi - t| > 2^J\sigma \ge 1$**：用 $|\psi(t) - \psi(\gamma_\chi)| \le |\psi(t)| + |\psi(\gamma_\chi)|$ 拆分：
   - $|\psi(t)|$ 部分：$\le \sigma|\psi(t)|\sum_{|\gamma_\chi-t|>1}(t-\gamma_\chi)^{-2} \ll \sigma|\psi(t)|\log(p(2+|t|)) \ll_c |\psi(t)|(1 + \log(2+|t|))$，其 $L^2(\mathbb{R})$ 范数为 $O_c(1)$。
   - $|\psi(\gamma_\chi)|$ 部分：在 $|t| \le 2$ 上 $\le \sigma\sum_{\gamma_\chi}\psi(\gamma_\chi) \ll \sigma L = c$；在 $|t| > 2$ 上按 $|\gamma_\chi| \le |t|/2$（得 $\ll \frac{\sigma}{t^2}\sum_\gamma \psi(\gamma) \ll \frac{c}{t^2}$）与 $|\gamma_\chi| > |t|/2$（得 $\ll \sigma e^{-t^2/8}\sum_\gamma e^{-\gamma^2/4} \ll c e^{-t^2/8}$）拆分，其 $L^2(\mathbb{R})$ 范数亦为 $O_c(1)$。

综合三段并在 $t \in \mathbb{R}$ 上取 $L^2$ 范数，对所有 $\chi \in X_p^-$ 一致得 $\|E_\chi\|_{L^2(\mathbb{R})} \ll_c L/\log L$。结合 (2.2) 得
$$\left|\sqrt{M_{2p}(c)} - \sqrt{2}\|V\|_{\mathcal{L}}\right| \ll_c \frac{L}{\log L}. \tag{2.3}$$

### 步骤 4：Plancherel 与低频 Weil–Guinand 显式公式

由 $\widehat{P_\sigma}(\xi) = \pi e^{-2\pi\sigma|\xi|}$ 及对固定 $p$ 的绝对可和性 $\sum_{\gamma_\chi}\psi(\gamma_\chi) < \infty$，逐项取 Fourier 变换得
$$\widehat{V_\chi}(\xi) = \pi e^{-2\pi\sigma|\xi|}S_\chi(\xi) - \frac{1}{2}\left(\log\frac{p}{\pi}\right)\widehat{\psi}(\xi), \qquad S_\chi(\xi) := \sum_{\gamma_\chi} \psi(\gamma_\chi)e^{-2\pi i\xi\gamma_\chi}. \tag{2.4}$$

对 Schwartz 测试函数 $H_\xi(t) = \psi(t)e^{-2\pi i\xi t}$（满足 $\widehat{H_\xi}(\eta) = \widehat{\psi}(\xi + \eta)$），模 $p$ 本原奇特征（$\kappa_\chi = 1$）的 Weil–Guinand 显式公式（Rudnick–Sarnak Prop. 2.1）给出
$$S_\chi(\xi) = \frac{\log(p/\pi)}{2\pi}\widehat{\psi}(\xi) + R_\chi(\xi), \tag{2.5}$$
其中
$$R_\chi(\xi) := G(\xi) - \frac{1}{2\pi}\sum_{n=1}^\infty \frac{\Lambda(n)}{\sqrt{n}}\left\{\chi(n)\widehat{\psi}\!\left(\xi + \frac{\log n}{2\pi}\right) + \bar\chi(n)\widehat{\psi}\!\left(\xi - \frac{\log n}{2\pi}\right)\right\},$$
$$G(\xi) := \frac{1}{2\pi}\int_{\mathbb{R}} \psi(t)e^{-2\pi i\xi t}\Re\frac{\Gamma'}{\Gamma}\!\left(\frac{3}{4} + \frac{it}{2}\right)\mathrm{d}t.$$

**断言（低频均方界）**：当 $p$ 充分大时，
$$\mathbb{E}_{\chi \in X_p^-}\int_{|\xi| \le \sqrt{L}} |R_\chi(\xi)|^2\,\mathrm{d}\xi = O(L). \tag{2.6}$$

*断言的证明*：
1. **Gamma 项**：$G(\xi)$ 与 $p, \chi$ 无关，由 Plancherel 得 $\int_{|\xi|\le\sqrt{L}} |G(\xi)|^2\,\mathrm{d}\xi \le \int_{\mathbb{R}} |G(\xi)|^2\,\mathrm{d}\xi = O(1)$。
2. **高斯尾部截断（$n > x_p$）**：取 $x_p := e^{4\pi\sqrt{L}}$。因 $8\pi\sqrt{\log(2p)} = o(\log p)$，对充分大的 $p$ 满足 $x_p^2 < p - 1$。对任意 $|\xi| \le \sqrt{L}$ 与 $n > x_p$，有 $\frac{\log n}{2\pi} > 2\sqrt{L} \ge 2|\xi|$，故 $|\xi \pm \frac{\log n}{2\pi}| \ge \frac{\log n}{4\pi}$。代入 $\widehat{\psi}(u) = \sqrt{2}\pi^{1/4}e^{-2\pi^2 u^2}$：
   $$2\pi^2\left(\frac{\log n}{4\pi}\right)^2 = \frac{(\log n)^2}{8} = \frac{(\log n)^2}{16} + \frac{(\log n)^2}{16} \ge \pi^2 L + 2\log n \qquad (p \text{ 充分大}).$$
   因此尾部绝对值一致不超过 $O\!\left(e^{-\pi^2 L}\sum_{n > x_p}\Lambda(n)n^{-5/2}\right) = O(e^{-\pi^2 L})$，其在 $|\xi| \le \sqrt{L}$ 上的 $L^2$ 积分贡献为 $O(\sqrt{L}e^{-2\pi^2 L}) = o(1)$。
3. **主部截断和（$n \le x_p$）与精确奇特征正交**：令 $a_n(\xi) := \frac{\Lambda(n)}{2\pi\sqrt{n}}\widehat{\psi}(\xi + \frac{\log n}{2\pi}) \in \mathbb{R}$，$b_n(\xi) := a_n(-\xi) \in \mathbb{R}$，记 $P_\chi(\xi) := \sum_{n \le x_p}(a_n(\xi)\chi(n) + b_n(\xi)\bar\chi(n))$。展开 $|P_\chi(\xi)|^2$：
   $$|P_\chi(\xi)|^2 = \sum_{m, n \le x_p}\Big[(a_m a_n + b_m b_n)\chi(m)\bar\chi(n) + a_m b_n\chi(m)\chi(n) + b_m a_n\bar\chi(m)\bar\chi(n)\Big].$$
   因 $1 \le m, n \le x_p < p$，均有 $(mn, p) = 1$，套用模 $p$ 奇特征精确正交关系：
   $$\mathbb{E}_{\chi \in X_p^-}\chi(m)\bar\chi(n) = \mathbf{1}_{m \equiv n\,(p)} - \mathbf{1}_{m \equiv -n\,(p)}, \qquad \mathbb{E}_{\chi \in X_p^-}\chi(m)\chi(n) = \mathbf{1}_{mn \equiv 1\,(p)} - \mathbf{1}_{mn \equiv -1\,(p)}.$$
   在 $x_p^2 < p - 1$ 下逐项核查：
   - $m \equiv n \pmod p \iff m = n$（因 $1 \le m, n < p$）；
   - $m \equiv -n \pmod p$ 无解（因 $2 \le m + n \le 2x_p < p$）；
   - $mn \equiv 1 \pmod p \iff mn = 1 \iff m = n = 1$，而 $\Lambda(1) = 0$ 故 $a_1 = b_1 = 0$；
   - $mn \equiv -1 \pmod p$ 无解（因 $2 \le mn + 1 \le x_p^2 + 1 < p$）。

   故所有非对角、相反同余与乘积同余项精确为零，得恒等式
   $$\mathbb{E}_{\chi \in X_p^-}|P_\chi(\xi)|^2 = \sum_{n \le x_p}\left(a_n(\xi)^2 + b_n(\xi)^2\right).$$
   对 $|\xi| \le \sqrt{L}$ 积分并放缩至 $\mathbb{R}$，由 $\|\widehat{\psi}\|_2^2 = 1$ 与 Chebyshev 估计：
   $$\int_{|\xi| \le \sqrt{L}} \mathbb{E}_{\chi \in X_p^-}|P_\chi(\xi)|^2\,\mathrm{d}\xi \le \frac{1}{4\pi^2}\sum_{n \le x_p}\frac{\Lambda(n)^2}{n} \cdot 2\|\widehat{\psi}\|_2^2 = \frac{1}{2\pi^2}\sum_{n \le x_p}\frac{\Lambda(n)^2}{n} \ll (\log x_p)^2 = 16\pi^2 L = O(L).$$
综合三部分即证 (2.6)。

### 步骤 5：合并低频与高频

由 Plancherel，$2\|V\|_{\mathcal{L}}^2 = 2\,\mathbb{E}_\chi\int_{|\xi|\le\sqrt{L}} |\widehat{V_\chi}(\xi)|^2\,\mathrm{d}\xi + 2\,\mathbb{E}_\chi\int_{|\xi|>\sqrt{L}} |\widehat{V_\chi}(\xi)|^2\,\mathrm{d}\xi$。

- **低频 $|\xi| \le \sqrt{L}$**：将 (2.5) 代入 (2.4) 得
  $$\widehat{V_\chi}(\xi) = \frac{1}{2}\left(\log\frac{p}{\pi}\right)\left(e^{-2\pi\sigma|\xi|} - 1\right)\widehat{\psi}(\xi) + \pi e^{-2\pi\sigma|\xi|}R_\chi(\xi).$$
  因 $|e^{-2\pi\sigma|\xi|} - 1| \le 2\pi\sigma|\xi| = \frac{2\pi c}{L}|\xi|$ 且 $\frac{1}{2}\log\frac{p}{\pi} \le \frac{L}{2}$，第一项绝对值 $\le \pi c|\xi|\,|\widehat{\psi}(\xi)|$，其 $L^2(\mathbb{R})$ 范数为 $O_c(1)$。结合 (2.6) 得
  $$2\,\mathbb{E}_{\chi \in X_p^-}\int_{|\xi| \le \sqrt{L}} |\widehat{V_\chi}(\xi)|^2\,\mathrm{d}\xi = O_c(L).$$

- **高频 $|\xi| > \sqrt{L}$**：(2.4) 中第二项 $-\frac{1}{2}(\log\frac{p}{\pi})\widehat{\psi}(\xi)$ 在 $|\xi| > \sqrt{L}$ 上的 $L^2$ 范数为 $O(Le^{-2\pi^2 L}) = o(1)$。对第一项作变量替换 $\xi = \frac{L}{2\pi}y$（$\mathrm{d}\xi = \frac{L}{2\pi}\,\mathrm{d}y$，$4\pi\sigma|\xi| = 2c|y|$），并利用 $\widetilde{F}_{2p}(y)$ 为偶函数：
  $$2\,\mathbb{E}_{\chi \in X_p^-}\int_{|\xi| > \sqrt{L}} \pi^2 e^{-4\pi\sigma|\xi|}|S_\chi(\xi)|^2\,\mathrm{d}\xi = 2 \cdot \pi^2 \cdot \frac{L}{2\pi} \cdot \frac{L}{2\pi} \cdot 2\int_{2\pi/\sqrt{L}}^\infty e^{-2cy}\widetilde{F}_{2p}(y)\,\mathrm{d}y = L^2\int_{2\pi/\sqrt{L}}^\infty e^{-2cy}\widetilde{F}_{2p}(y)\,\mathrm{d}y.$$

在 $L^2(X_p^- \times \mathbb{R})$ 中用反三角不等式合并低高频估计，得
$$\left|\sqrt{2}\|V\|_{\mathcal{L}} - L\left(\int_{2\pi/\sqrt{L}}^\infty e^{-2cy}\widetilde{F}_{2p}(y)\,\mathrm{d}y\right)^{1/2}\right| \ll_c \sqrt{L}.$$
结合 (2.3) 并两边同除以 $L$，即证 Lemma 2。 $\square$
