# AI・Grounding・RAG・Agentic AI向け Search Engine / Web Search API 評価レポート

## 方法論に関する注記

本資料は **実験ベンチマークを用いていません**。  
すべてのスコアは、以下に基づいて評価しています。

- ベンダーの公式資料
- 公式技術文書 / 公式ドキュメント
- pricing pages
- lifecycle / policy pages
- および、一部のケースでは根拠が明確なパートナー統合資料

**1,000 request あたりの価格**は、別立ての比較用ベースラインとして扱い、以下の 1–5 点評価表には **含めていません**。

## 最終 1–5 点評価表

| Engine | Coverage | Freshness | JP / Localization | AI / Grounding / RAG | Operational | 合計 / 25 |
|---|---:|---:|---:|---:|---:|---:|
| Brave Search API | 5 | 5 | 5 | 5 | 4 | 24 |
| SearchAPI.io | 5 | 4 | 5 | 5 | 5 | 24 |
| SerpApi | 5 | 4 | 5 | 5 | 4 | 23 |
| Serper | 4 | 4 | 4 | 5 | 4 | 21 |
| Grounding with Bing Search | 4 | 5 | 4 | 5 | 2 | 20 |
| Autom | 5 | 4 | 4 | 2 | 4 | 19 |
| Piloterr | 5 | 3 | 4 | 3 | 3 | 18 |
| Google Custom Search JSON API | 2 | 2 | 4 | 3 | 1 | 12 |

## 評価基準

### 1. Coverage
文書化されている検索対象範囲の広さ、および search surfaces / endpoints の数を評価する。

### 2. Freshness
real-time、up-to-date、news endpoint、freshness/date filtering に関する公式な証拠の有無を評価する。

### 3. JP / Localization
`gl`、`hl`、`lr`、`search_lang`、`ui_lang`、`market`、`set_lang` などのパラメータに基づき、日本語対応力と localization を評価する。

### 4. AI / Grounding / RAG
**導入済みのプロジェクト / framework / IDE / agent platform** があり、かつ **名称が明確に示されている** 場合を高く評価する。根拠は公式資料または信頼できるパートナー資料に限定する。

### 5. Operational
SLA、throughput、legal/privacy/governance、および製品ライフサイクル上のリスクに基づいて運用信頼性を評価する。

---

# レポート用標準表

## 1) Brave Search API

| 評価項目の説明 | 根拠（evidence） | 出典 | 採点理由 |
|---|---|---|---|
| **Coverage（5/5）** | “over 30 billion pages”; “Web search”, “News search”, “Image search”, “Place search” | https://brave.com/search/api/ ; https://api-dashboard.search.brave.com/documentation/pricing | **大規模な独自インデックス** と複数の search surfaces を公開しているため。 |
| **Freshness（5/5）** | “real-time search data”; “100 million page updates every day”; “Last 24 Hours”, “Custom Date Range” | https://api-dashboard.search.brave.com/documentation/pricing ; https://api-dashboard.search.brave.com/app/documentation/web-search/get-started ; https://brave.com/search/api/ | **リアルタイム性**、**継続的なインデックス更新**、**freshness filtering** のすべてに関する証拠があるため。 |
| **JP / Localization（5/5）** | “Country”; “Search Language”; “UI Language”; `country`, `search_lang`, `ui_lang` | https://api-dashboard.search.brave.com/app/documentation/web-search/get-started ; https://api-dashboard.search.brave.com/api-reference/news/news_search/post ; https://api-dashboard.search.brave.com/api-reference/web/place_search | **国 / コンテンツ言語 / UI 言語** の各制御が揃っており、日本語クエリに適しているため。 |
| **AI / Grounding / RAG（5/5）** | “optimized for grounding LLM responses”; “Dify”, “Flowise”, “LangChain”, “Quivr”, “Windsurf”, “Zed” | https://api-dashboard.search.brave.com/documentation/services/llm-context ; https://brave.com/search/api/tools/ | **LLM Context API** があり、**統合済みプロジェクト / framework が公開されている** ため。 |
| **Operational（4/5）** | “Capacity 50 requests per second”; “Full-funnel Zero Data Retention” | https://api-dashboard.search.brave.com/documentation/pricing | 運用能力と privacy 面の根拠は強いが、**SearchAPI.io のような 99.9% SLA の明示** は確認できなかったため。 |

