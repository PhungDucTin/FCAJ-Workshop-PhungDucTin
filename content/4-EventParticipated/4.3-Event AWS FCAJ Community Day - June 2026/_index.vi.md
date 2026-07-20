---
title: "Event 3"
date: 2026-06-27
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---

# Bài Thu Hoạch "First Cloud AI Journey Community Day - June 2026"

<h4 align="center"><em></em></h4>

![Poster](</images/4-EventParticipated/4.3-Event AWS FCAJ Community Day - June 2026/Evt_3.png>)

### Mục Đích Của Sự Kiện

- Chia sẻ kiến thức và kinh nghiệm thực chiến về các công nghệ Cloud (đặc biệt là AWS) và Trí tuệ nhân tạo (GenAI).
- Hướng nghiệp và chia sẻ về con đường phát triển sự nghiệp (career path) của kỹ sư Cloud trong kỷ nguyên AI.
- Cập nhật các giải pháp AI mới nhất như Voice AI cho tiếng Việt, AWS DevOps Agent, và ứng dụng Amazon Q trong vận hành nhân sự và bảo mật.
- Tạo không gian giao lưu, hỏi đáp trực tiếp giữa các chuyên gia, diễn giả từ các công ty công nghệ và cộng đồng kỹ sư, sinh viên tham dự sự kiện.

### Danh Sách Diễn Giả

- **Steve Tran** - CTO/Founder, CloudThinker
- **Trung Vu** – CEO, Revve AI
- **Nghi Danh** - AI Engineer, Renova Cloud
- **Kiet Tran** - AI Engineer, AWS Student Builder Group
- **Nguyen Nguyen** - Cloud Engineer, Cloud Kinetics
- **Bao Phan** - Cloud Engineer, Cloud Kinetics
- **Truong Tran** - AI Solution Sales, Noventiq
- **Anh Dang** - Solution Sales, Noventiq
- **Toan Nguyen** - AWS Security Builder

### Nội Dung Nổi Bật

#### Định hướng nghề nghiệp & Ứng dụng Agentic Platform trong hạ tầng Cloud (Trình bày: Steve Tran)

- **Tư duy AI (AI Mindset) trong lộ trình sự nghiệp:** Thị trường đang dịch chuyển từ việc tuyển dụng số lượng lớn sang ưu tiên các kỹ sư Senior biết ứng dụng AI. Để không bị đào thải, các kỹ sư cần sớm cọ xát với bài toán doanh nghiệp thực tế.
- **Giải quyết nợ công nghệ (Technical Debt):** Giới thiệu nền tảng Agentic AI chuyên dụng để hỗ trợ vận hành Cloud Infrastructure, giúp tự động hóa việc xử lý sự cố, tối ưu chi phí (FinOps) và kiểm thử bảo mật.
- **Multi-Agent vs Single-Agent:** Dù Single-Agent có thể làm được hầu hết tác vụ, nhưng kiến trúc Multi-Agent lại ưu việt hơn nhờ khả năng giới hạn Context Window, tiết kiệm chi phí và đặc biệt hiệu quả trong việc phân quyền theo chức năng (RBAC) cho hệ thống lớn.

#### Xây dựng Voice AI Assistant tối ưu cho tiếng Việt (Trình bày: Trung Vu & Kiet Tran & Nghi Danh)

- **Thách thức ngôn ngữ:** Tiếng Việt là một ngôn ngữ "low resource" đối với các model Speech-to-Speech lớn. Giải pháp thực tiễn là sử dụng luồng: Speech-to-Text -> LLM xử lý ngữ cảnh -> Text-to-Speech.
- **Tinh chỉnh cho doanh nghiệp (Enterprise Customization):** Hệ thống AI được tinh chỉnh để biết cách ngắt lời lịch sự, nhận diện giới tính (để xưng hô Anh/Chị), và thực hiện các tác vụ tự động (Tool Calling). Đặc biệt, hệ thống có khả năng chuyển giao mượt mà cho nhân viên tư vấn thật (Human Handoff) khi phát hiện khách hàng không hài lòng.

#### Tự động hóa điều tra sự cố với AWS DevOps Agent (Trình bày: Nguyen Nguyen & Bao Phan)

