# Báo cáo đánh giá search engine / web search API cho AI, Grounding, RAG và Agentic AI

## Ghi chú phương pháp

Tài liệu này **không dùng thực nghiệm benchmark**.  
Toàn bộ điểm số được chấm dựa trên:

- tài liệu chính thức của nhà cung cấp,
- tài liệu kỹ thuật / docs chính thức,
- pricing pages,
- lifecycle / policy pages,
- và trong một số trường hợp là tài liệu tích hợp từ đối tác có cơ sở rõ ràng.

**Giá / 1.000 request** được dùng như baseline đối chiếu riêng và **không gộp** vào bảng chấm điểm 1–5 dưới đây.

## Bảng chấm điểm 1–5 cuối cùng

| Engine | Coverage | Freshness | JP / Localization | AI / Grounding / RAG | Operational | Tổng / 25 |
|---|---:|---:|---:|---:|---:|---:|
| Brave Search API | 5 | 5 | 5 | 5 | 4 | 24 |
| SearchAPI.io | 5 | 4 | 5 | 5 | 5 | 24 |
| SerpApi | 5 | 4 | 5 | 5 | 4 | 23 |
| Serper | 4 | 4 | 4 | 5 | 4 | 21 |
| Grounding with Bing Search | 4 | 5 | 4 | 5 | 2 | 20 |
| Autom | 5 | 4 | 4 | 2 | 4 | 19 |
| Piloterr | 5 | 3 | 4 | 3 | 3 | 18 |
| Google Custom Search JSON API | 2 | 2 | 4 | 3 | 1 | 12 |

## Tiêu chí chấm điểm

### 1. Coverage
Đánh giá độ rộng phạm vi dữ liệu và số lượng search surfaces / endpoints được tài liệu hóa.

### 2. Freshness
Đánh giá mức độ có bằng chứng official về real-time, up-to-date, news endpoint, freshness/date filtering.

### 3. JP / Localization
Đánh giá khả năng hỗ trợ tiếng Nhật và localization dựa trên các tham số như `gl`, `hl`, `lr`, `search_lang`, `ui_lang`, `market`, `set_lang`.

### 4. AI / Grounding / RAG
Ưu tiên rất cao khi có **dự án / framework / IDE / agent platform** đã tích hợp và **được gọi tên rõ** trong tài liệu chính thức hoặc tài liệu đối tác mạnh.

### 5. Operational
Đánh giá độ tin cậy vận hành dựa trên SLA, throughput, legal/privacy/governance, và rủi ro lifecycle sản phẩm.

---

# Bảng chuẩn văn phong báo cáo khóa học

## 1) Brave Search API

| Mô tả tiêu chí | Bằng chứng | Nguồn | Lý do cho điểm |
|---|---|---|---|
| **Độ bao phủ (5/5)** | “over 30 billion pages”; “Web search”, “News search”, “Image search”, “Place search” | https://brave.com/search/api/ ; https://api-dashboard.search.brave.com/documentation/pricing | Có **chỉ mục riêng quy mô lớn** và nhiều search surfaces công khai. |
| **Cập nhật liên tục (5/5)** | “real-time search data”; “100 million page updates every day”; “Last 24 Hours”, “Custom Date Range” | https://api-dashboard.search.brave.com/documentation/pricing ; https://api-dashboard.search.brave.com/app/documentation/web-search/get-started ; https://brave.com/search/api/ | Có cả **tuyên bố real-time**, **cập nhật chỉ mục liên tục**, và **freshness filtering**. |
| **Hỗ trợ tiếng Nhật / localization (5/5)** | “Country”; “Search Language”; “UI Language”; `country`, `search_lang`, `ui_lang` | https://api-dashboard.search.brave.com/app/documentation/web-search/get-started ; https://api-dashboard.search.brave.com/api-reference/news/news_search/post ; https://api-dashboard.search.brave.com/api-reference/web/place_search | Có đủ **quốc gia + ngôn ngữ nội dung + ngôn ngữ giao diện**, nên phù hợp cho truy vấn tiếng Nhật. |
| **Mức sẵn sàng cho AI / Grounding / RAG (5/5)** | “optimized for grounding LLM responses”; “Dify”, “Flowise”, “LangChain”, “Quivr”, “Windsurf”, “Zed” | https://api-dashboard.search.brave.com/documentation/services/llm-context ; https://brave.com/search/api/tools/ | Có **LLM Context API** và danh sách **dự án / framework tích hợp công khai** rất mạnh. |
| **Độ tin cậy vận hành (4/5)** | “Capacity 50 requests per second”; “Full-funnel Zero Data Retention” | https://api-dashboard.search.brave.com/documentation/pricing | Có năng lực vận hành và privacy tốt, nhưng **không thấy SLA public rõ như 99.9% SLA**. |

