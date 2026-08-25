<h1 align="center">Grefer · 王贵福</h1>

<p align="center">
  <em>OTC options trader who writes his own pricing and hedging tools.</em><br>
  <sub>场外期权交易员 · 自己写定价与对冲工具</sub>
</p>

<p align="center">
  <a href="https://blog.grefer.cn"><img src="https://img.shields.io/badge/Blog-blog.grefer.cn-0076a8?style=flat-square&logo=hexo&logoColor=white" alt="Blog" /></a>
  <a href="mailto:melonsneverdie@gmail.com"><img src="https://img.shields.io/badge/Email-melonsneverdie%40gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white" alt="Email" /></a>
  <img src="https://img.shields.io/badge/FRM-Charterholder-2b6cb0?style=flat-square" alt="FRM" />
  <img src="https://img.shields.io/badge/CFA-Level%20I%20Pass-2b6cb0?style=flat-square" alt="CFA" />
  <img src="https://komarev.com/ghpvc/?username=Grefer&color=0076a8&style=flat-square&label=Profile%20Views" alt="Profile Views" />
</p>

---

## 🧭 About

I price and hedge OTC options for a living, and I write the tools I need. Eight years inside
Chinese derivatives — interbank quoting systems, IRS broking, and now delta-hedging an
options book — so the code here comes from the desk, not from a textbook. The two projects
below are the ones I actually maintain.

> 近 8 年金融衍生品从业经历，覆盖利率、外汇、商品与可转债四类资产。现任场外期权交易员，
> 负责报价与 Delta 动态对冲；此前从事银行间报价引擎系统的产品设计。
> 这里的代码基本都来自交易台上真实遇到的问题——先有问题，再有工具。

---

## 📦 Projects

### [DeltaLab](https://github.com/Grefer/DeltaLab) · 期权 Delta 动态对冲回测引擎

<p>
  <a href="https://github.com/Grefer/DeltaLab"><img src="https://img.shields.io/github/stars/Grefer/DeltaLab?style=flat-square&label=stars&color=0076a8" alt="stars" /></a>
  <img src="https://img.shields.io/badge/Python-3.10--3.13-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python" />
</p>

**要回答的问题：对冲频率该怎么选？**

卖方每天都要决定「什么时候调仓」。调得勤，跟踪误差小但成本高；调得松，成本省下来但敞口
放大。这个权衡没有解析解，只能在真实行情上量。

- 覆盖香草、累计 / 累沽、亚式、气囊、雪球等主流场外结构，奇异结构走蒙特卡洛路径模拟
- 数据源（Wind / CSV）× 调仓规则（定时、价格区间、日波动率倍数）自由组合
- **策略优选**：以「每日收盘」为固定基准，在近周至近年五档周期上严格连续回放，按增量收益 /
  增量信噪比排名——并在各周期结论不一致时**主动告警**，而不是只把最优解报给你

### [CBLens](https://github.com/Grefer/CBLens) · A 股可转债定价与研究工作台

<p>
  <a href="https://github.com/Grefer/CBLens"><img src="https://img.shields.io/github/stars/Grefer/CBLens?style=flat-square&label=stars&color=0076a8" alt="stars" /></a>
  <img src="https://img.shields.io/badge/Python-3.10%2B-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python" />
</p>

**要回答的问题：模型说这只转债便宜，能信吗？**

- 定价引擎用 Crank–Nicolson 有限差分格式求解 PDE，完整处理赎回 / 回售 / 下修条款、分层票息
  与应计利息、含信用利差贴现的宽限期，输出 Δ / Γ / ν / Θ 与价值分解
- 全市场并发批量定价与筛选；从公告中抽取条款变更事件回溯至条款库，保证估值口径与真实条款一致
- **横截面检验的结论是否定的**：机会分的 Rank-IC ≈ 0（2025 年 −0.26），所以它被降级为复核
  标记，不参与排序、不当买入信号。但同一个模型的**聚合中位偏差反而是有效的大类择时信号**
  （与中证转债指数下季收益 Spearman ≈ −0.52）

  [研究笔记](https://github.com/Grefer/CBLens/blob/main/docs/research/2026-06-score-ic-and-valuation-timing.md)
  里写死了样本外预注册的复评时点与成功标准，不得事后修改；也记着一次「基于单一牛市证据改默认、
  四年复测后回退」的教训。

---

## ✍️ Writing

研究笔记发在 [blog.grefer.cn](https://blog.grefer.cn)，偏实证与工程细节。

---

## 🛠 Stack

<p>
  <img src="https://img.shields.io/badge/-Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/-NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy" />
  <img src="https://img.shields.io/badge/-SciPy-8CAAE6?style=for-the-badge&logo=scipy&logoColor=white" alt="SciPy" />
  <img src="https://img.shields.io/badge/-pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="pandas" />
  <img src="https://img.shields.io/badge/-MATLAB-0076a8?style=for-the-badge&logo=mathworks&logoColor=white" alt="MATLAB" />
  <img src="https://img.shields.io/badge/-Wind%20API-c8102e?style=for-the-badge" alt="Wind API" />
</p>

数值方法：蒙特卡洛路径模拟、有限差分 PDE 求解、希腊字母与价值分解、隐含波动率反解。

---

## 📊 Stats

<p align="center">
  <img src="https://stats.grefer.cn/api?username=Grefer&show_icons=true&theme=tokyonight&hide_border=true&count_private=true&card_width=445" alt="Grefer GitHub Stats" width="420" height="165" />
  <img src="https://stats.grefer.cn/api/top-langs/?username=Grefer&layout=compact&theme=tokyonight&hide_border=true&langs_count=8&card_width=445" alt="Grefer Top Languages" width="420" height="165" />
</p>

<p align="center">
  <img src="https://grefer-activity-graph.vercel.app/graph?username=Grefer&theme=tokyo-night&hide_border=true&area=true" alt="Grefer Activity Graph" width="806" />
</p>

<p align="center">
  <sub>"Commit small, commit often." — 一次一个仓库，从 2019 年到现在。</sub>
</p>
