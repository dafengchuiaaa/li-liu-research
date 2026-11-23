# Li–Liu 最弱谱假设 S 与模 $p$ 奇特征零点对关联测度收敛：完整证明总稿

本总稿将独立核验并修正闭合后的 **Lemma 1、Lemma 2、Lemma 3 与主定理 W1** 整合为一套单向无循环依赖的完整证明链，可直接用于整体审校或拆分提交至仓库 `dafengchuiaaa/li-liu-research`。

---

## 一、总假设与统一记号

设 $p \to \infty$ 为奇素数，$N = 2p$，$L = \log(2p)$，$\alpha_N = 1/L$，$\beta = 1/8$。假设 $\mathrm{GRH}(2p)$ 成立。
- $X_p^-$ 为模 $p$ 的本原奇特征族（$|X_p^-| = \frac{p-1}{2}$），记 $\mathbb{E}_{\chi \in X_p^-} := \frac{2}{p-1}\sum_{\chi \in X_p^-}$；$X_{2p}^-$ 为模 $2p$ 的奇特征族（与 $X_p^-$ 一一对应诱导）。
- 对 $\chi \in X_p^-$，记 $L(s, \chi)$ 的非平凡零点为 $\rho_\chi = \frac{1}{2} + i\gamma_\chi$（$\gamma_\chi \in \mathbb{R}$，计重数）。
- 固定高斯窗 $\psi(t) = \pi^{-1/4}e^{-t^2/2}$，$w(t) = \psi(t)^2 = \pi^{-1/2}e^{-t^2}$；Fourier 变换 $\widehat{f}(\xi) = \int_{\mathbb{R}} f(t)e^{-2\pi i\xi t}\,\mathrm{d}t$，则 $\|\psi\|_2 = \|\widehat{\psi}\|_2 = 1$，$\widehat{\psi}(\xi) = \sqrt{2}\pi^{1/4}e^{-2\pi^2\xi^2}$。
- 对固定 $c > 1$（记 $\sigma = c/L$）与 $y \in \mathbb{R}$，定义
  $$M_{2p}(c) := \int_{\mathbb{R}} w(t)\,\mathscr{P}_{2p}(\sigma + it, \sigma - it)\,\mathrm{d}t, \qquad \widetilde{F}_{2p}(y) := \frac{2\pi}{L}\,\mathbb{E}_{\chi \in X_p^-}\left|\sum_{\gamma_\chi} \psi(\gamma_\chi)e^{-iyL\gamma_\chi}\right|^2.$$
- Li–Liu 算子 $T_{2p}$ 作用在 Hardy 空间 $\mathcal{H}_{2p} = H^2(S_{2p})$（$S_{2p} = \{\alpha_N < \Re s < \beta\}$，内积 $\langle h, g\rangle = \int_{\Gamma_{2p}} h(s)\overline{g(s)}\,|\mathrm{d}s|$ 无 $1/(2\pi)$ 因子）上，积分核为 $\frac{\mathscr{E}_{2p}(s, \bar{z})}{(1+s)(1+\bar{z})}$，其中 $\mathscr{E}_{2p}(s, z) = \mathscr{P}_{2p}(s, z) - \mathscr{D}_{2p}(s+z) - \mathscr{K}_{2p}(s, z)$，
  $$\mathscr{K}_{2p}(s, z) = \mathfrak{S}(2p)\left(\frac{\pi}{2p}\right)^{s+z} P_{2p}(s+z)\,\zeta(1 - s - z)\,\mathcal{X}_1(s)\,\mathcal{X}_1(z), \qquad P_{2p}(w) = \prod_{\substack{\ell > 2 \\ \ell \ne p}}\left(1 + \frac{\ell^{-w}}{\ell - 2}\right).$$

---

## 二、Lemma 1（Cauchy 边界局部化与连续核主项）

**命题**：在 $\mathrm{GRH}(2p)$ 下，对任意固定 $c > 1$，
$$\frac{M_{2p}(c)}{L^2} = \frac{1 - e^{-2c}}{4c^2} + O_c\!\left(\frac{\|T_{2p}\|}{L} + L^{-1/4}\right).$$