## 2) SearchAPI.io

| Mô tả tiêu chí | Bằng chứng | Nguồn | Lý do cho điểm |
|---|---|---|---|
| **Độ bao phủ (5/5)** | “Google SERP API”, “Google Shopping API”, “Google News API”, “Google Scholar API”, “Bing Search API” | https://www.searchapi.io/pricing | Có danh mục API rộng, gồm nhiều vertical và nhiều engine. |
| **Cập nhật liên tục (4/5)** | “real-time search engine results pages”; “real-time data in mere seconds” | https://www.searchapi.io/ ; https://www.searchapi.io/pricing | Có bằng chứng rõ về **real-time**, nhưng phần freshness controls không được tài liệu hóa sâu bằng Brave. |
| **Hỗ trợ tiếng Nhật / localization (5/5)** | “to filter documents written in Japanese, the value should be set to `lang_jp`”; “cr parameter restricts...” | https://www.searchapi.io/docs/google | Có bằng chứng **JP explicit** tốt nhất trong nhóm. |
| **Mức sẵn sàng cho AI / Grounding / RAG (5/5)** | “Dify, Flowise, LangChain, and Haystack” | https://www.searchapi.io/ | Có các **tích hợp AI được gọi tên trực tiếp** trên site chính thức. |
| **Độ tin cậy vận hành (5/5)** | “99.9% SLA”; “Legal Protection Guarantee”; “Dedicated Throughput” | https://www.searchapi.io/pricing | Bộ bằng chứng vận hành mạnh nhất trong nhóm: SLA, legal, throughput. |

## 3) SerpApi

| Mô tả tiêu chí | Bằng chứng | Nguồn | Lý do cho điểm |
|---|---|---|---|
| **Độ bao phủ (5/5)** | “Google News API”, “Google Scholar API”, “Bing Search API”; “Maps, Local, Stories, Shopping... Knowledge Graph” | https://serpapi.com/pricing ; https://serpapi.com/ | Coverage rất rộng, gồm nhiều engine và nhiều loại SERP. |
| **Cập nhật liên tục (4/5)** | “Each API request runs immediately”; “Real Time and Real Results” | https://serpapi.com/ | Có bằng chứng mạnh về **live retrieval**, nhưng docs freshness filter không nổi bật bằng Brave/Bing. |
| **Hỗ trợ tiếng Nhật / localization (5/5)** | `gl=us&hl=en`; “lang_{two-letter language code}” | https://serpapi.com/search-api | Có đủ tham số quốc gia, giao diện và ngôn ngữ tài liệu. |
| **Mức sẵn sàng cho AI / Grounding / RAG (5/5)** | “Claude Desktop, VS Code, Cursor”; “open-source Model Context Protocol (MCP) server” | https://serpapi.com/integrations/mcp ; https://serpapi.com/blog/introducing-serpapis-mcp-server/ | Có **MCP server chính thức** và tích hợp AI clients được gọi tên rõ. |
| **Độ tin cậy vận hành (4/5)** | “U.S. Legal Shield”; “1,000 searches per month”; “200 throughput per hour” | https://serpapi.com/pricing ; https://serpapi.com/search-api | Có legal và throughput public, nhưng cách công bố SLA không mạnh bằng SearchAPI.io. |

## 4) Serper

| Mô tả tiêu chí | Bằng chứng | Nguồn | Lý do cho điểm |
|---|---|---|---|
| **Độ bao phủ (4/5)** | “Search”, “Images”, “News”, “Maps”, “Places”, “Videos”, “Shopping”, “Scholar”, “Patents”, “Autocomplete” | https://serper.dev/ | Rộng trong hệ Google, nhưng không đa-engine như SearchAPI.io hay SerpApi. |
| **Cập nhật liên tục (4/5)** | “Real-time results”; “we directly query Google”; “We do not cache anything” | https://serper.dev/ | Có bằng chứng mạnh về **real-time** và **no cache**. |
| **Hỗ trợ tiếng Nhật / localization (4/5)** | “Customize query location” | https://serper.dev/ | Có localization theo vị trí, nhưng không có bằng chứng JP explicit mạnh như `lang_jp`. |
| **Mức sẵn sàng cho AI / Grounding / RAG (5/5)** | “Haystack Integration”, “Jan AI Integration”, “CrewAI Integration”, “LangChain Integration”; “Google search API integration” | https://serper.dev/ ; https://docs.crewai.com/en/tools/search-research/overview ; https://docs.langchain.com/oss/python/integrations/providers/google_serper | Có **nhiều tích hợp công khai được gọi tên rõ**. |
| **Độ tin cậy vận hành (4/5)** | “300 queries per second”; “1 to 2 seconds” | https://serper.dev/ | Throughput và tốc độ tốt, nhưng thiếu SLA/legal public mạnh hơn. |