- **Giải quyết sự phân mảnh dữ liệu:** Khi có lỗi, DevOps thường mất nhiều thời gian tra cứu log/trace rải rác. AWS DevOps Agent giúp tự động tổng hợp thông tin, xây dựng Topology của hệ thống để khoanh vùng sự cố.
- **Quy trình 4 bước tự động:** Bao gồm Phân loại -> Điều tra nguyên nhân gốc (Root Cause) -> Đề xuất hướng giải quyết -> Đề xuất cải thiện kiến trúc.
- **Con người làm chủ:** AI đóng vai trò điều tra và xuất kịch bản sửa lỗi (script), nhưng quyền phê duyệt và thực thi (Execute) hoàn toàn thuộc về con người để đảm bảo tính an toàn.

#### Ứng dụng Amazon Q chuyển đổi số quy trình Nhân sự (HR) (Trình bày: Truong Tran & Anh Dang)

- **Giải quyết nỗi đau của HR:** Các phương pháp sàng lọc CV thủ công mất nhiều thời gian, dễ rập khuôn theo cảm tính, và có nguy cơ rò rỉ dữ liệu nội bộ nếu HR dùng các AI public.
- **Sức mạnh tự động hóa của Amazon Q:** Có thể được huấn luyện (Skills) để tự động đối chiếu CV ứng viên với Job Description, chấm điểm chi tiết từng kỹ năng và xuất báo cáo tổng quan.
- **Kết nối linh hoạt:** Dễ dàng đọc dữ liệu trực tiếp từ hệ sinh thái có sẵn của doanh nghiệp như Microsoft SharePoint, OneDrive hay Google Workspace mà không cần di chuyển dữ liệu.

#### Bảo mật kết nối giữa Amazon Q và MCP Server nội bộ (Trình bày: Toan Nguyen & Nghi Danh)

- **Rủi ro Public Endpoint:** Đưa dữ liệu doanh nghiệp từ các MCP Server (như JIRA, Internal Database) ra internet công cộng để AI truy cập là lỗ hổng bảo mật cực kỳ nguy hiểm.
- **Giải pháp bảo mật mạng riêng (Private Connection):** Kiến trúc kết nối an toàn sử dụng VPC Connection kết hợp với Application Load Balancer (ALB) và mã hóa TLS. Giải pháp này đảm bảo luồng giao tiếp của Amazon Q và hệ thống nội bộ hoàn toàn nằm trong môi trường bảo mật của AWS, tuân thủ nghiêm ngặt các quy định về Compliance.

### Những Gì Học Được

#### Chuyển dịch Tư duy & Định hướng sự nghiệp

- **Từ "Thợ Code" đến "Người Điều Phối Hệ Thống":** Lập trình viên hiện đại không nên chỉ cạnh tranh bằng tốc độ gõ code, vì AI đã làm điều đó quá tốt. Thay vào đó, giá trị cốt lõi nằm ở khả năng phân tích nghiệp vụ, thiết kế kiến trúc và sử dụng AI như một "Copilot" để tăng tốc độ giải quyết bài toán (Problem Solving).
- **Business-First Approach:** Đừng lạm dụng AI chỉ vì nó là xu hướng. Mọi giải pháp AI đưa vào doanh nghiệp (như dùng Amazon Q cho phòng HR hay Agentic cho DevOps) đều phải giải quyết được những nỗi đau thực tế: giảm thiểu lỗi thủ công, rút ngắn thời gian (MTTR/Time-to-hire), và tối ưu chi phí (FinOps).

#### Bài học về Kiến trúc & Thiết kế Hệ thống AI

- **Sức mạnh của Multi-Agent:** Đối với các bài toán quy mô lớn, việc nhồi nhét mọi "skill" vào một mô hình AI duy nhất (Single-Agent) dễ dẫn đến quá tải bộ nhớ ngữ cảnh (Context Window) và khó phân quyền. Việc chia nhỏ thành các Agent chuyên biệt (Multi-Agent) hoạt động dưới sự điều phối chung giúp hệ thống dễ bảo trì, tối ưu chi phí token và quản lý quyền truy cập (RBAC) chặt chẽ hơn.
- **Chia để trị (Decoupled Workflows):** Bài học từ team làm Voice AI cho thấy, với các ngôn ngữ ít tài nguyên như tiếng Việt, không nên dựa dẫm vào một model Speech-to-Speech nguyên khối. Việc bóc tách luồng xử lý thành Speech-to-Text -> LLM -> Text-to-Speech giúp hệ thống linh hoạt hơn, dễ tinh chỉnh ngữ cảnh (xưng hô giới tính, ngắt lời) và gọi hàm (Tool Calling) chính xác hơn.
- **Observability là điều kiện tiên quyết:** AWS DevOps Agent rất thông minh, nhưng nó sẽ bị "mù" nếu hạ tầng không được thiết lập sẵn các luồng ghi log, metrics và alarm tiêu chuẩn. Dữ liệu đầu vào minh bạch thì AI mới có thể chẩn đoán đúng bệnh.