**证明**：
1. **主项**：记 $H_{2p}(w) = \mathfrak{S}(2p)P_{2p}(w)/\zeta(1+w)$，逐素因子核验得 $H_{2p}(0) = 1$ 且在 $|w| \le 1/4$ 上一致解析，故 $H_{2p}(2c/L) = 1 + O_c(1/L)$。结合 $\zeta(1 \pm 2c/L) = \pm\frac{L}{2c} + O(1)$、$(\frac{\pi}{2p})^{2c/L} = e^{-2c}(1 + O_c(1/L))$ 以及 $|\mathcal{X}_1(c/L + it_0)|^2 = 1 + O_c(L^{-1}\log(2+|t_0|))$（对所有 $t_0 \in \mathbb{R}$ 一致），得 $\mathscr{K}_{2p}(c/L+it_0, c/L-it_0) = -\frac{e^{-2c}}{4c^2}L^2 + O_c(L\log(2+|t_0|))$。加上 $\mathscr{D}_{2p}(2c/L) = \frac{L^2}{4c^2} + O(1)$ 并对 $w(t_0)\,\mathrm{d}t_0$ 积分，得 $\frac{1-e^{-2c}}{4c^2}L^2 + O_c(L)$。
2. **双边界围道平移**：取 $\varepsilon = c - 1 > 0$ 与 $h(s) = \frac{\sqrt{\varepsilon\alpha_N}}{s - z_0} \in \mathcal{H}_{2p}$（$z_0 = (1-\varepsilon)\alpha_N + it_0$，$\|h\|^2 = \pi + O_\varepsilon(1/L)$）。按 $\Gamma_N = L_N \sqcup R_N$ 拆解 $\langle T_{2p}h, h\rangle = I_{LL} + I_{LR} + I_{RL} + I_{RR}$。在 $I_{LL}$ 中将 $z$ 移至 $\Re(2\alpha_N - z) = 3/4$、$s$ 移至 $\Re s = 3/4$（全纯带 $0 < \Re s, \Re w < 3/2$ 内水平段由 $\zeta$ 凸性界/函数方程与 $|\mathcal{X}_1(s)| \ll (1+|\Im s|)^{-\Re s}$ 抵消为 $O(T^{-13/8+\delta}) \to 0$），提取双留数主项 $\frac{4\pi^2\varepsilon}{L}\frac{\mathscr{E}_{2p}(c/L+it_0, c/L-it_0)}{|1+c/L+it_0|^2}$。
3. **余项与自举**：记 $X(t_0) = \mathscr{P}_{2p}(c/L+it_0, c/L-it_0)$。在 $\Re s = 3/4$ 上 $|\frac{L'}{L}(\frac{5}{4}+it,\chi)| = O(1)$；在 $\beta = 1/8$ 上由 GRH 界 $|\frac{L'}{L}(\frac{5}{8}+it,\chi)| \ll (\log(p(2+|t|)))^{3/4}$。对单留数交叉项沿 $\chi$ 及 $t_0$ 用 Cauchy–Schwarz，得
   $$\left|M_{2p}(c) - \frac{1-e^{-2c}}{4c^2}L^2\right| \ll_c L\|T_{2p}\| + L^{3/2} + L^{3/4}\sqrt{M_{2p}(c)}.$$
   令 $Y = M_{2p}(c)/L^2$，由 $Y \le A + B\sqrt{Y} \implies Y \le 2A + B^2$ 自动闭合，无需任何先验均方上界。 $\square$

---

## 三、Lemma 2（Hadamard–Poisson–Plancherel 等价）

**命题**：在 $\mathrm{GRH}(2p)$ 下，对任意固定 $c > 1$，
$$\left|\frac{\sqrt{M_{2p}(c)}}{L} - \left(\int_{2\pi/\sqrt{L}}^\infty e^{-2cy}\widetilde{F}_{2p}(y)\,\mathrm{d}y\right)^{1/2}\right| \ll_c \frac{1}{\log L}.$$

