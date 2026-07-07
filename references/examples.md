# Worked Examples

Two examples showing calibrated depth and tone. Both are condensed from real runs. Use them for taste — what [fatal] means, what a real kill criteria looks like, what low-stakes restraint looks like — not as templates to fill.

## Example 1: Low stakes — restraint

**User:** "反驳我：我觉得我们的周报应该改成双周报。"

**Response (entire):**

> 最锋利的一条：你要省的是写周报的 30 分钟，但双周报意味着问题的最大潜伏期从 7 天变成 14 天——上次那种"第 10 天才发现方向跑偏"的事故，成本是几个 30 分钟？
>
> 三个问题：谁在读周报，他们用它做什么决定？改成双周之后，那个决定的信息从哪来？还是说其实没人读——那该讨论的是砍掉而不是减半？

Note what did NOT happen: no template, no ledger, no steelman section, no verdict vocabulary. One objection with a number in it, three questions that change the decision. Done.

## Example 2: High stakes — full depth (condensed)

**User:** "帮我泼泼冷水：我打算辞职做一个 AI 简历优化 SaaS，面向中国求职者，收费 99 元/月。我有 10 万积蓄，计划 6 个月做出第一版。做过 3 年后端，没做过产品和营销。"

**Response (condensed — real run browsed competitors first and cited sources):**

> **Cold Read**
> 你要拿"辞职 + 10 万积蓄"赌一个 99 元/月的订阅产品，不可逆的部分是辞职，不是产品。最强版本的论证成立：求职是高焦虑场景、AI 确实改变了成本结构、你的技术足够——但这些对已经在场上的所有竞品同样成立。
>
> **Where It Breaks**
> - [fatal] 订阅制和求职需求在结构上互斥。求职期 1-3 个月，拿到 offer 当天流失，LTV ≈ 100-300 元（99 × 1-3 个月，量级估算），不是 12 × 99。商业模式假设了一个不存在的续费行为——这打断的是"用户会持续付费"这根梁。
> - [fatal] 付费意愿被免费替代品击穿：DeepSeek/Kimi 免费能改到 80 分，垂直竞品要么免费要么 4.9 元起（browse 验证，来源见文末）。你要回答的不是"我的产品好不好"，而是"用户为什么不用免费的"。
> - [serious] 6 个月花在最容易的 10% 上。套壳产品两周能上线收费版；这类产品死于分销，而分销是你明说没做过的事。"6 个月做第一版"翻译过来是：用积蓄购买 6 个月回避营销的时间。
> - [friction] 跑道测算：10 万 ÷（生活费 + 社保自缴 5k-10k/月，未验证你的实际开销）≈ 8-14 个月，前 6 个月零验证。
>
> **The Load-Bearing Assumption**
> "独立开发者做 C 端工具 SaaS 大多死于无人付费和分销"这个基准率不适用于我，因为 ___。目前你能填的只有"我技术好、我肯投入"——那正是分母们的共同特征。纯信念。
>
> **Smallest Test**
> 不辞职，4 个周末：落地页 + 真实付款按钮（先测 49-99 元一次性定价，人工兜底交付），小红书/求职群发内容引流。**Kill criteria（提前写死，不许事后挪）：4 周内真实付费 < 5 人，或获客只能靠熟人——订阅制形态就地终止，不辞职，不追加。**
>
> **Verdict**
> Test first，且否决"辞职"部分。辞职是花 10 万验证的信息，小测试花几百块买同一个信息，价差 100 倍。你说你有几成把握？如果心里是七八成，证据目前支持大约两成——这个差距就是要测的东西。决定权在你。
>
> *Pruned: 3 objections dropped（API 成本上涨、个保法合规、简历数据冷启动——用户一句话就能挡回去的都删了）。*

Note the tone: every [fatal] names the assumption it breaks; every number is an order-of-magnitude estimate labeled as such or browsed; the kill criteria is specific enough that four weeks later there is no room to argue about whether it fired.
