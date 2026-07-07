---
title: "Worklog Tuần 8"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8:

* Đẩy mạnh quy trình Kiểm thử Bảo mật Ứng dụng Động (DAST) lên cấp độ chuyên sâu: Kiểm thử có xác thực (Authenticated Scan) và Đánh giá Lỗ hổng Logic.
* Tập trung rà soát và kiểm tra các lỗ hổng Broken Access Control (vượt quyền) hoặc SQLi lọt qua WAF.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| :---: | :--- | :---: | :---: | :--- |
| **2** | **Thực hiện đồ án nhóm:** <br> - Nghiên cứu & Cấu hình OWASP ZAP Nâng cao: <br>&emsp; + Nghiên cứu tính năng Replacer trên OWASP ZAP. <br>&emsp; + Cấu hình ZAP để truyền trực tiếp JWT Token hợp lệ vào Header (`Authorization: Bearer <JWT>`), chuẩn bị cho rà quét có xác thực. | 08/06/2026 | 08/06/2026 | **- Tài liệu OWASP ZAP (Replacer):** <br> https://www.zaproxy.org/docs/ |
| **3** | **Thực hiện đồ án nhóm:** <br> - Kiểm thử Lỗ hổng Vượt quyền (BAC & IDOR): <br>&emsp; + Sử dụng tính năng Manual Request Editor của ZAP. <br>&emsp; + Đóng vai người dùng hợp lệ, cố tình phát lệnh `DELETE` nhắm vào các ID bài viết thuộc về tài khoản của người dùng khác để kiểm tra logic phân quyền tài nguyên. | 09/06/2026 | 09/06/2026 | **- Tài liệu OWASP (BAC):** <br> https://owasp.org/Top10/A01/ <br> **- Tài liệu thực hiện Kiểm thử bảo mật:** <br> https://docs.google.com/document/d/1GEyjB94n11W4QRiCeyGlwQj5SbOsCIgL_go_GqllWzA/edit?usp=sharing|
| **4** | **Thực hiện đồ án nhóm:** <br> - Rà quét Tự động qua lớp Xác thực (Active Scan): <br>&emsp; + Kích hoạt Active Scan nhắm trực tiếp vào nhánh `/api/post/` để fuzzing dữ liệu. <br>&emsp; + Giả lập hành vi tấn công nội bộ, rải thảm các tải trọng (payloads) chứa mã độc SQLi, SSRF/RCE xuyên qua lớp xác thực đầu vào để kiểm tra WAF và Backend. | 10/06/2026 | 10/06/2026 | **- Tài liệu OWASP ZAP (Active Scan):** <br> https://www.zaproxy.org/docs/ |
| **5** | **Thực hiện đồ án nhóm:** <br> - Phân tích Log, Chẩn đoán hệ thống & Lập báo cáo: <br>&emsp; + Đọc hiểu các mã trạng thái HTTP (400, 403, 500) phát sinh trong quá trình kiểm thử để đánh giá cơ chế Xử lý Ngoại lệ (Exception Handling). <br>&emsp; + Khắc phục các xung đột Header và tổng hợp dữ liệu thành Báo cáo DAST Giai đoạn 2. | 11/06/2026 | 11/06/2026 | |
| **6** | **Họp nhóm:** <br> - Báo cáo kết quả tại văn phòng Bootcamp FCAJ : <br>&emsp; + Đóng gói các tệp log xuất ra từ ZAP (CSV) làm bằng chứng PoC. <br>&emsp; + Xây dựng luồng trình bày trực quan (Live Demo) 2 kịch bản ZAP: lỗi BAC và SQLi trước nhóm phát triển tại văn phòng Bootcamp FCAJ. | 12/06/2026 | 12/06/2026 | |


### Kết quả đạt được tuần 8:

* Đã cấu hình thành công ZAP đóng vai trò người dùng hợp lệ thâm nhập qua lớp Authentication.
* Kết quả: Hệ thống Backend (Spring Boot) nhận diện chính xác sự bất hợp lý giữa chủ sở hữu Token và chủ tài nguyên, chặn đứng hành vi xóa dữ liệu trái phép (trả về mã 403 Forbidden), chứng minh logic bảo mật hoạt động hoàn hảo.
* Thiết lập thành công tính năng Replacer tự động gắn Header Authorization để nã đạn qua lớp xác thực.
* Chống SSRF/RCE: Các nỗ lực truy cập siêu dữ liệu đám mây hay chèn lệnh thực thi đều bị AWS WAF và ALB chặn đứng từ xa (403 Forbidden).
* Chống SQL Injection: Các request lọt qua WAF đều bị cơ chế Parameterized Queries của Backend bẻ gãy, từ chối xử lý (trả về 400 Bad Request), hoàn toàn không có tình trạng lọt payload độc hại.

### Minh chứng thực hiện tuần 8:

#### 1. Họp nhóm tại Bootcamp FCAJ

<h4 align="center"><em>Lên văn phòng học tập và làm việc nhóm</em></h4>

![Lên văn phòng học tập và làm việc nhóm](/1206_meeting_w9.JPG)

#### 2. Cấu hình ZAP thực hiện BAC

<h4 align="center"><em>Kiểm tra thông tin để thực hiện BAC</em></h4>

![Kiểm tra thông tin để thực hiện BAC](/preview.png)

#### 3. Cấu hình ZAP thực hiện Header Authorization

<h4 align="center"><em>Cấu hình ZAP gắn Header Authorization</em></h4>

![Cấu hình ZAP gắn Header Authorization](/delete.png)