**证明**：记 $\mathcal{L} = L^2(X_p^- \times \mathbb{R}, \frac{2}{p-1}\#\otimes\mathrm{d}t)$，$g_\chi(t) = \frac{L'}{L}(\frac{1}{2}+\sigma+it, \chi)$（$\chi \in X_p^-$）。
1. **剥离素数 2**：诱导差 $\frac{\chi^*(2)\log 2}{2^{1/2+\sigma+it}-\chi^*(2)}$ 绝对值 $< 2$，故 $|\sqrt{M_{2p}(c)} - \|\psi g\|_{\mathcal{L}}| \le 2$。
2. **虚部消去**：$|g_\chi|^2 = 2(\Re g_\chi)^2 - \Re(g_\chi^2)$；将 $\int \frac{e^{-t^2}}{\sqrt{\pi}}g_\chi(t)^2\,\mathrm{d}t = \frac{1}{i\sqrt{\pi}}\int_{\sigma-i\infty}^{\sigma+i\infty} e^{(s-\sigma)^2}(\frac{L'}{L}(\frac{1}{2}+s,\chi))^2\,\mathrm{d}s$ 移至 $\Re s = 2$（水平段因 $|e^{(s-\sigma)^2}| \le e^4 e^{-(\Im s)^2}$ 超指数消失），一致得 $O(1)$，故 $|\sqrt{M_{2p}(c)} - \sqrt{2}\|\psi\Re g\|_{\mathcal{L}}| = O(1)$。
3. **Hadamard–Poisson 与交换子**：$\Re g_\chi(t) = \sum_{\gamma_\chi} P_\sigma(t-\gamma_\chi) - \frac{1}{2}\log\frac{p}{\pi} - \frac{1}{2}\Re\frac{\Gamma'}{\Gamma}(\frac{3/2+\sigma+it}{2})$，Gamma 项在 $\mathcal{L}$ 中为 $O(1)$。令 $V_\chi(t) = \sum_{\gamma_\chi}\psi(\gamma_\chi)P_\sigma(t-\gamma_\chi) - \frac{1}{2}(\log\frac{p}{\pi})\psi(t)$，交换子 $E_\chi(t) = \sum_{\gamma_\chi}(\psi(t)-\psi(\gamma_\chi))P_\sigma(t-\gamma_\chi)$ 按 $|\gamma_\chi-t| \le \sigma$、二进环 $2^{j-1}\sigma < |\gamma_\chi-t| \le 2^j\sigma$（$1 \le j \le J \asymp \log L$）及 $> 1$ 三段拆解，用 GRH 界 $S(t,\chi) \ll \frac{\log(p(2+|t|))}{\log\log(p(2+|t|))}$ 一致得 $\|E_\chi\|_{L^2(\mathbb{R})} \ll_c L/\log L$，故 $|\sqrt{M_{2p}(c)} - \sqrt{2}\|V\|_{\mathcal{L}}| \ll_c L/\log L$。
4. **低频显式公式均方界**：由 $\widehat{P_\sigma}(\xi) = \pi e^{-2\pi\sigma|\xi|}$，$\widehat{V_\chi}(\xi) = \pi e^{-2\pi\sigma|\xi|}S_\chi(\xi) - \frac{1}{2}(\log\frac{p}{\pi})\widehat{\psi}(\xi)$，其中 Weil–Guinand 显式公式给出 $S_\chi(\xi) = \frac{\log(p/\pi)}{2\pi}\widehat{\psi}(\xi) + R_\chi(\xi)$。取 $x_p = e^{4\pi\sqrt{L}}$（$x_p^2 < p - 1$）：
   - $n > x_p$ 尾部：对 $|\xi| \le \sqrt{L}$ 有 $|\xi \pm \frac{\log n}{2\pi}| \ge \frac{\log n}{4\pi}$，从而 $2\pi^2(\frac{\log n}{4\pi})^2 = \frac{(\log n)^2}{8} \ge \pi^2 L + 2\log n$，总贡献 $O(e^{-\pi^2 L})$；
   - $n \le x_p$ 主部：用模 $p$ 奇特征精确正交关系 $\mathbb{E}_\chi\chi(m)\bar\chi(n) = \mathbf{1}_{m\equiv n(p)} - \mathbf{1}_{m\equiv -n(p)}$ 及 $\mathbb{E}_\chi\chi(m)\chi(n) = \mathbf{1}_{mn\equiv 1(p)} - \mathbf{1}_{mn\equiv -1(p)}$，在 $x_p^2 < p - 1$ 下 $m\equiv -n$、$mn\equiv -1$ 无解，$mn\equiv 1$ 仅 $m=n=1$（$\Lambda(1)=0$），仅剩对角项 $\frac{1}{2\pi^2}\sum_{n\le x_p}\frac{\Lambda(n)^2}{n} \ll (\log x_p)^2 = 16\pi^2 L$。
   故 $\mathbb{E}_\chi\int_{|\xi|\le\sqrt{L}} |R_\chi(\xi)|^2\,\mathrm{d}\xi = O(L)$。
5. **Plancherel 合并**：在 $|\xi| \le \sqrt{L}$ 上，$\widehat{V_\chi}(\xi) = \frac{1}{2}(\log\frac{p}{\pi})(e^{-2\pi\sigma|\xi|}-1)\widehat{\psi}(\xi) + \pi e^{-2\pi\sigma|\xi|}R_\chi(\xi)$，两项均方总和为 $O_c(L)$；在 $|\xi| > \sqrt{L}$ 上，作替换 $\xi = \frac{L}{2\pi}y$ 并利用偶性得主项 $L^2\int_{2\pi/\sqrt{L}}^\infty e^{-2cy}\widetilde{F}_{2p}(y)\,\mathrm{d}y$（常数 $2\cdot\pi^2\cdot\frac{L}{2\pi}\cdot\frac{L}{2\pi}\cdot 2 = L^2$）。反三角不等式合并即证 Lemma 2。 $\square$

---

## 四、Lemma 3（零频质量集中）

**命题**：在 $\mathrm{GRH}(2p)$ 下，
$$\int_0^{2\pi/\sqrt{L}} \widetilde{F}_{2p}(y)\,\mathrm{d}y = \frac{1}{2} + O\!\left(L^{-1/2}\right).$$

**证明**：偶性折半并替换 $y = \frac{2\pi}{L}\xi$ 得 $\frac{2\pi^2}{L^2}\mathbb{E}_\chi\int_{|\xi|\le\sqrt{L}} |\frac{\log(p/\pi)}{2\pi}\widehat{\psi}(\xi) + R_\chi(\xi)|^2\,\mathrm{d}\xi$。主项为 $\frac{1}{2}(\frac{\log(p/\pi)}{L})^2(1 - O(e^{-4\pi^2 L})) = \frac{1}{2} + O(L^{-1})$，余项平方由 $\mathbb{E}_\chi\int_{|\xi|\le\sqrt{L}}|R_\chi|^2 = O(L)$ 得 $O(L^{-1})$，交叉项由 Cauchy–Schwarz 得 $O(L^{-1/2})$。 $\square$

---

## 五、主定理 W1（条件性测度弱收敛）

**定理**：设沿全部充分大的奇素数 $p$ 成立 $\mathrm{GRH}(2p)$ 与 $\|T_{2p}\| = o(\log p)$。令 $\mathrm{d}\mu_p(y) = e^{-3y}\widetilde{F}_{2p}(y)\mathbf{1}_{y>2\pi/\sqrt{L}}\,\mathrm{d}y$，$\mathrm{d}\nu_p(y) = e^{-3y}\widetilde{F}_{2p}(y)\mathbf{1}_{y\ge 0}\,\mathrm{d}y$。则：
1. $\mu_p \Rightarrow e^{-3y}\min(y, 1)\,\mathrm{d}y$，且 $\nu_p \Rightarrow \frac{1}{2}\delta_0 + e^{-3y}\min(y, 1)\,\mathrm{d}y$；
2. 对任意 $f \in C_c([0, \infty))$，$\int_{2\pi/\sqrt{L}}^\infty f(y)\widetilde{F}_{2p}(y)\,\mathrm{d}y \to \int_0^\infty f(y)\min(y,1)\,\mathrm{d}y$ 且 $\int_0^\infty f(y)\widetilde{F}_{2p}(y)\,\mathrm{d}y \to \frac{1}{2}f(0) + \int_0^\infty f(y)\min(y,1)\,\mathrm{d}y$。

**证明**：对任意 $\lambda > -1$ 取 $c = \frac{\lambda+3}{2} > 1$，联合 Lemma 1 与 Lemma 2 得 $\mathcal{L}\mu_p(\lambda) \to \frac{1-e^{-2c}}{4c^2} = \mathcal{L}\mu(\lambda)$。取 $\lambda = 0$ 得总质量一致有界，取 $\lambda = -1/2$ 得 $\mu_p([R,\infty)) \le e^{-R/2}\mathcal{L}\mu_p(-1/2) \ll e^{-R/2}$（一致紧性）；由 Prokhorov 定理与 Laplace 变换唯一性得 $\mu_p \Rightarrow \mu$。乘以 $e^{3y}$ 得局部弱收敛；结合 Lemma 3 与测试函数在 $0$ 处的连续性得低频部分弱收敛于 $\frac{1}{2}\delta_0$，从而 $\nu_p \Rightarrow \frac{1}{2}\delta_0 + \mu$。 $\square$
