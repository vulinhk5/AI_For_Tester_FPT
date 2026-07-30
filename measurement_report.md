| Tiêu chí | Jira Rovo AI | TestRail AI | Postman Postbot AI |
|----------|--------------|-------------|--------------------|
| **Mục tiêu** | Sinh User Story, Acceptance Criteria và Test Scenario | Sinh Test Case từ Requirement | Sinh API Test Script và Assertions |
| **Thời gian thực hiện thủ công** | 15 phút | 70–90 phút | 120 phút |
| **Thời gian AI tạo kết quả** | 2 phút | Gần như ngay lập tức | 25 phút |
| **Thời gian QA Review** | 5 phút | 20–30 phút | Cần QA kiểm tra thủ công |
| **Tổng thời gian sử dụng AI** | 7 phút | 25–40 phút | 25 phút |
| **Thời gian tiết kiệm** | 8 phút (53,3%) | Khoảng 45–55 phút (60–65%) | Khoảng 95 phút (~79%) |
| **Hiệu quả (ROI)** | ROI ≈ 114,3% | Tiết kiệm khoảng 60–65% thời gian | Tăng năng suất đáng kể so với làm thủ công |
| **AI làm được** | Sinh User Story, Acceptance Criteria và Test Scenario đúng phạm vi yêu cầu | Sinh 28 Test Case với các kiểm tra Required, Validation, Min/Max | Sinh API Test, Assertions, JSON Schema Validation và Boundary Tests |
| **Hạn chế** | Vẫn cần QA kiểm tra trước khi sử dụng | Thiếu khoảng 25% Test Case, có Test Case trùng, tự suy luận Business Rule không tồn tại, dữ liệu ngày tháng lỗi thời | Không hiểu Business Rule đặc thù, vẫn cần QA xác minh kết quả |
| **Hallucination** | 0% | Có (1 Business Rule tự suy luận và một số Test Case trùng lặp) | Không nêu tỷ lệ cụ thể, vẫn cần QA đối chiếu yêu cầu |
| **Khả năng tùy chỉnh** | Không đề cập | Trung bình, hỗ trợ chọn Template và Preview trước khi tạo | Không đề cập |
| **Kết luận** | Giảm hơn 50% thời gian tạo tài liệu QA, chất lượng tốt sau khi QA review | Tiết kiệm nhiều thời gian nhưng bắt buộc phải QA review | Rất phù hợp để tăng tốc API Testing nhưng không thể thay thế QA |


