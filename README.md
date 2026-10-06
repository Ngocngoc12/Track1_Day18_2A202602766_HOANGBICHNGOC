# Day 18 — Three Prototypes, One Next Change

## 1. Thông tin cá nhân & đội ngũ

- Họ và tên: **Hoàng Bích Ngọc**
- Mã sinh viên: **2A202602766**
- Tên nhóm: `[Bổ sung tên nhóm]`
- Thành viên: `[Bổ sung đủ 3 thành viên]`
- Case: **AI Tutor — hỗ trợ learner trong quá trình học/làm lab**

## 2. Hypothesis Problem

Khi một lớp học/lab có nhiều learner đang làm bài đồng thời, Instructor/Lab Coach gặp khó khăn trong việc xác định learner nào đang thực sự cần hỗ trợ bởi vì không phải learner nào gặp khó khăn cũng chủ động hỏi hoặc thể hiện rõ vấn đề, dẫn đến một số learner có thể bị phát hiện muộn và phải mắc kẹt lâu hơn trước khi nhận được hỗ trợ.

- Situation: Lớp/lab có nhiều learner đang làm bài cùng lúc.
- User: Instructor/Lab Coach.
- Job: Xác định learner cần hỗ trợ và quyết định ai cần được hỗ trợ trước.
- Barrier: Learner không chủ động hỏi; Instructor không thể quan sát tất cả.
- Consequence: Learner có thể bị mắc kẹt lâu và nhận hỗ trợ muộn.

**Still unproven:** Chưa biết tín hiệu hệ thống/AI có giúp tìm đúng learner cần hỗ trợ mà không tạo quá nhiều cảnh báo sai hay không.

## 3. Three Solution Options

- **Option A — Learner-led:** Learner tự gửi yêu cầu; Instructor review request.
- **Option B — AI detects + Learner confirms:** AI phát hiện tín hiệu, hỏi learner xác nhận rồi mới chuyển request cho Instructor.
- **Option C — AI-initiated Support Queue:** AI tạo candidate từ tín hiệu hành vi; Instructor xem evidence, confidence và quyết định hỗ trợ, theo dõi hoặc dismiss.

Prototype hiện có: [mở prototype HTML](./vlearn_support_queue_guided_prototype.html). File hiện thể hiện rõ nhất cơ chế Option C và learner self-support flow; A/B vẫn cần được bổ sung thành các màn hình điều hướng riêng trước khi tuyên bố đã có đủ A/B/C test-ready.

## 4. Đóng góp cụ thể của tôi

Tôi chịu trách nhiệm chuẩn bị prototype HTML cho luồng Support Queue, gồm giao diện Instructor/Lab Coach, danh sách learner, evidence timeline, confidence, các lựa chọn hỗ trợ/theo dõi/dismiss và reset prototype. Tôi tham gia xây dựng Comparison Contract, Data Fixture và Human–AI Decision Table. Các thông tin về phân công nhóm và đóng góp của thành viên khác cần được nhóm bổ sung/xác nhận.

## 5. Dữ liệu kiểm thử & bài học

`prototype-feedback-note.md` hiện là biểu mẫu chờ điền sau phiên test do tôi điều phối. Chưa đưa feedback, quote hoặc kết luận giả vào README.

`group-feedback-synthesis.md` là biểu mẫu tổng hợp chờ đủ 3 Feedback Notes. Chỉ chốt **một Next Change** sau khi có dữ liệu thật.

## 6. AI Support Log

AI được sử dụng để hỗ trợ cấu trúc tài liệu, rà soát yêu cầu Day 18 và hỗ trợ chuẩn hóa nội dung prototype. Tôi phải tự kiểm tra lại nội dung, đặc biệt là ranh giới Human–AI, Evidence, Confidence, Dismiss và Reset. AI không được dùng để tạo quote, hành vi quan sát hoặc kết quả tester giả. Chi tiết xem [`ai-support-log.md`](./ai-support-log.md).

## Quality Gates checklist

- [x] Evidence Continuity: có Hypothesis Problem và Still Unproven.
- [x] Meaningful Options: A/B/C khác nhau về cơ chế và mức độ tự trị.
- [x] Human Control: Option C có evidence, confidence và quyết định của Instructor.
- [ ] Test-ready: cần hoàn thiện luồng A/B/C riêng và test với người ngoài nhóm.
- [ ] Learning, Not Praise: cần bổ sung 3 Feedback Notes thật và một Next Change dựa trên pattern.

## Pre-flight

- [ ] Bổ sung tên nhóm và đủ 3 thành viên.
- [ ] Kiểm tra prototype A/B/C đều mở được.
- [ ] Test với 3 người ngoài nhóm.
- [ ] Điền Feedback Note cá nhân bằng dữ liệu thật.
- [ ] Tổng hợp nhóm và chốt đúng một Next Change.
- [ ] Cập nhật AI Support Log theo đóng góp thực tế.