## 2) SearchAPI.io

| 評価項目の説明 | 根拠（evidence） | 出典 | 採点理由 |
|---|---|---|---|
| **Coverage（5/5）** | “Google SERP API”, “Google Shopping API”, “Google News API”, “Google Scholar API”, “Bing Search API” | https://www.searchapi.io/pricing | 複数の vertical と複数の engine を含む、広い API カタログを持つため。 |
| **Freshness（4/5）** | “real-time search engine results pages”; “real-time data in mere seconds” | https://www.searchapi.io/ ; https://www.searchapi.io/pricing | **real-time** の証拠は明確だが、freshness controls の文書化は Brave ほど詳細ではないため。 |
| **JP / Localization（5/5）** | “to filter documents written in Japanese, the value should be set to `lang_jp`”; “cr parameter restricts...” | https://www.searchapi.io/docs/google | 日本語に関する **明示的な証拠** が最も強いため。 |
| **AI / Grounding / RAG（5/5）** | “Dify, Flowise, LangChain, and Haystack” | https://www.searchapi.io/ | AI 統合先が **公式サイトで明示的に列挙** されているため。 |
| **Operational（5/5）** | “99.9% SLA”; “Legal Protection Guarantee”; “Dedicated Throughput” | https://www.searchapi.io/pricing | SLA、legal、throughput に関する運用根拠が最も強いため。 |

## 3) SerpApi

| 評価項目の説明 | 根拠（evidence） | 出典 | 採点理由 |
|---|---|---|---|
| **Coverage（5/5）** | “Google News API”, “Google Scholar API”, “Bing Search API”; “Maps, Local, Stories, Shopping... Knowledge Graph” | https://serpapi.com/pricing ; https://serpapi.com/ | 複数 engine と多様な SERP 種別をカバーしているため。 |
| **Freshness（4/5）** | “Each API request runs immediately”; “Real Time and Real Results” | https://serpapi.com/ | **live retrieval** の根拠は強いが、freshness filter の文書化は Brave / Bing ほど強くないため。 |
| **JP / Localization（5/5）** | `gl=us&hl=en`; “lang_{two-letter language code}” | https://serpapi.com/search-api | 国、UI 言語、ドキュメント言語に関するパラメータが揃っているため。 |
| **AI / Grounding / RAG（5/5）** | “Claude Desktop, VS Code, Cursor”; “open-source Model Context Protocol (MCP) server” | https://serpapi.com/integrations/mcp ; https://serpapi.com/blog/introducing-serpapis-mcp-server/ | **公式 MCP server** があり、AI クライアント統合先が明示されているため。 |
| **Operational（4/5）** | “U.S. Legal Shield”; “1,000 searches per month”; “200 throughput per hour” | https://serpapi.com/pricing ; https://serpapi.com/search-api | legal と throughput の根拠はあるが、SLA の公開の仕方は SearchAPI.io ほど明確ではないため。 |

## 4) Serper

| 評価項目の説明 | 根拠（evidence） | 出典 | 採点理由 |
|---|---|---|---|
| **Coverage（4/5）** | “Search”, “Images”, “News”, “Maps”, “Places”, “Videos”, “Shopping”, “Scholar”, “Patents”, “Autocomplete” | https://serper.dev/ | Google 系では広いが、SearchAPI.io や SerpApi ほど多 engine ではないため。 |
| **Freshness（4/5）** | “Real-time results”; “we directly query Google”; “We do not cache anything” | https://serper.dev/ | **real-time** および **no cache** の証拠があるため。 |
| **JP / Localization（4/5）** | “Customize query location” | https://serper.dev/ | location 調整はあるが、`lang_jp` のような日本語向け明示的証拠は弱いため。 |
| **AI / Grounding / RAG（5/5）** | “Haystack Integration”, “Jan AI Integration”, “CrewAI Integration”, “LangChain Integration”; “Google search API integration” | https://serper.dev/ ; https://docs.crewai.com/en/tools/search-research/overview ; https://docs.langchain.com/oss/python/integrations/providers/google_serper | **名称付きの公開統合** が複数確認できるため。 |
| **Operational（4/5）** | “300 queries per second”; “1 to 2 seconds” | https://serper.dev/ | throughput と速度の根拠はあるが、SLA / legal の公開情報はより限定的なため。 |

