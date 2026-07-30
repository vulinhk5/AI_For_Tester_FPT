## 1. Jira Rovo AI

| **Mục** | **Chi tiết** |
|----------|--------------|
| **Điểm đã làm** | - Sinh nhanh User Story, Acceptance Criteria và High-Level Test Scenarios<br>- Cấu trúc output rõ ràng, dễ review<br>- Tuân thủ đúng ràng buộc của prompt (không sinh thừa validation ở cấp field)<br>- Văn phong phù hợp với QA |
| **Hạn chế** | - Chất lượng output phụ thuộc nhiều vào prompt; không thể xác minh hành vi thực tế của hệ thống<br>- Không thể xác nhận việc cấu hình quyền Recruiter/Manager có đúng trong ứng dụng thực tế hay không<br>- Không thể truy cập đầy đủ ngữ cảnh UC10 nếu không được cung cấp trong prompt hoặc tài liệu đính kèm; có thể sinh ra diễn đạt mơ hồ (ví dụ: "navigation flow") nếu yêu cầu quá ngắn gọn |
| **Ngoài phạm vi thiết kế** | - Field-level validation<br>- Hành vi Submit<br>- Hành vi Cancel<br>- Trạng thái job mặc định<br>- Hành vi backend/API<br>- Hành vi database |
| **Review yêu cầu** | Bắt buộc QA phải review trước khi sử dụng làm tài liệu chính thức. |

## 2. TestRail AI

| **Mục** | **Chi tiết** |
|---------------|--------------|
| **Điểm đã làm** | - Xử lý tốt các business rule rõ ràng (bắt buộc/tùy chọn, giới hạn số lượng, so sánh min/max).<br>- Tự động suy luận các test case biên mà không cần chỉ định cụ thể (ví dụ: rule `>= hôm nay` → tự sinh thêm case `= hôm nay`).<br>- Tốc độ sinh test case gần như tức thời (28 test cases). |
| **Hạn chế** | - Coverage chưa triệt để (~77%), chỉ bao phủ 10/13 thành phần UI; bỏ qua các thành phần hiển thị tĩnh như label và breadcrumb.<br>- Có nguy cơ hallucination (AI tự "sáng tác" business rule không có trong tài liệu gốc, ví dụ: tự suy luận `Salary To ≥ Salary From`).<br>- Không tự nhận biết được việc sinh trùng lặp test case.<br>- Hard-code dữ liệu test bằng mốc thời gian cũ (ví dụ: năm 2025) thay vì sử dụng biến hoặc năm hiện tại. |
| **Khả năng tùy biến** | - Giao diện (UI) tốt, hỗ trợ nhiều định dạng output (Steps, Plain Text, BDD).<br>- Có tính năng Preview để loại bỏ các test case không mong muốn trước khi import.<br>- Phần xử lý AI (Backend) là hộp đen (black box), không thể can thiệp vào cách AI suy luận và phụ thuộc hoàn toàn vào prompt. |
| **Bảo mật dữ liệu** | - Toàn bộ nội dung yêu cầu được gửi lên máy chủ của TestRail.<br>- Cần anonymize (ẩn danh hóa) dữ liệu trước khi sử dụng với tài liệu dự án thực tế hoặc dữ liệu nhạy cảm. |

## 3. Postbot AI (Postman)

| **Mục** | **Chi tiết** |
|---------------|--------------|
| **Điểm đã làm** | - Sinh test cases cho cả Positive và Negative scenarios.<br>- Hỗ trợ Boundary Value Analysis (khi business rule được cung cấp đầy đủ).<br>- Sinh mã assertion (`pm.test()`).<br>- Sinh JSON Schema validation.<br>- Giải thích ý nghĩa các trường trong API response.<br>- Dễ dàng tùy chỉnh output thông qua prompt. |
| **Hạn chế** | - Không tự hiểu ngữ cảnh nghiệp vụ nếu không được mô tả trong prompt.<br>- Không phát hiện được sự không tương ứng giữa API và yêu cầu nghiệp vụ (ví dụ: sử dụng Login API trong khi yêu cầu là Create Job).<br>- Không thể kiểm thử các trường không tồn tại trong API response (ví dụ: `Job Title`, `Start Date`).<br>- Chất lượng kết quả phụ thuộc nhiều vào prompt. |
| **Hạn chế khác** | - Phiên bản miễn phí giới hạn số lượt sử dụng AI.<br>- Toàn bộ output cần được kiểm tra thủ công trước khi sử dụng hoặc nộp. |

## So sánh tổng quan

| **Chủ đề** | **Rovo** | **TestRail AI** | **Postbot AI** |
|------------|----------|-----------------|----------------|
| **Phụ thuộc chất lượng prompt** | ✅ | ✅ | ✅ |
| **Không thể xác minh hành vi thực tế/runtime** | ✅ | — | ✅ (không kiểm thử được các trường API không trả về) |
| **Nguy cơ nội dung sai lệch/tự sáng tác** | Chỉ diễn đạt mơ hồ | Tự sáng tác business rule (hallucination) | — |
| **Khoảng trống về coverage** | Loại trừ phạm vi rõ ràng | ~77%, bỏ sót UI tĩnh | Bỏ sót trường không có trong API |
| **Phát hiện được input không khớp yêu cầu thực tế** | N/A | N/A | ❌ (không phát hiện Login API và UC10 bị lệch pha) |
| **Có cảnh báo về bảo mật dữ liệu** | Không đề cập | ✅ Có cảnh báo và khuyến nghị anonymize | Không đề cập |
| **Bắt buộc con người review** | ✅ | ✅  | ✅ |

> **Kết luận**
>
> Không công cụ nào có thể tự xác minh hành vi thực tế của hệ thống hoặc tự phát hiện khi input không khớp với yêu cầu nghiệp vụ. Tất cả output do AI sinh ra đều cần được QA đối chiếu với tài liệu UC10 gốc và review trước khi sử dụng chính thức.
