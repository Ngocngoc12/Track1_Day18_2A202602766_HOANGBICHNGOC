# Three-option design sheet

## Evidence Snapshot

Các dữ kiện kế thừa từ Day 17: learner có thể gặp khó khăn nhưng không biết nên hỏi gì; Instructor đôi khi phải suy đoán từ dấu hiệu bên ngoài; lớp đông khiến Instructor không thể quan sát toàn bộ learner; một số learner tự giải quyết bằng AI, tài liệu hoặc hỏi Lab Coach.

> Khi nộp chính thức, thay phần mô tả này bằng Raw Fact và câu nói/hành vi thật từ 3 Practice Notes Day 17. Không tự tạo quote.

## Hypothesis Problem

Khi một lớp học/lab có nhiều learner đang làm bài đồng thời, Instructor/Lab Coach gặp khó khăn trong việc xác định learner nào đang thực sự cần hỗ trợ bởi vì không phải learner nào gặp khó khăn cũng chủ động hỏi hoặc thể hiện rõ vấn đề, dẫn đến một số learner có thể bị phát hiện muộn và phải mắc kẹt lâu hơn trước khi nhận được hỗ trợ.

## 70% Invariants

- Target User: Instructor/Lab Coach.
- Situation: Lớp lab đông, learner làm bài đồng thời.
- Task: Chọn một learner cần review tiếp theo.
- Desired outcome: Chọn được learner và hiểu lý do xuất hiện.
- Content fixture: Cùng lớp, learner, tiến độ và dữ liệu hành vi.
- UI: Cùng layout, dữ liệu mẫu và task.

## Data Fixture

| Learner | Tiến độ | Lần thử | Thời gian | Yêu cầu hỗ trợ | Tín hiệu |
|---|---:|---:|---:|---|---|
| Lan | 78% | 2 | 4 phút | Có | Mô tả lỗi JOIN |
| Minh | 62% | 4 | 13 phút | Không | Xem hint 3 lần |
| Huy | 55% | 5 | 16 phút | Không | Lặp lại cùng lỗi |
| Mai | 72% | 2 | 7 phút | Không | Mở tài liệu |
| An | 92% | 1 | 2 phút | Không | Không bất thường |

Đây là canned fixture cho prototype, không phải dữ liệu nghiên cứu thật.

## 30% Variables

| Tiêu chí | A | B | C |
|---|---|---|---|
| Cơ chế | Learner tự yêu cầu | AI phát hiện, learner xác nhận | AI tạo candidate, Instructor review |
| Quyền khởi tạo | Learner | AI đề xuất, learner checkpoint | AI đề xuất |
| Quyền cuối cùng | Instructor xử lý request | Instructor xử lý request đã xác nhận | Instructor giữ/bỏ flag và quyết định hỗ trợ |
| Trade-off | Kiểm soát cao, dễ bỏ sót | Cân bằng nhưng phụ thuộc phản hồi | Phát hiện sớm, nguy cơ false positive |

## Human–AI Decision Table

| Trụ cột | Option A | Option B | Option C |
|---|---|---|---|
| Expectation | Chỉ có request learner gửi | AI chỉ chuyển sau khi learner xác nhận | AI tạo gợi ý, không phải kết luận |
| Role & Agency | AI không tự đánh giá | AI hỏi learner | AI act + Instructor review |
| Evidence | Nội dung learner mô tả | Tín hiệu + confirmed | Tín hiệu + reason + confidence |
| Control & Recovery | Open/Skip | Review/Dismiss | Support/Watch/Not needed, Back/Reset |

## Cost of Failure

- A: learner im lặng không xuất hiện.
- B: learner bỏ qua hoặc không xác nhận.
- C: false positive làm queue quá tải; vì vậy phải hiển thị evidence, confidence và quyền dismiss.

## Prototype status

File `vlearn_support_queue_guided_prototype.html` hiện triển khai chi tiết nhất cho Option C và có learner flow. Cần bổ sung/điều hướng rõ hai critical interaction của A và B trước phiên test so sánh trọn bộ A/B/C.