## 5) Grounding with Bing Search

| 評価項目の説明 | 根拠（evidence） | 出典 | 採点理由 |
|---|---|---|---|
| **Coverage（4/5）** | “billions of publicly available web pages” | https://www.microsoft.com/en-us/bing/apis/grounding-pricing | 公開 Web を大規模にカバーするが、Foundry 向け専用 tool であり、広い search surfaces 群ではないため。 |
| **Freshness（5/5）** | “relevant and up-to-date information”; “real-time results” | https://www.microsoft.com/en-us/bing/apis/grounding-pricing | **up-to-date** と **real-time** に関する公式根拠が非常に明確なため。 |
| **JP / Localization（4/5）** | `market`; `set_lang`; `freshness` | https://learn.microsoft.com/en-us/python/api/azure-ai-agents/azure.ai.agents.models.binggroundingsearchconfiguration | 国 / market と language 制御はあるが、日本語明示の根拠は強くないため。 |
| **AI / Grounding / RAG（5/5）** | “resource or tool in Azure AI Foundry”; “Azure AI Agents” | https://www.microsoft.com/en-us/bing/apis/grounding-pricing ; https://learn.microsoft.com/en-us/azure/foundry-classic/agents/how-to/tools-classic/bing-grounding | Azure AI Agents / Foundry の **公式 grounding tool** であるため。 |
| **Operational（2/5）** | “Data Protection Addendum doesn't apply”; “outside the Azure compliance and Geo boundary” | https://learn.microsoft.com/en-us/azure/foundry/agents/how-to/tools/web-overview | 強力な機能を持つ一方、compliance / privacy 上の注意事項が非常に明確であるため減点。 |

## 6) Autom

| 評価項目の説明 | 根拠（evidence） | 出典 | 採点理由 |
|---|---|---|---|
| **Coverage（5/5）** | “Bing Search GET”, “Brave Search GET”, “Google News GET”, “Google Search GET”, “Google Shopping GET”, “Google Videos GET” | https://docs.autom.dev/api-reference/bing/search | 複数 engine と複数 vertical を一つの API でカバーしているため。 |
| **Freshness（4/5）** | “Accurate, up-to-date search results” | https://www.autom.dev/ | up-to-date に関する公式 claim が確認できるため。 |
| **JP / Localization（4/5）** | `cc`: “en-US” | https://docs.autom.dev/api-reference/bing/search | market / country 制御の根拠はあるが、日本語向け明示根拠は弱いため。 |
| **AI / Grounding / RAG（2/5）** | “Model Context Protocol” | https://docs.autom.dev/api-reference/bing/search | MCP 対応の兆候はあるが、**名称付きの AI 統合プロジェクト** は確認できなかったため。 |
| **Operational（4/5）** | “99.9% uptime”; “thousands of requests per second” | https://www.autom.dev/ | uptime と throughput に関する公開根拠があるため。 |

## 7) Piloterr

| 評価項目の説明 | 根拠（evidence） | 出典 | 採点理由 |
|---|---|---|---|
| **Coverage（5/5）** | “Bing Search GET”, “Brave Search GET”, “Google News GET”, “Google Search GET”, “Google Videos GET”, “Website Crawler GET” | https://docs.piloterr.com/google-search-autocomplete ; https://docs.piloterr.com/brave-search | search engine 系と scraping / web tools 系の両方を含む、幅広い endpoint 群を持つため。 |
| **Freshness（3/5）** | “Retrieve real-time Google Search autocomplete suggestions”; “~2s Avg. response” | https://docs.piloterr.com/google-search-autocomplete ; https://docs.piloterr.com/ | 一部 endpoint に real-time の根拠はあるが、全体的な freshness の根拠は弱め。 |
| **JP / Localization（4/5）** | “support for language and country localization”; `gl`; `hl` | https://docs.piloterr.com/google-search-autocomplete | country と interface language の制御が確認できるため。 |
| **AI / Grounding / RAG（3/5）** | “connecting Piloterr to LangChain”; “OpenAI Agents SDK”; “Piloterr MCP server” | https://composio.dev/toolkits/piloterr/framework/langchain ; https://composio.dev/toolkits/piloterr/framework/open-ai-agents-sdk | 実際の統合事例はあるが、**最も強い証拠が Composio 由来であり first-party ではない** ため。 |
| **Operational（3/5）** | “1 credit = standard API request”; “25 requests per second” | https://www.piloterr.com/pricing | pricing と rate-limit の根拠はあるが、SLA の公開情報は弱い。 |