#### Tiêu chuẩn Vận hành và Bảo mật trong Doanh nghiệp 

- **Nguyên tắc "Human-in-the-loop" (Con người làm chủ):** Dù AI có khả năng tự động hóa mạnh mẽ, quyền quyết định cuối cùng ở các tác vụ quan trọng luôn phải do con người kiểm soát. Ví dụ: DevOps Agent chỉ đề xuất kịch bản sửa lỗi, kỹ sư mới là người bấm lệnh chạy; hoặc Voice AI sẽ tự động chuyển tiếp (Human Handoff) cho nhân viên thật khi khách hàng có dấu hiệu không hài lòng.
- **Bảo mật kết nối AI (Private Networking) là sống còn:** Khi đưa AI vào đọc dữ liệu nội bộ của công ty (Database, Jira, Hồ sơ nhân sự...), tuyệt đối không được đưa các API này ra internet công cộng (Public Internet). Việc sử dụng mạng nội bộ khép kín (như VPC Connection kết hợp Application Load Balancer) để kết nối với các MCP Server là tiêu chuẩn bắt buộc để đáp ứng các yêu cầu bảo mật (Compliance) khắt khe nhất.

### Ứng Dụng Vào Công Việc

- **Cập nhật quy trình làm việc:** Áp dụng AI vào việc viết document, tóm tắt log sự cố, và kiểm thử bảo mật cơ bản để tiết kiệm thời gian, tập trung giải quyết các logic nghiệp vụ phức tạp.
- **Thử nghiệm tích hợp AI Assistant:** Đăng ký và dùng thử các công cụ như AWS DevOps Agent (hiện đang có bản free) hoặc Amazon Q để đánh giá khả năng tối ưu hóa thời gian xử lý công việc (MTTR) cho team hiện tại.
- **Rà soát bảo mật kết nối AI:** Nếu dự án hiện tại đang dùng API của OpenAI/Anthropic để đọc dữ liệu công ty, cần đề xuất quy hoạch lại luồng dữ liệu (sử dụng PrivateLink, VPC) để tránh rò rỉ thông tin nhạy cảm.
- **Lan tỏa ứng dụng AI cho Non-Tech:** Phối hợp với phòng HR hoặc Operation để xây dựng các bot tự động hóa quy trình đọc file/báo cáo nội bộ, giúp họ thấy được giá trị thực tế của Cloud và AI.

### Trải nghiệm trong event

Sự kiện “FCAJ Community Day - June 2026” là một trong những trải nghiệm chân thực và giá trị nhất về việc mang AI từ "lý thuyết" vào "thực chiến" trong môi trường doanh nghiệp.

#### Học hỏi từ các diễn giả có chuyên môn cao
- Các diễn giả đến từ các công ty như **Cloud Thinker**, **Revve AI**, **Cloud Kinetics** và **Noventiq** đã chia sẻ những best practices trong việc thiết kế và vận hành hệ thống AI hiện đại.
- Qua các case study thực tế (như bài toán chấm điểm CV cho HR hay xử lý sự cố hạ tầng), mình hiểu rõ hơn lý do và cách áp dụng kiến trúc Multi-Agent System thay vì Single-Agent, cũng như cách thiết lập các tiêu chuẩn vận hành an toàn **(Enterprise Standards)** vào các project lớn.

#### Trải nghiệm kỹ thuật thực tế
- Tận mắt chứng kiến các phiên live-demo chuyên sâu giúp mình hình dung rõ cách bóc tách luồng xử lý phức tạp, ví dụ như chia nhỏ mô hình Voice AI tiếng Việt thành các cụm **Speech-to-Text, LLM và Text-to-Speech** để tối ưu độ trễ và độ chính xác.
- Học cách nhận diện và phòng chống rủi ro bảo mật khi tích hợp AI với dữ liệu nội bộ. Nổi bật là giải pháp sử dụng **VPC Connection** kết hợp Application Load Balancer để kết nối bảo mật với các **MCP Server**, tránh việc phơi bày dữ liệu ra Public Internet.
- Rút ra bài học thực chiến qua màn giả lập tấn công hệ thống ép tải: quan sát cách AI tự động truy vết log để tìm nguyên nhân gốc rễ (Root Cause) nhưng vẫn tuân thủ nghiêm ngặt nguyên tắc **"Human-in-the-loop"** (luôn cần con người phê duyệt kịch bản sửa lỗi).

