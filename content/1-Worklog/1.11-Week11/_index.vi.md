---
title: "Worklog Tuần 11"
date: 2026-06-29
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11:

* Xử lý các cảnh báo giả (false positives) trên AWS WAF Console.
* Tinh chỉnh Scope-Down Statement cho chức năng Rate Limiting.
* Kiểm tra luồng 1 với Rule Action = "Count" cho người dùng thông thường.
* Kiểm tra luồng 2 với Rule Action = "Block" cho lưu lượng DDoS/API được mô phỏng bằng K6.
* Thực hiện kiểm tra chéo và hoàn thiện Hugo Server cùng báo cáo thực tập.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --------- | ------------ | --------------- | -------------- |
|**2** | **Thực hiện đồ án nhóm:** <br> - Xem xét các cảnh báo giả trên AWS WAF Console <br> - Phân biệt lưu lượng hợp lệ với yêu cầu đáng ngờ <br> - Điều chỉnh logic rule và chuẩn bị phương án tối ưu ban đầu | 29/06/2026 | 29/06/2026 |  |
| **3** | **Thực hiện đồ án nhóm:** <br> - Tinh chỉnh Scope-Down Statement cho Rate Limiting <br> - Thêm điều kiện để giảm tình trạng chặn nhầm luồng người dùng bình thường <br> - Ghi nhận logic tối ưu và hành vi kỳ vọng | 30/06/2026 | 30/06/2026 | |
| **4** | **Thực hiện đồ án nhóm:** <br> - Chuyển Rule Action sang "Count" <br> - Chạy bài test bằng K6 cho luồng 1 (người dùng thường) <br> - Quan sát hành vi request, log WAF và các cảnh báo mà không chặn lưu lượng | 01/07/2026 | 01/07/2026 | |
| **5** | **Thực hiện đồ án nhóm:** <br> - Chuyển Rule Action sang "Block" <br> - Chạy bài test bằng K6 cho luồng 2 (mô phỏng DDoS/API attack) <br> - Kiểm tra lưu lượng độc hại được chặn hiệu quả và logic bảo vệ vẫn hoạt động | 02/07/2026 | 02/07/2026 | |
| **6** | **Họp nhóm:** <br> - Thực hiện kiểm tra chéo với thành viên nhóm <br> - Hoàn thiện nội dung trên Hugo Server và đảm bảo báo cáo thống nhất <br> - Hoàn tất báo cáo thực tập và tài liệu liên quan | 03/07/2026 | 03/07/2026 | |


### Kết quả đạt được tuần 11:

* Hoàn thiện tinh chỉnh Scope-Down Statement cho Rate Limiting để giảm khả năng chặn nhầm lưu lượng người dùng hợp lệ.**

* Hoàn thiện kiểm tra ở chế độ "Count" cho luồng 1 và xác nhận logic giám sát hoạt động đúng với lưu lượng người dùng thường.**

* Hoàn thiện kiểm tra ở chế độ "Block" cho luồng 2 bằng K6 và xác nhận lưu lượng DDoS/API bị chặn hiệu quả.**

### Minh chứng thực hiện tuần 11:

#### 1. Tinh chỉnh Rule Block-DDoS-Login để giảm khả năng chặn nhầm

<h4 align="center"><em>Thực hiện thiết lập Web ACL với 4 Rule trên ALB cho hệ thống</em></h4>

![Thực hiện thiết lập Web ACL với 4 Rule Group trên ALB cho hệ thống](/images/1-Worklog/1.11-Week11/ruleset.png)

<h4 align="center"><em>Cấu hình thông số Rate-Limit để chống DDOS</em></h4>

![Cấu hình thông số Rate-Limit để chống DDOS](/images/1-Worklog/1.11-Week11/config1.png)

![Cấu hình thông số Rate-Limit để chống DDOS](/images/1-Worklog/1.11-Week11/config2.png)

#### 2. Kết quả kiểm thử luồng 1 bằng K6

<h4 align="center"><em>Dashboard hiển thị WAF cho phép luồng hợp lệ vào hệ thống</em></h4>

![Dashboard hiển thị WAF cho phép luồng hợp lệ vào hệ thống](/images/1-Worklog/1.11-Week11/k6_flow1.png)

![Dashboard hiển thị WAF cho phép luồng hợp lệ vào hệ thống](/images/1-Worklog/1.11-Week11/k6_flow1_1.png)

#### 3. Kết quả kiểm thử luồng 2 bằng K6

<h4 align="center"><em>Dashboard hiển thị WAF chặn tấn công DDoS hệ thống</em></h4>

![Dashboard hiển thị WAF chặn tấn công DDoS hệ thống](/images/1-Worklog/1.11-Week11/k6_flow2.png)

![Dashboard hiển thị WAF chặn tấn công DDoS hệ thống](/images/1-Worklog/1.11-Week11/k6_flow2_1.png)

#### 4. Họp nhóm trao đổi thông tin 

<h4 align="center"><em>Họp nhóm trao đổi nhiệm vụ đã thực hiện</em></h4>

![Họp nhóm trao đổi nhiệm vụ đã thực hiện](/images/1-Worklog/1.11-Week11/307_meeting_w11.JPG)
