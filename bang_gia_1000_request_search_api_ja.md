# 1,000 request あたり価格換算表

## 目的
本資料は、調査対象となった search engine / search API 間で **コスト比較の基準** として用いるため、**1,000 request / query / transaction あたりの換算価格** を整理したものである。

## 換算の原則
- 可能な限り、各ベンダーの **公式 pricing page** または **overview page** に掲載された価格を使用する。
- **credit-based** モデルについては、ベンダーが `1 credit = standard API request` のように明示している場合、その情報に従って換算する。
- **複数 tier** がある場合は、以下を優先して記載する。
  - **entry / 一般的 / 比較しやすいプラン**
  - 必要に応じて、**大規模利用時の低価格 tier**
- 本表は **粗いコスト比較** のためのものであり、以下の差異は反映していない。
  - search quality
  - freshness
  - localization
  - AI / grounding features
  - SLA / legal / governance

---

## 価格換算表

| 候補 | 1,000 request あたり換算価格 | 換算根拠 | 公式ソース |
|---|---:|---|---|
| **Brave Search API** | **$5 / 1,000 requests** | Pricing page に “$5.00 per 1,000 requests” と明記 | https://api-dashboard.search.brave.com/documentation/pricing |
| **Serper** | **$1.00 / 1,000 query** (Starter) | Pricing page に “50k credits ($1.00/1k)” と記載 | https://serper.dev/ |
| **Serper（大規模利用）** | **$0.30 / 1,000 query** | Pricing page に “12.5M credits ($0.30/1k)” と記載 | https://serper.dev/ |
| **SearchAPI.io** | **$4 / 1,000 searches** | Pricing page に “$4 per 1,000 searches” と記載 | https://www.searchapi.io/pricing |
| **SerpApi** | **$25 / 1,000 searches** | Pricing page に “$25 / month” と “1,000 searches per month” と記載 | https://serpapi.com/pricing |
| **Autom** | **$1 / 1,000 request** | Pricing page に “$50” と “50k credits” と記載。1 credit ≈ 1 standard request とみなして換算 | https://www.autom.dev/pricing |
| **Piloterr (USD)** | **$2.72 / 1,000 request** | Pricing page に “$49/mo”, “18,000 credits”, “1 credit = standard API request” と記載 ⇒ 49 / 18 ≈ 2.72 | https://www.piloterr.com/pricing |
| **Piloterr (EUR)** | **€2.50 / 1,000 request** | Pricing page に “45€/mo”, “18,000 credits”, “1 credit = standard API request” と記載 ⇒ 45 / 18 = 2.50 | https://www.piloterr.com/pricing |
| **Google Custom Search JSON API** | **$5 / 1,000 queries** | Overview page に “Additional requests cost $5 per 1000 queries” と記載 | https://developers.google.com/custom-search/v1/overview |
| **Grounding with Bing Search** | **$14 / 1,000 transactions** | Pricing page に “$14 per 1,000 transactions” と記載 | https://www.microsoft.com/en-us/bing/apis/grounding-pricing |

---

## 公式ソースからの主要価格引用

### Brave Search API
- “**$5.00 per 1,000 requests**”
- URL: https://api-dashboard.search.brave.com/documentation/pricing

### Serper
- “**50k credits ($1.00/1k)**”
- “**12.5M credits ($0.30/1k)**”
- URL: https://serper.dev/

### SearchAPI.io
- “**$4 per 1,000 searches**”
- URL: https://www.searchapi.io/pricing

### SerpApi
- “**$25 / month**”
- “**1,000 searches per month**”
- URL: https://serpapi.com/pricing

### Autom
- “**$50**”
- “**50k credits**”
- URL: https://www.autom.dev/pricing

### Piloterr
- “**$49/mo**”
- “**18,000 credits**”
- “**1 credit = standard API request**”
- “**45€/mo**”
- “**18,000 credits**”
- URL: https://www.piloterr.com/pricing

### Google Custom Search JSON API
- “**Additional requests cost $5 per 1000 queries**”
- URL: https://developers.google.com/custom-search/v1/overview

### Grounding with Bing Search
- “**$14 per 1,000 transactions**”
- URL: https://www.microsoft.com/en-us/bing/apis/grounding-pricing

---

## 安い順 → 高い順（比較用の目安）

> 注意: 以下の順序は **1,000 request あたりの粗い換算価格** のみで並べている。  
> search quality や AI 機能は反映していない。

1. **Serper（大規模利用）** — $0.30 / 1,000
2. **Serper（Starter）** — $1.00 / 1,000
3. **Autom** — 約 $1.00 / 1,000
4. **Piloterr (EUR)** — €2.50 / 1,000
5. **Piloterr (USD)** — $2.72 / 1,000
6. **SearchAPI.io** — $4.00 / 1,000
7. **Brave Search API** — $5.00 / 1,000
8. **Google Custom Search JSON API** — $5.00 / 1,000
9. **Grounding with Bing Search** — $14.00 / 1,000
10. **SerpApi** — $25.00 / 1,000

---

## 重要な注記

### 1. Serper には複数の価格帯がある
Serper は単一価格ではない。  
entry レベルで公平に比較するなら、以下を用いることができる。

- **$1.00 / 1,000**（Starter）

大規模利用時の価格優位を見たい場合は、以下を用いることができる。

- **$0.30 / 1,000**（Ultimate）

### 2. Autom は credit-based モデルである
Autom の pricing page には以下が記載されている。

- “$50”
- “50k credits”

本表では、実務上の近似として以下を前提に換算している。

- **1 credit ≈ 1 standard request**

今後、特定 endpoint に異なる credit 消費規則が確認された場合は、その endpoint ごとに再計算が必要である。

### 3. Piloterr は USD と EUR の両方を表示している
Piloterr は以下の 2 通貨で価格を表示している。

- **USD**
- **EUR**

そのため、混同を避けるために本表では両方の換算価格を残している。

### 4. Google Custom Search JSON API
Google は以下を明確に記載している。

- 本 API は **新規顧客向けではない**
- 現在の pricing は **existing customers** にのみ適用される
- サービスは **2027/01/01** に終了予定である

したがって、換算価格が **$5 / 1,000** であっても、**新規プロジェクト向けの有力候補とは言い難い**。

### 5. Grounding with Bing Search
**$14 / 1,000 transactions** という価格は、Azure AI / Bing Grounding の grounding サービスに対するものであり、**旧来の Bing Web Search API** の価格ではない。

---

## 短い結論

**1,000 request あたりの価格** だけを見ると:

- **大規模利用で最も安い** のは **Serper**
- **entry レベルで安い** のは **Serper** と **Autom**
- **中価格帯** は **Piloterr** と **SearchAPI.io**
- **かなり高価** なのは **Grounding with Bing Search** と **SerpApi**

ただし、AI / Grounding / RAG / Agentic AI 向けに選定する場合は、価格だけでなく以下も合わせて評価する必要がある。

- 日本語 localization
- freshness
- AI integration
- SLA / compliance
- production 適合性