## 5) Grounding with Bing Search

| Mô tả tiêu chí | Bằng chứng | Nguồn | Lý do cho điểm |
|---|---|---|---|
| **Độ bao phủ (4/5)** | “billions of publicly available web pages” | https://www.microsoft.com/en-us/bing/apis/grounding-pricing | Có phạm vi web công khai lớn, nhưng là tool chuyên cho Foundry hơn là bộ search surfaces rộng. |
| **Cập nhật liên tục (5/5)** | “relevant and up-to-date information”; “real-time results” | https://www.microsoft.com/en-us/bing/apis/grounding-pricing | Có bằng chứng official rất rõ về **up-to-date** và **real-time**. |
| **Hỗ trợ tiếng Nhật / localization (4/5)** | `market`; `set_lang`; `freshness` | https://learn.microsoft.com/en-us/python/api/azure-ai-agents/azure.ai.agents.models.binggroundingsearchconfiguration | Có country/market và language control, nhưng không có bằng chứng JP explicit mạnh. |
| **Mức sẵn sàng cho AI / Grounding / RAG (5/5)** | “resource or tool in Azure AI Foundry”; “Azure AI Agents” | https://www.microsoft.com/en-us/bing/apis/grounding-pricing ; https://learn.microsoft.com/en-us/azure/foundry-classic/agents/how-to/tools-classic/bing-grounding | Đây là **tool grounding chính thức** trong hệ Azure AI Agents / Foundry. |
| **Độ tin cậy vận hành (2/5)** | “Data Protection Addendum doesn't apply”; “outside the Azure compliance and Geo boundary” | https://learn.microsoft.com/en-us/azure/foundry/agents/how-to/tools/web-overview | Tính năng mạnh, nhưng có caveat compliance/privacy rất rõ nên bị trừ điểm. |

## 6) Autom

| Mô tả tiêu chí | Bằng chứng | Nguồn | Lý do cho điểm |
|---|---|---|---|
| **Độ bao phủ (5/5)** | “Bing Search GET”, “Brave Search GET”, “Google News GET”, “Google Search GET”, “Google Shopping GET”, “Google Videos GET” | https://docs.autom.dev/api-reference/bing/search | Unified API phủ nhiều engine và nhiều vertical. |
| **Cập nhật liên tục (4/5)** | “Accurate, up-to-date search results” | https://www.autom.dev/ | Có claim official rõ về dữ liệu cập nhật. |
| **Hỗ trợ tiếng Nhật / localization (4/5)** | `cc`: “en-US” | https://docs.autom.dev/api-reference/bing/search | Có evidence về market/country control, nhưng chưa thấy JP explicit mạnh. |
| **Mức sẵn sàng cho AI / Grounding / RAG (2/5)** | “Model Context Protocol” | https://docs.autom.dev/api-reference/bing/search | Có dấu hiệu hỗ trợ MCP, nhưng **không thấy dự án AI tích hợp được gọi tên rõ** trong nguồn đã đọc. |
| **Độ tin cậy vận hành (4/5)** | “99.9% uptime”; “thousands of requests per second” | https://www.autom.dev/ | Có uptime và throughput public tốt. |

## 7) Piloterr

| Mô tả tiêu chí | Bằng chứng | Nguồn | Lý do cho điểm |
|---|---|---|---|
| **Độ bao phủ (5/5)** | “Bing Search GET”, “Brave Search GET”, “Google News GET”, “Google Search GET”, “Google Videos GET”, “Website Crawler GET” | https://docs.piloterr.com/google-search-autocomplete ; https://docs.piloterr.com/brave-search | Danh mục endpoint rất rộng, cả search engine lẫn scraping/web tools. |
| **Cập nhật liên tục (3/5)** | “Retrieve real-time Google Search autocomplete suggestions”; “~2s Avg. response” | https://docs.piloterr.com/google-search-autocomplete ; https://docs.piloterr.com/ | Có bằng chứng real-time cho một số endpoint, nhưng chưa thấy lớp freshness tổng thể mạnh. |
| **Hỗ trợ tiếng Nhật / localization (4/5)** | “support for language and country localization”; `gl`; `hl` | https://docs.piloterr.com/google-search-autocomplete | Có đủ country và interface language control. |
| **Mức sẵn sàng cho AI / Grounding / RAG (3/5)** | “connecting Piloterr to LangChain”; “OpenAI Agents SDK”; “Piloterr MCP server” | https://composio.dev/toolkits/piloterr/framework/langchain ; https://composio.dev/toolkits/piloterr/framework/open-ai-agents-sdk | Có tích hợp thực tế, nhưng bằng chứng mạnh nhất đến từ **đối tác Composio**, không phải first-party. |
| **Độ tin cậy vận hành (3/5)** | “1 credit = standard API request”; “25 requests per second” | https://www.piloterr.com/pricing | Có pricing và rate-limit rõ, nhưng bằng chứng SLA public còn yếu. |

