| **Mục** | **Chi tiết** |
|----------|--------------|
| **Điểm mạnh** | - Sinh nhanh User Story, Acceptance Criteria và High-Level Test Scenarios<br>- Cấu trúc output rõ ràng, dễ review<br>- Tuân thủ đúng ràng buộc của prompt (không sinh thừa validation ở cấp field)<br>- Văn phong phù hợp với QA |
| **Hạn chế** | - Chất lượng output phụ thuộc nhiều vào prompt; không thể xác minh hành vi thực tế của hệ thống<br>- Không thể xác nhận việc cấu hình quyền Recruiter/Manager có đúng trong ứng dụng thực tế hay không<br>- Không thể truy cập đầy đủ ngữ cảnh UC10 nếu không được cung cấp trong prompt hoặc tài liệu đính kèm; có thể sinh ra diễn đạt mơ hồ (ví dụ: "navigation flow") nếu yêu cầu quá ngắn gọn |
| **Ngoài phạm vi thiết kế** | - Field-level validation<br>- Hành vi Submit<br>- Hành vi Cancel<br>- Trạng thái job mặc định<br>- Hành vi backend/API<br>- Hành vi database |
| **Review yêu cầu** | Bắt buộc QA phải review trước khi sử dụng làm tài liệu chính thức. |
