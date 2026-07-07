---
title: "Các bài blogs đã dịch"
date: 2026-04-20
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

###  [Blog 1 - Đồ án Mạng xã hội nội bộ "Mini Social Network" – Ứng dụng mô hình 3-Tier Architecture trên nền tảng AWS](3.1-Blog1/)
Blog này chia sẻ về quá trình thiết kế và triển khai đồ án mạng xã hội nội bộ mang tên "Mini Social Network" trên nền tảng AWS Cloud. Dự án này được xây dựng vững chắc dựa trên chuẩn mô hình Kiến trúc 3 lớp (3-Tier Architecture) nhằm đảm bảo tính cô lập và bảo mật dữ liệu ở mức tối đa. Kiến trúc hệ thống được phân tách minh bạch thành hai luồng chính: Data Plane chịu trách nhiệm xử lý luồng truy cập của người dùng và Control Plane đảm nhận công tác vận hành, tự động hóa CI/CD cùng hệ thống giám sát ngầm. Bài blog này sẽ phân tích chi tiết cơ chế vận hành của hệ thống, đồng thời mở ra không gian thảo luận về các giải pháp nâng cấp hạ tầng quan trọng (Phase 2) như tích hợp CloudFront, sử dụng VPC Endpoints và dịch chuyển CI/CD lên Cloud-Native.
###  [Blog 2 - Nhật Ký Đưa Ứng Dụng Lên Cloud – Từ Bài Học $35 Đến Kiến Trúc Tối Ưu Chi Phí](3.2-Blog2/)
Blog này là phần tiếp theo của loạt bài viết về dự án "Mini Social Network", nơi nhóm phát triển chia sẻ hành trình thực chiến đưa ứng dụng lên môi trường AWS. Bài viết này là quyển nhật ký đúc kết những sai lầm từ tư duy gom chung mọi thứ vào một máy chủ ảo (VPS) ban đầu, cho đến bước ngoặt chuyển đổi tối ưu hóa kiến trúc Cloud Native. Các bạn sẽ được tìm hiểu chi tiết cách từng bộ phận giải quyết bài toán chuyên môn: từ việc hạ tầng cắt giảm chi phí NAT Gateway (từ $35/tháng xuống $0), Frontend xử lý lỗi định tuyến SPA kết hợp CloudFront, đến tích hợp giám sát chủ động và thiết lập DevSecOps ngay từ khâu thiết kế. Qua đó, bài blog mang đến góc nhìn thực tế về việc cân bằng giữa hiệu năng, khả năng tự động hóa và tối ưu chi phí trên Cloud.
###  [Blog 3 - ...](3.3-Blog3/)
Blog này giới thiệu cách bắt đầu xây dựng data lake trong lĩnh vực y tế bằng cách áp dụng kiến trúc microservices. Bạn sẽ tìm hiểu vì sao data lake quan trọng trong việc lưu trữ và phân tích dữ liệu y tế đa dạng (hồ sơ bệnh án điện tử, dữ liệu xét nghiệm, thiết bị IoT y tế…), cách microservices giúp hệ thống linh hoạt, dễ mở rộng và dễ bảo trì hơn. Bài viết cũng hướng dẫn các bước khởi tạo môi trường, tổ chức pipeline xử lý dữ liệu, và đảm bảo tuân thủ các tiêu chuẩn bảo mật & quyền riêng tư như HIPAA.