## 8) Google Custom Search JSON API

| 評価項目の説明 | 根拠（evidence） | 出典 | 採点理由 |
|---|---|---|---|
| **Coverage（2/5）** | “web search or image search”; “Programmable Search Engine” | https://developers.google.com/custom-search/v1/overview | full-web / multi-surface search APIs と比べると範囲が狭いため。 |
| **Freshness（2/5）** | この資料群では “real-time” や freshness controls に関する強い公式根拠は確認できない | https://developers.google.com/custom-search/v1/overview ; https://developers.google.com/custom-search/v1/reference/rest/v1/cse/list | freshness に関する強い証拠が不足しているため低評価。 |
| **JP / Localization（4/5）** | “The `gl` parameter boosts...” ; “You can use the `hl` request parameter...” ; “the `lr` parameter” | https://developers.google.com/custom-search/v1/reference/rest/v1/cse/list ; https://developers.google.com/custom-search/docs/json_api_reference ; https://developers.google.com/resources/api-libraries/documentation/customsearch/v1/java/latest/com/google/api/services/customsearch/Customsearch.Cse.List.html | country / UI / content-language 制御は揃っているが、製品のライフサイクル面に制約があるため。 |
| **AI / Grounding / RAG（3/5）** | “Gemini can query an external API endpoint”; “ground Gemini responses using results from Google's search engine” | https://docs.cloud.google.com/vertex-ai/generative-ai/docs/grounding/grounding-with-your-search-api ; https://docs.cloud.google.com/vertex-ai/generative-ai/docs/grounding/grounding-with-google-search | Gemini との **間接的な統合経路** はあるが、**CSE を名指しした built-in integration ではない** ため。 |
| **Operational（1/5）** | “closed to new customers”; “until January 1, 2027” | https://developers.google.com/custom-search/v1/overview | 新規プロジェクトにとって製品ライフサイクル上のリスクが非常に高いため。 |

---

## レポート挿入用の短い結論

**文書化された証拠の強さ** と **導入準備性** のみを見ると、**Brave Search API** と **SearchAPI.io** が **24/25** で最上位、次いで **SerpApi** が **23/25** となる。

ただし、別途整理した **1,000 request あたり価格** のベースラインを合わせて見ると、**Serper** は価格面で大きな優位があり、しかも資料上の評価も十分に高いことから、非常に有力な候補である。

## 1,000 request あたり価格ベースライン（別立て比較）

| 候補 | 1,000 request あたりの換算価格 | 注記 |
|---|---:|---|
| Serper | $0.30 / 1,000 query から | 公式サイト上の開始価格 |
| Autom | 約 $1 / 1,000 request | 公開 entry plan から換算 |
| Piloterr | 約 €2.50 / 1,000 request | credit-based plan から換算 |
| SearchAPI.io | $4 / 1,000 search | 公開 pricing |
| Google Custom Search JSON API | $5 / 1,000 query | 既存顧客のみ |
| Grounding with Bing Search | $14 / 1,000 transaction | Microsoft 公式 pricing |
| SerpApi | $25 / 1,000 search | 公開 pricing |

---

## 最終所見

- **文書化・AI integration・localization を重視** する場合、上位候補は **Brave Search API**, **SearchAPI.io**, **SerpApi** である。
- **低コスト** を重視しつつ、十分な資料根拠も求める場合は、**Serper** が有力である。
- **Google Custom Search JSON API** と **Grounding with Bing Search** は重要な比較対象ではあるが、それぞれ次の大きな制約を持つ。
  - Google CSE: 新規プロジェクトには不利な lifecycle
  - Bing Grounding: compliance / governance 上の注意点が明確
