# Li–Liu 谱假设 S：研究档案

> **研究状态：开放问题。** 本档案由 2026-11-23 前后 Gemini 与 GPT 的研究交接、证明草稿和交叉核查整理。**不是**已发表论文或完整验证证明。

## 当前目标

考察 Li–Liu 的弱谱假设 S。在 Dirichlet GRH 和原论文谱对应定理成立的条件下，最弱 S 等价于

\[
\lim_{N\to\infty,\;2\mid N}\frac{\|T_N\|}{\mathfrak S(N)}=0.
\]

**当前优先路线（分支 2）：** 研究较弱假设 `||T_{2p}||=o(log p)` 对模素数 `p` 的奇 Dirichlet 特征零点对关联形式因子的必要条件。预期的**候选条件性结论**：

\[
e^{-3y}\widetilde F_{2p}(y)\mathbf 1_{y>2\pi/\sqrt{\log(2p)}}\,dy
\Rightarrow e^{-3y}\min(y,1)\,dy.
\]

这是一条 **待证** 的测度收敛命题，不得表述成已证完整 GUE 猜想。

## 研究档案怎么读

- [`STATUS.md`](STATUS.md)：**唯一的进度索引**。后续新增或修正证据时必须同步更新。
- [`verified/`](verified/)：独立代数证明/可核验的普适不等式；均注明依赖。
- [`conditional/`](conditional/)：条件性推导（基于论文定理或待复核解析引理）。
- [`needs-review/`](needs-review/)：Gemini 已提出，但尚未完成独立解析审计的证明环节。
- [`invalidated/`](invalidated/)：**明确不能使用的旧证明**及失败原因。
- [`history/`](history/)：各轮 Gemini 推导版本的**重构性摘要**和审查轨迹，并非逐字逐式的原稿存档。
- [`links/`](links/)：论文与外部 Lean 项目。

## 核心结论（截至 2026-11-23）

1. 原始强 R 的反驳与最弱 S 是不同任务。旧 GRH 否定最弱 S 的尝试已失败。
2. 旧推导把 `P_N(w)` 的 `ℓ∤N` 错录为 `ℓ∣N`，从而把连续核主项少算一阶 `log N`。
3. 对 `N=2p`，真实 Euler 乘积给出 `\mathfrak S(2p)P_{2p}(2c/L)\sim L/(2c)`，使连续核具有 `-e^{-2c}L²/(4c²)` 的主项。
4. 由此推测的零点形式因子极限为 `min(y,1)`，不是旧稿的 `y`；旧 Fejér 矛盾消失。
5. `Lemma 1` 的核心结论可考虑由 Li–Liu Proposition 5.4 的再生核估计直接导出，但**尚应核对原论文精确常数及核的加权误差**；`Lemma 2/3` 继续审计。

## 保护原成果

已公开的 [li-liu-spectral-r-lean](https://github.com/dafengchuiaaa/li-liu-spectral-r-lean) 仍保持独立。其七项 Lean 定理证明与旧 R 审查有关的离散恒等式，不是本仓库关于算子谱或零点对关联的解析证明。不要修改、覆盖或把新的研究状态误写进它。

## 来源与证据限制

本次归档根据用户在聊天中贴出的 Gemini 文本、GPT 交叉核查以及公开 GitHub 仓库内容整理。由于部分聊天粘贴的公式在渲染中缺失，**history 文件是经过明确标识的摘要，不能冒充 Gemini 原始全文**。将来取得 LaTeX 或原始 Markdown 后，应以新文件保留原稿，记录 SHA/版本与差异。