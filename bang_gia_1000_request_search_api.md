# Bảng giá quy đổi về 1.000 request

## Mục đích
Tài liệu này tổng hợp **giá quy đổi về 1.000 request / query / transaction** để dùng làm **mốc đối chiếu chi phí** giữa các search engine / search API đã khảo sát.

## Nguyên tắc quy đổi
- Ưu tiên dùng **giá niêm yết chính thức** trên pricing page hoặc overview page của nhà cung cấp.
- Với mô hình **credit-based**, quy đổi theo đúng thông tin official như `1 credit = standard API request` nếu nhà cung cấp công bố rõ.
- Với dịch vụ có **nhiều tier**, bảng này ưu tiên ghi:
  - **entry / phổ biến / dễ đối chiếu**, và
  - ghi chú thêm nếu nhà cung cấp có **mức giá thấp hơn ở volume lớn**.
- Bảng này chỉ phục vụ **đối chiếu chi phí thô**, chưa phản ánh sự khác nhau về:
  - search quality,
  - freshness,
  - localization,
  - AI / grounding features,
  - SLA / legal / governance.

---

## Bảng giá quy đổi

| Ứng viên | Giá quy đổi / 1.000 request | Cơ sở quy đổi | Nguồn official |
|---|---:|---|---|
| **Brave Search API** | **$5 / 1.000 requests** | Pricing page ghi rõ “$5.00 per 1,000 requests” cho gói Search | https://api-dashboard.search.brave.com/documentation/pricing |
| **Serper** | **$1.00 / 1.000 query** (Starter) | Pricing page ghi “50k credits ($1.00/1k)” ở gói Starter | https://serper.dev/ |
| **Serper (volume lớn)** | **$0.30 / 1.000 query** | Pricing page ghi “12.5M credits ($0.30/1k)” ở gói Ultimate | https://serper.dev/ |
| **SearchAPI.io** | **$4 / 1.000 searches** | Pricing page ghi “$4 per 1,000 searches” ở Developer Plan | https://www.searchapi.io/pricing |
| **SerpApi** | **$25 / 1.000 searches** | Pricing page ghi “$25 / month” cho “1,000 searches per month” ở Starter | https://serpapi.com/pricing |
| **Autom** | **$1 / 1.000 request** | Pricing page ghi “$50” cho “50k credits”; quy đổi ra $1 / 1.000 nếu 1 credit ≈ 1 request chuẩn | https://www.autom.dev/pricing |
| **Piloterr (USD)** | **$2.72 / 1.000 request** | Pricing page ghi “$49/mo”, “18,000 credits”, và “1 credit = standard API request” ⇒ 49 / 18 ≈ 2.72 | https://www.piloterr.com/pricing |
| **Piloterr (EUR)** | **€2.50 / 1.000 request** | Pricing page ghi “45€/mo”, “18,000 credits”, và “1 credit = standard API request” ⇒ 45 / 18 = 2.50 | https://www.piloterr.com/pricing |
| **Google Custom Search JSON API** | **$5 / 1.000 queries** | Overview page ghi “Additional requests cost $5 per 1000 queries” | https://developers.google.com/custom-search/v1/overview |
| **Grounding with Bing Search** | **$14 / 1.000 transactions** | Pricing page ghi “$14 per 1,000 transactions” | https://www.microsoft.com/en-us/bing/apis/grounding-pricing |

---

## Trích dẫn giá chính từ nguồn official

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

## Xếp theo giá rẻ → đắt (mốc đối chiếu)

> Lưu ý: thứ tự dưới đây là **so theo giá quy đổi thô / 1.000 request**.  
> Không phản ánh chất lượng search hay tính năng AI.

1. **Serper (Ultimate volume lớn)** — $0.30 / 1.000
2. **Serper (Starter)** — $1.00 / 1.000
3. **Autom** — khoảng $1.00 / 1.000
4. **Piloterr (EUR)** — €2.50 / 1.000
5. **Piloterr (USD)** — $2.72 / 1.000
6. **SearchAPI.io** — $4.00 / 1.000
7. **Brave Search API** — $5.00 / 1.000
8. **Google Custom Search JSON API** — $5.00 / 1.000
9. **Grounding with Bing Search** — $14.00 / 1.000
10. **SerpApi** — $25.00 / 1.000

---

## Ghi chú quan trọng

### 1. Serper có nhiều mức giá
Serper không chỉ có một mức duy nhất.  
Nếu dùng để so sánh công bằng ở mức entry, có thể lấy:
- **$1.00 / 1.000** ở Starter

Nếu muốn xét khả năng scale volume lớn, có thể dùng:
- **$0.30 / 1.000** ở Ultimate

### 2. Autom là mô hình credit
Trong pricing page, Autom công bố:
- “$50”
- “50k credits”

Bảng này quy đổi theo giả định thực dụng:
- **1 credit ≈ 1 request chuẩn**

Nếu sau này phát hiện một endpoint cụ thể có mức trừ credit khác, cần điều chỉnh riêng cho endpoint đó.

### 3. Piloterr có hai bảng giá tiền tệ
Piloterr hiển thị cả:
- **USD** và
- **EUR**

Do đó, để tránh nhầm lẫn, bảng này giữ cả hai mốc quy đổi.

### 4. Google Custom Search JSON API
Google ghi rất rõ:
- API này **không dành cho khách hàng mới**
- pricing hiện tại chỉ áp dụng cho **existing customers**
- dịch vụ sẽ ngừng vào **01/01/2027**

Vì vậy, dù giá quy đổi là **$5 / 1.000**, đây **không phải lựa chọn tốt cho dự án mới**.

### 5. Grounding with Bing Search
Mức giá **$14 / 1.000 transactions** áp dụng cho dịch vụ grounding trong hệ Azure AI / Bing Grounding, **không phải Bing Web Search API kiểu cũ**.

---

## Kết luận ngắn

Nếu chỉ xét **giá / 1.000 request**:
- **rẻ nhất ở quy mô lớn** là **Serper**
- **rẻ ở mức entry** là **Serper** và **Autom**
- **mid-tier** là **Piloterr** và **SearchAPI.io**
- **đắt hơn đáng kể** là **Grounding with Bing Search** và **SerpApi**

Tuy nhiên, khi chọn cho project AI / Grounding / RAG / Agentic AI, cần kết hợp thêm:
- localization tiếng Nhật,
- freshness,
- AI integration,
- SLA / compliance,
- và độ phù hợp với production.