## 8) Google Custom Search JSON API

| Mô tả tiêu chí | Bằng chứng | Nguồn | Lý do cho điểm |
|---|---|---|---|
| **Độ bao phủ (2/5)** | “web search or image search”; “Programmable Search Engine” | https://developers.google.com/custom-search/v1/overview | Phạm vi hẹp hơn các full-web / multi-surface search APIs. |
| **Cập nhật liên tục (2/5)** | Không thấy bằng chứng official mạnh về “real-time” hay freshness controls trong bộ nguồn đã đọc | https://developers.google.com/custom-search/v1/overview ; https://developers.google.com/custom-search/v1/reference/rest/v1/cse/list | Vì thiếu bằng chứng freshness mạnh, điểm giữ ở mức thấp. |
| **Hỗ trợ tiếng Nhật / localization (4/5)** | “The `gl` parameter boosts...” ; “You can use the `hl` request parameter...” ; “the `lr` parameter” | https://developers.google.com/custom-search/v1/reference/rest/v1/cse/list ; https://developers.google.com/custom-search/docs/json_api_reference ; https://developers.google.com/resources/api-libraries/documentation/customsearch/v1/java/latest/com/google/api/services/customsearch/Customsearch.Cse.List.html | Có đủ country/UI/content-language controls, nhưng sản phẩm đã vào giai đoạn thoái lui. |
| **Mức sẵn sàng cho AI / Grounding / RAG (3/5)** | “Gemini can query an external API endpoint”; “ground Gemini responses using results from Google's search engine” | https://docs.cloud.google.com/vertex-ai/generative-ai/docs/grounding/grounding-with-your-search-api ; https://docs.cloud.google.com/vertex-ai/generative-ai/docs/grounding/grounding-with-google-search | Có **đường tích hợp gián tiếp hợp lệ** với Gemini qua “your search API”, nhưng **không phải built-in integration gọi tên CSE**. |
| **Độ tin cậy vận hành (1/5)** | “closed to new customers”; “until January 1, 2027” | https://developers.google.com/custom-search/v1/overview | Rủi ro vòng đời sản phẩm rất cao cho dự án mới. |

---

## Kết luận ngắn để chèn vào báo cáo

Nếu chỉ xét theo **bằng chứng tài liệu hóa và mức sẵn sàng triển khai**, **Brave Search API** và **SearchAPI.io** đứng đầu với **24/25**, tiếp theo là **SerpApi** với **23/25**.

Tuy nhiên, nếu ghép thêm baseline **giá / 1.000 request**, thì **Serper** vẫn là ứng viên rất đáng chú ý vì chi phí thấp hơn rõ rệt nhưng điểm tài liệu hóa vẫn ở mức tốt.

## Baseline giá / 1.000 request (đối chiếu riêng)

| Ứng viên | Giá quy đổi / 1.000 request | Ghi chú |
|---|---:|---|
| Serper | từ $0.30 / 1.000 query | Giá bắt đầu theo site chính thức |
| Autom | khoảng $1 / 1.000 request | Quy đổi từ gói entry công bố |
| Piloterr | khoảng €2.50 / 1.000 request | Quy đổi từ credit-based plan |
| SearchAPI.io | $4 / 1.000 search | Pricing công khai |
| Google Custom Search JSON API | $5 / 1.000 query | Chỉ cho khách hiện hữu |
| Grounding with Bing Search | $14 / 1.000 transaction | Pricing chính thức của Microsoft |
| SerpApi | $25 / 1.000 search | Pricing công khai |

---

## Nhận định cuối cùng

- Nếu ưu tiên **mạnh về tài liệu hóa, AI integration và localization**, nhóm đầu là **Brave Search API**, **SearchAPI.io**, **SerpApi**.
- Nếu ưu tiên **chi phí thấp** nhưng vẫn có hồ sơ tài liệu hóa tốt, **Serper** là ứng viên nổi bật.
- **Google Custom Search JSON API** và **Grounding with Bing Search** nên xuất hiện như **đối chứng quan trọng**, nhưng đều có hạn chế lớn:
  - Google CSE: lifecycle bất lợi cho dự án mới.
  - Bing Grounding: caveat compliance / governance đáng chú ý.