#### Ứng dụng công cụ hiện đại
- Trực tiếp tìm hiểu về khả năng tự động hóa luồng công việc của **Amazon Q**, biến hàng tá CV ứng viên lộn xộn thành một báo cáo chấm điểm và đối chiếu trực quan (HTML Report) chỉ trong vài giây, giúp giải phóng sức lao động cho bộ phận HR.
- Hiểu sâu hơn về các công cụ hỗ trợ hạ tầng như **AWS DevOps Agent**, công cụ giúp gom nhóm dữ liệu log/trace bị phân mảnh thành một bản đồ Topology rõ ràng, giúp rút ngắn tối đa thời gian MTTR (Mean Time To Recovery).

#### Kết nối và trao đổi
- Workshop tạo cơ hội trao đổi trực tiếp với các chuyên gia, đồng nghiệp trong ngành thông qua các phiên Q&A rất thực tế (như hỏi đáp về bài toán chi phí truyền tải dữ liệu khi dùng Amazon Q hay cách xử lý giọng địa phương của Voice AI). Điều này giúp mở rộng networking và định hình rõ hơn yêu cầu khắt khe của thị trường việc làm hiện tại.
- Qua các ví dụ thực tế, mình nhận ra tầm quan trọng của **Business-first approach** và **AI Mindset**: thay vì gõ code thủ công hay lạm dụng AI một cách vô định, kỹ sư thời nay cần bắt đầu từ việc hiểu đúng bài toán nghiệp vụ để trở thành một "Problem Solver" thực thụ.

#### Bài học rút ra
- Việc áp dụng kiến trúc **Multi-Agent** và chiến lược "chia để trị" (như bóc tách luồng xử lý Voice AI thành STT-> LLM ->  TTS) giúp hệ thống vượt qua giới hạn bộ nhớ (Context Window), phân quyền hiệu quả và tối ưu hóa chi phí vận hành.
- Đưa AI vào môi trường doanh nghiệp bắt buộc phải đặt **Security & Compliance** lên hàng đầu. Tuyệt đối không phơi bày dữ liệu ra Public Internet mà phải dùng kết nối mạng riêng (như **VPC Connection** cho MCP Server), đồng thời luôn tuân thủ nguyên tắc **"Human-in-the-loop"** (con người phải là người phê duyệt quyết định cuối cùng).
- Để AI (như AWS DevOps Agent) phát huy tác dụng, hệ thống hạ tầng phải đảm bảo tính minh bạch dữ liệu **(Observability)** từ trước. Người kỹ sư hiện đại cần trang bị **AI Mindset**, tập trung dùng AI tự động hóa để giải quyết các "nỗi đau" nghiệp vụ thay vì chỉ tập trung gõ code thủ công.

#### Một số hình ảnh khi tham gia sự kiện
<h4 align="center"><em>Ảnh check-in nhóm tại sự kiện</em></h4>

![Ảnh check-in tại sự kiện](</images/4-EventParticipated/4.3-Event AWS FCAJ Community Day - June 2026/anh1.jpg>)

<h4 align="center"><em>Ảnh mọi người tham gia sự kiện</em></h4>

![Ảnh mọi người tham gia sự kiện](</images/4-EventParticipated/4.3-Event AWS FCAJ Community Day - June 2026/anh2.jpg>)
 > Tổng thể, sự kiện "AWS First Cloud AI Journey Community Day - June 2026" đã mở ra một bức tranh hoàn chỉnh về một kỷ nguyên công nghệ mới: AI không còn dừng lại ở việc hỏi - đáp văn bản đơn thuần, mà đang biến thành những Agent chuyên biệt (về Vận hành hạ tầng, Bảo mật, Nhân sự). Để tồn tại và phát triển, những kỹ sư IT cần thoát khỏi lối mòn của "thợ code" để trở thành những người kiến tạo, làm chủ các quy trình tự động hóa.
