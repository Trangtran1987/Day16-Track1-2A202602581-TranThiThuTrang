# Memo Teardown — Claude Science (Anthropic)

**Họ tên:** Tran Thi Thu Trang — MSV 2A202602581

**Vì sao chọn sản phẩm này:** (1–2 câu)

**§1. Timeline các cập nhật lớn**

*Phạm vi: timeline mảng khoa học / life sciences của Anthropic, đích đến là Claude Science.*

| Thời điểm | Cập nhật | Context lúc đó | Nguyên lý |
|---|---|---|---|
| 05/2025 | **Chương trình AI for Science**: tặng tới $20.000 API credits cho nhóm nghiên cứu, ưu tiên sinh học, có review an toàn sinh học. [Nguồn](https://www.anthropic.com/news/ai-for-science-program) | Anthropic chưa có sản phẩm khoa học, chỉ bán API. Google vừa công bố AI co-scientist (2/2025). | **Vòng lặp học**: đổi credits lấy use case thật từ nhà khoa học trước khi build sản phẩm, đồng thời tìm early adopters. |
| 10/2025 | **Claude for Life Sciences**: Sonnet 4.5 + connector MCP tới Benchling, 10x Genomics, PubMed, BioRender…; thêm skill QC cho dữ liệu single-cell RNA. [Nguồn](https://www.anthropic.com/news/claude-for-life-sciences) · [CNBC](https://www.cnbc.com/2025/10/20/anthropic-claude-life-sciences-research-ai.html) | Sonnet 4.5 vừa ra, mạnh về agent; MCP đã thành chuẩn. Pharma lớn đã thử (Novo Nordisk rút tài liệu nghiên cứu lâm sàng từ hơn 10 tuần xuống 10 phút). | **Wrapper → moat**: gắn AI vào đúng nơi dữ liệu thí nghiệm đang nằm sẵn (ELN, dữ liệu genomics), không làm chatbot đứng riêng. |
| 01/2026 | **Claude for Healthcare + mở rộng Life Sciences** (công bố quanh hội nghị JPM26): chuẩn HIPAA, connector Medidata, ClinicalTrials.gov, ChEMBL, Open Targets…; **Agent Skills** cho soạn protocol thử nghiệm lâm sàng, triển khai scVI-tools/Nextflow. [Nguồn](https://www.anthropic.com/news/healthcare-life-sciences) | Đã có khách pharma từ mốc 10/2025. Cuộc đua AI y tế nóng lên. | **Vertical AI = AI Expert + Domain Expert**: đóng gói hiểu biết domain thành Skills và đáp ứng tuân thủ (HIPAA), thứ model chung không tự có. |
| 04/2026 | **Mua Coefficient Bio** (~$400 triệu bằng cổ phiếu, đội dưới 10 người); đây là thương vụ mua lớn đầu tiên của Anthropic. [Nguồn](https://thenextweb.com/news/anthropic-just-paid-400-million-for-a-startup-with-fewer-than-10-people) | Đã có connector và skills, nhưng thiếu người hiểu sâu quy trình làm thuốc từ bên trong. | **Vertical AI**: mua thẳng nửa "Domain Expert" (đội ngũ, không phải công nghệ) thay vì tự học dần. |
| 30/06/2026 | **Claude Science** (beta): app "AI workbench" chạy macOS/Linux; agent điều phối với hơn 60 skills/connector (genomics, proteomics, structural biology, cheminformatics); mọi output đều có lịch sử truy vết; GPU qua Modal do user tự trả; dùng chung hạn mức gói Pro/Max/Team/Enterprise. [Nguồn](https://www.anthropic.com/news/claude-science-ai-workbench) · [TechCrunch](https://techcrunch.com/2026/06/30/anthropics-claude-science-bets-on-workflow-not-a-new-model-to-win-over-scientists/) | Nhà khoa học vẫn phải nhảy qua lại giữa database, notebook, terminal và cluster. Claude Code đã chứng minh mô hình "agent + công cụ" thắng ở mảng lập trình. | **x10**: gom cả chuỗi công cụ rời rạc vào một môi trường, agent chạy từ đầu đến cuối, nên cải thiện theo cấp số chứ không phải 10%. Kèm **moat workflow**: TechCrunch nhận định Anthropic "đặt cược vào workflow, không phải model mới". |
| 30/06/2026 | **Anthropic tự chạy chương trình phát triển thuốc** cho bệnh bị lãng quên (neglected diseases). [Nguồn](https://www.cnbc.com/2026/06/30/anthropic-launches-ai-drug-discovery-program-claude-science.html) | Ra cùng ngày với Claude Science; cần uy tín với khách pharma. | **Vòng lặp học (dogfooding)**: chính Anthropic nói "We believe in the power of tight feedback loops", tự dùng sản phẩm để thấy chỗ workflow gãy. |
| 09/2026 | **Life Sciences Verification Program** (beta): tổ chức đã xác minh được dùng Mythos/Opus/Sonnet với rào chắn an toàn nới hơn cho nghiên cứu sinh học; chia 2 mức Standard và High-risk. [Nguồn](https://www.unite.ai/anthropic-launches-life-sciences-verification-program-in-beta/) · [HPCwire](https://www.hpcwire.com/aiwire/2026/09/21/anthropic-eases-ai-safeguards-for-verified-life-science-teams/) | Model mạnh về sinh học (Mythos) bị rào chắn an toàn chặn đúng những việc hợp pháp mà pharma cần làm. | **Định nghĩa "tốt" theo domain**: với sinh học, "tốt" là vừa đủ mạnh vừa an toàn có kiểm soát; niềm tin và cơ chế xác minh trở thành moat. |

**Vì sao chọn những mốc này:** Mình chỉ giữ các quyết định làm thay đổi *sản phẩm, đối tượng khách hàng hoặc mô hình* của mảng khoa học. Các mốc đã loại:
- Tuyển Eric Kauderer-Abrams làm head of life sciences (2025): đây là quyết định nhân sự, không phải quyết định sản phẩm.
- Bài nghiên cứu "tăng tốc hơn 30 model sinh học phân tử khoảng 4 lần" (9/2026): đây là kết quả nghiên cứu, mang tính marketing.
- Các connector/skill lẻ được thêm dần: đây là cập nhật nhỏ.
- Các bản model chung (Sonnet 4.5, Mythos): không riêng cho mảng khoa học, nên chỉ đưa vào cột Context.

**§2. Tệp user & JTBD**

| | Early adopters (2025 – đầu 2026) | Tệp hiện tại (từ 6/2026) |
|---|---|---|
| Đặc điểm | **Nhà sinh học tính toán / bioinformatician ở lab học thuật** (postdoc, nghiên cứu sinh) làm genomics, single-cell; đã quen viết Python/R trên Jupyter và chạy HPC của trường; dùng Claude qua API nhờ credits của AI for Science. Ví dụ: nhóm nghiên cứu glioma ở UCSF Brain Tumor Center, Allen Institute, Centre for Population Genomics. | 2 nhóm mới: **(a) đội R&D / clinical / regulatory ở pharma và biotech** (Novo Nordisk, Sanofi, AbbVie, Manifold Bio), mua qua gói Team/Enterprise; **(b) nhà khoa học "wet-lab" không giỏi code** (bác sĩ nghiên cứu, nhà thần kinh học), nay dùng được nhờ app có sẵn công cụ. |
| JTBD chính | "Đi từ dữ liệu thô (sequencing, single-cell) tới kết quả phân tích và hình vẽ dùng được cho paper mà không mất cả tuần viết script và cấu hình pipeline." Kèm theo: "làm tổng quan tài liệu nhanh mà vẫn truy được nguồn." | (a) "Rút ngắn đường từ câu hỏi sinh học tới bằng chứng đủ chắc để hội đồng duyệt hoặc nộp cơ quan quản lý, kèm dấu vết kiểm toán" (chọn target, soạn tài liệu lâm sàng). (b) "Tự trả lời câu hỏi trên dữ liệu của mình mà không phải xếp hàng chờ nhóm bioinformatics." |
| Trước đó họ làm bằng cách nào | Tự viết script, nhảy qua lại giữa PubMed, database, notebook, terminal và cluster; nhờ ChatGPT/Claude chat viết từng đoạn code rồi chép tay sang. | (a) Chuyển việc tuần tự giữa nhiều nhóm (bioinformatics, medical writing, CRO) và nhiều hệ thống rời (Benchling, Medidata); một tài liệu lâm sàng có thể mất hơn 10 tuần. (b) Gửi yêu cầu cho core bioinformatics, chờ vài tuần, hoặc bỏ câu hỏi. |

Nguồn: [The Scientist](https://www.the-scientist.com/early-verdicts-on-claude-science-faster-workflows-but-gaps-remain-74745) · [Hacker News](https://news.ycombinator.com/item?id=48735770) · [TechCrunch](https://techcrunch.com/2026/06/30/anthropics-claude-science-bets-on-workflow-not-a-new-model-to-win-over-scientists/) · [CNBC 10/2025](https://www.cnbc.com/2025/10/20/anthropic-claude-life-sciences-research-ai.html) · [Anthropic – rare disease grants](https://www.anthropic.com/news/rare-disease-research-grants)

**Dịch chuyển tệp:** có 2 mốc ở §1 gây ra dịch chuyển:
- **10/2025, Claude for Life Sciences**: connector tới Benchling, 10x… đưa Claude vào hệ thống doanh nghiệp đang dùng, nên pharma (Novo Nordisk, Sanofi) trở thành khách hàng. Mốc **01/2026** (HIPAA, Medidata, skill soạn protocol) mở tiếp sang đội clinical và regulatory.
- **06/2026, Claude Science**: app có sẵn hơn 60 skills, agent tự chạy end-to-end, không cần tự cài môi trường, nên người *không biết code* cũng dùng được. Tệp user mở rộng từ "người biết code" sang "người có câu hỏi khoa học".

**Switching cost (map 4 forces):**

| Lực | Nội dung với Claude Science |
|---|---|
| **Push**: vấn đề với cách hiện tại | Công cụ rời rạc; phải tự code và cấu hình HPC; chờ core bioinformatics; tài liệu lâm sàng làm tay nhiều tuần. |
| **Pull**: sức hút của cái mới | Hơn 60 skills/connector có sẵn; agent chạy từ đầu đến cuối; output có lịch sử truy vết, tái lập được; chạy local (dữ liệu nhạy cảm không phải rời máy); không tính phí riêng ngoài gói Claude. Đối thủ thì khó tiếp cận: GPT-Rosalind của OpenAI chỉ mở cho doanh nghiệp Mỹ đã qua thẩm định. |
| **Habit**: thói quen cũ | Pipeline Nextflow/R/Jupyter đã chạy ổn; quy trình phê duyệt nội bộ của pharma; văn hoá "tự tay làm thì mới tin" của giới khoa học. |
| **Anxiety**: nỗi lo khi chuyển | Trích dẫn bịa (HN: "includes at least one hallucinated reference"); AI "không biết tự nghi ngờ" (Lecoq, Allen Institute); lo dữ liệu độc quyền bị dùng để huấn luyện; rào chắn an toàn sinh học chặn cả việc hợp pháp; sợ bị khoá vào một nhà cung cấp; phí khoảng $200/tháng; mới hỗ trợ sinh học. |

**Lực mạnh nhất hiện nay là Pull.** Dữ liệu của user vẫn nằm ở Benchling, Medidata, kho dữ liệu của trường; Claude Science chỉ *kết nối* tới chứ không *giữ* dữ liệu. Vì vậy switching cost thực tế còn thấp. Nếu một đối thủ ra workbench tương đương, user có thể chuyển khá dễ. Điều này giải thích vì sao Anthropic đang xây lực giữ chân bằng thứ khó sao chép: niềm tin và quyền truy cập đã xác minh (LSVP 9/2026), uy tín tự làm thuốc (6/2026), và lịch sử phân tích có truy vết nằm trong app.

**§3. Ba dự đoán hướng đi (6–12 tháng tới)**

**Dự đoán 1** *(loại: mở rộng tính năng / segment / mô hình kiếm tiền / đe dọa Big Tech)*
- **Dự đoán:** …
- **Lập luận:** … *(dẫn ngược về §1–§2)*

**Dự đoán 2** *(loại: …)*
- **Dự đoán:** …
- **Lập luận:** …

**Dự đoán 3** *(loại: …)*
- **Dự đoán:** …
- **Lập luận:** …

**§4. AI Log**

| Việc | AI làm hay bạn làm? | Bạn kiểm chứng/phán đoán lại thế nào? |
|---|---|---|
| Tóm tắt đề bài lab và hướng dẫn các bước | AI (Claude Code) | |
| Tìm nhanh các mốc ứng viên của mảng khoa học/life sciences của Anthropic | AI (Claude Code, web search) | |
| Soạn nháp bảng timeline 7 mốc, context và gợi ý nguyên lý | AI (Claude Code) soạn nháp | |
| Chốt mốc giữ/loại và nguyên lý cuối cùng cho từng mốc | Bạn | |
| Tìm review/thảo luận user (The Scientist, Hacker News, TechCrunch) và soạn nháp §2 (bảng tệp user, JTBD, 4 forces) | AI (Claude Code) soạn nháp | |
| Chọn lực mạnh nhất trong 4 forces và nhận định switching cost | Bạn | |
| | | |
