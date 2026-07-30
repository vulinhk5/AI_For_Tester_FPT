| Tiêu chí | Jira Rovo AI | TestRail AI | Postman Postbot AI |
|----------|--------------|-------------|--------------------|
| **Mục tiêu** | Sinh User Story, Acceptance Criteria và Test Scenario | Sinh Test Case từ Requirement | Sinh API Test Script và Assertions |
| **Thời gian thực hiện thủ công** | 15 phút | 70–90 phút | 120 phút |
| **Thời gian AI tạo kết quả** | 2 phút | Gần như ngay lập tức | 25 phút |
| **Thời gian QA Review** | 5 phút | 20–30 phút | Cần QA kiểm tra thủ công |
| **Tổng thời gian sử dụng AI** | 7 phút | 25–40 phút | 25 phút |
| **Thời gian tiết kiệm** | 8 phút (53,3%) | Khoảng 45–55 phút (60–65%) | Khoảng 95 phút (~79%) |
| **Hiệu quả (ROI)** | ROI ≈ 114,3% | Tiết kiệm khoảng 60–65% thời gian | Tăng năng suất đáng kể so với làm thủ công |
| **AI làm được** | Sinh User Story, Acceptance Criteria và Test Scenario đúng phạm vi yêu cầu | Sinh Test Case bao phủ tốt các trường hợp Required, Validation, Min/Max và Date Validation | Sinh API Test Script, Assertions, JSON Schema Validation và Boundary Tests |
| **Hạn chế** | Vẫn cần QA kiểm tra trước khi sử dụng | Có thể bỏ sót Test Case, sinh Test Case trùng lặp, tự suy luận Business Rule không tồn tại và sử dụng dữ liệu lỗi thời | Không hiểu Business Rule đặc thù, vẫn cần QA xác minh kết quả |
| **Hallucination** | 0% | Có (Business Rule tự suy luận và Test Case trùng lặp) | Không nêu tỷ lệ cụ thể; vẫn cần QA đối chiếu yêu cầu |
| **Khả năng tùy chỉnh** | Không đề cập | **UI:** Hỗ trợ nhiều định dạng đầu ra (Steps, Text, BDD) và Preview để chọn/lọc Test Case trước khi import.<br>**Backend:** Không thể can thiệp vào model hoặc cách AI suy luận; chất lượng phụ thuộc vào Prompt. | **Tốt:** Có khả năng tùy chỉnh theo Prompt khá linh hoạt. Chất lượng và độ chính xác của Test Script phụ thuộc nhiều vào mức độ rõ ràng, đầy đủ và chi tiết của Prompt do người dùng cung cấp. |
| **Bảo mật dữ liệu** | Không đề cập | Toàn bộ Requirement/Use Case được gửi lên server của TestRail để xử lý. Với dữ liệu nhạy cảm cần **ẩn danh hóa (Anonymize)** trước khi sử dụng để tuân thủ chính sách bảo mật. | AI xử lý Username, Password, JWT Token và Refresh Token. Prompt được xử lý trên dịch vụ cloud. Chỉ sử dụng ThingsBoard Demo API nên mức rủi ro thấp và không có dữ liệu production bị lộ. |
| **Kết luận** | Giảm hơn 50% thời gian tạo tài liệu QA, chất lượng tốt sau khi QA review | Tiết kiệm nhiều thời gian nhưng bắt buộc phải QA review do AI có thể bỏ sót hoặc tự suy luận nghiệp vụ | Rất phù hợp để tăng tốc API Testing nhưng không thể thay thế QA trong việc xác minh Business Rule |


