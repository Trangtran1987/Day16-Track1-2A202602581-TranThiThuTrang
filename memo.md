# Memo Teardown — Claude Science (Anthropic)

**Họ tên:** Trần Thị Thu Trang — MSV 2A202602581

**Vì sao chọn sản phẩm này:** Tôi chọn sản phẩm này vì nó khá mới ra và có liên quan tới công việc của tôi trước kia.
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

**Dự đoán 1** *(loại: mở rộng segment, R&D doanh nghiệp có quản lý)*
- **Dự đoán:** Trong 6–12 tháng, Claude Science sẽ có bản **Enterprise cho pharma**: hỗ trợ workflow chuẩn GxP/validated, nhật ký kiểm toán đủ để nộp cơ quan quản lý, triển khai trong hạ tầng riêng của khách (VPC/on-prem) với cam kết không dùng dữ liệu để huấn luyện, gắn với quyền truy cập đã xác minh của LSVP.
- **Lập luận:** Chuỗi mốc §1 đi đúng hướng này: HIPAA (01/2026), rồi workbench có lịch sử truy vết (06/2026), rồi LSVP (09/2026). Ở §2, JTBD của tệp pharma là "bằng chứng kèm dấu vết kiểm toán", còn lực Anxiety lớn nhất là lo dữ liệu độc quyền. Tin tuyển dụng PM Claude Science ghi rõ việc "making the workbench ready for enterprise R&D teams", và có vị trí phụ trách "GxP/validated workflows, auditability" ([job](https://job-boards.greenhouse.io/anthropic/jobs/5394887008)).

**Dự đoán 2** *(loại: mở rộng tính năng, lab-in-the-loop)*
- **Dự đoán:** Claude Science sẽ **kết nối trực tiếp với thiết bị phòng thí nghiệm** (máy hút dịch tự động, kính hiển vi, robot) theo chuẩn Model Hardware Standard. Agent sẽ khép kín vòng: thiết kế thí nghiệm, gửi lệnh chạy, nhận dữ liệu về, rồi phân tích.
- **Lập luận:** Nguyên lý **vòng lặp học** đã lặp lại 2 lần ở §1 (AI for Science 05/2025, tự làm thuốc 06/2026), và Anthropic đang xây wet lab riêng ([ODSC](https://opendatascience.com/anthropic-builds-biology-lab-as-claude-moves-into-physical-science/)). Workbench mới đạt **x10** ở phần tính toán; khâu chạy thí nghiệm thật vẫn đứt. Quan trọng hơn, §2 chỉ ra switching cost đang thấp vì dữ liệu nằm ngoài Claude Science. Khi dữ liệu thí nghiệm *sinh ra ngay trong* hệ thống, Anthropic chuyển được từ "kết nối dữ liệu" sang "giữ dữ liệu", tức tạo moat thật.

**Dự đoán 3** *(loại: mở rộng segment sang ngành khoa học khác, phản ứng với Big Tech)*
- **Dự đoán:** Claude Science sẽ ra **bộ skills/connector cho hoá học và vật liệu** (phổ NMR, cơ sở dữ liệu tinh thể, tính toán DFT trên HPC), là ngành đầu tiên ngoài sinh học, để không nhường mảng khoa học vật lý cho Google.
- **Lập luận:** §1 cho thấy mỗi lần mở một ngành, Anthropic đi cùng một khuôn: **credits → connector → skills → sản phẩm** (05/2025 → 10/2025 → 01/2026 → 06/2026). Khuôn này đang bắt đầu lại với hoá học: Anthropic đã công bố nghiên cứu NMR với Opus 4.7, mở credits cho các ngành ngoài sinh học, và tin tuyển PM có "expanding into new scientific fields". Ở §2, lời chê rõ nhất từ user là "zero connectors for non biology". Về Big Tech, Google đang đưa AI co-scientist vào cả 17 phòng thí nghiệm quốc gia của Bộ Năng lượng Mỹ (DOE) và ra Gemini for Science ([DeepMind](https://deepmind.google/blog/google-deepmind-supports-us-department-of-energy-on-genesis/)). Nếu Claude Science chỉ có sinh học, Anthropic sẽ mất tệp vật lý/hoá học.

*Tự đánh giá:* Mình tự tin nhất ở **Dự đoán 1**, vì có cả chuỗi mốc lẫn tin tuyển dụng ủng hộ. Giả định có thể làm nó gãy: pharma chấp nhận dùng Claude qua cloud sẵn có (Bedrock/Vertex) thay vì cần bản Enterprise riêng của Claude Science.

**§4. AI Log**

| Việc | AI làm hay bạn làm? | Bạn kiểm chứng/phán đoán lại thế nào? |
|---|---|---|
| Tóm tắt đề bài lab và hướng dẫn các bước | AI (Claude Code) | Đọc lại đề bài gốc, đối chiếu xem AI có bỏ sót yêu cầu, checkpoint hoặc deliverable nào không. |
| Tìm nhanh các mốc ứng viên của mảng khoa học/life sciences của Anthropic | AI (Claude Code, web search) | Kiểm tra lại nguồn chính thức của Anthropic, đối chiếu ngày tháng và nội dung của từng mốc; loại những thông tin không có nguồn đáng tin cậy. |
| Soạn nháp bảng timeline 7 mốc, context và gợi ý nguyên lý | AI (Claude Code) soạn nháp | Đối chiếu timeline với nguồn gốc; kiểm tra xem context có đúng với từng mốc không. |
| Chốt mốc giữ/loại và nguyên lý cuối cùng cho từng mốc | Bạn |Đọc các mốc và chỉ giữ các quyết định làm thay đổi sản phẩm |
| Tìm review/thảo luận user (The Scientist, Hacker News, TechCrunch) và soạn nháp §2 (bảng tệp user, JTBD, 4 forces) | AI (Claude Code) soạn nháp | Với JTBD và 4 forces, tự xem lại từ góc nhìn người dùng thay vì chấp nhận nguyên văn kết quả của AI. |
| Chọn lực mạnh nhất trong 4 forces và nhận định switching cost | Bạn | Dựa trên review và thảo luận công khai của user (The Scientist, Hacker News). |
| Tìm tín hiệu cho dự đoán (tin tuyển dụng, wet lab, nghiên cứu hoá học, động thái Google) và soạn nháp 3 dự đoán §3 | AI (Claude Code) soạn nháp | Kiểm tra nguồn, ngày đăng và mức độ liên quan của từng tín hiệu; phân biệt fact với suy luận/dự đoán. |
| Chọn 3 dự đoán giữ lại và tự đánh giá dự đoán nào chắc nhất | Bạn | Xem lại bằng chứng cho từng dự đoán, kiểm tra giả định ngầm và mức độ chắc chắn; loại dự đoán nếu bằng chứng yếu hoặc quá phụ thuộc vào suy đoán. |
