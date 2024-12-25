# Báo Cáo Phân Tích Thiết Kế Hệ Thống Phần Mềm

## Mentcare: A Mental Health Support System

### 1. Mô tả tóm tắt bài toán

#### Sự cần thiết và lợi ích khi giải quyết bài toán
Hệ thống Mentcare được thiết kế để hỗ trợ quản lý lâm sàng của bệnh nhân mắc các vấn đề về sức khỏe tâm thần. Sự cần thiết của hệ thống này bắt nguồn từ những vấn đề đặc thù trong việc quản lý và điều trị bệnh nhân tâm thần, bao gồm sự bất thường trong việc tuân thủ lịch hẹn, mất hồ sơ, và sự khó khăn trong việc duy trì thông tin liên lạc nhất quán giữa các cơ sở y tế. Những lợi ích chính khi triển khai hệ thống Mentcare bao gồm:
- **Cải thiện quản lý thông tin:** Hệ thống giúp lưu trữ và quản lý thông tin bệnh nhân một cách hiệu quả, giúp các bác sĩ và nhân viên y tế dễ dàng truy cập và cập nhật thông tin.
- **Nâng cao an toàn:** Cảnh báo và theo dõi bệnh nhân có nguy cơ cao, giúp giảm thiểu rủi ro tự làm hại hoặc gây hại cho người khác.
- **Báo cáo và quản lý:** Cung cấp các báo cáo quản lý và lâm sàng chi tiết để hỗ trợ việc ra quyết định và đánh giá hiệu suất điều trị.
- **Tuân thủ pháp luật:** Đảm bảo các quy trình liên quan đến giam giữ bắt buộc được thực hiện đúng quy định pháp luật.

#### Các yêu cầu chức năng
Hệ thống Mentcare phải đáp ứng các yêu cầu chức năng sau:
1. **Quản lý hồ sơ bệnh nhân:** Tạo, cập nhật và lưu trữ hồ sơ bệnh nhân, bao gồm thông tin cá nhân, lịch sử lâm sàng, chẩn đoán và điều trị.
2. **Giám sát bệnh nhân:** Theo dõi và cảnh báo về tình trạng bệnh nhân, bao gồm những trường hợp bệnh nhân không tuân thủ lịch hẹn hoặc có nguy cơ tự làm hại.
3. **Quản lý giam giữ bắt buộc:** Hỗ trợ quản lý các trường hợp bệnh nhân bị giam giữ bắt buộc, bao gồm theo dõi lịch trình đánh giá và thông báo cho các bên liên quan.
4. **Báo cáo hành chính:** Tạo các báo cáo định kỳ về số lượng bệnh nhân, chẩn đoán, điều trị và các chi phí liên quan.
5. **Tích hợp hệ thống:** Tích hợp với các hệ thống khác như hệ thống thông tin thuốc, hệ thống hồ sơ bệnh nhân quốc gia và hệ thống quản lý lịch hẹn.

#### Các yêu cầu phi chức năng
Các yêu cầu phi chức năng đảm bảo hệ thống hoạt động hiệu quả, an toàn và bảo mật:
1. **Khả năng sẵn sàng:** Hệ thống phải sẵn sàng hoạt động trong giờ làm việc của phòng khám và có lịch trình bảo trì rõ ràng.
2. **Hiệu năng:** Đảm bảo thời gian phản hồi nhanh chóng cho các truy vấn của người dùng, tối đa 2 giây.
3. **Bảo mật:** Áp dụng kiểm soát truy cập dựa trên vai trò, mã hóa dữ liệu và tuân thủ các tiêu chuẩn bảo mật y tế.
4. **Tương thích và tích hợp:** Hệ thống phải tương thích với các phần mềm và phần cứng hiện có của cơ sở y tế, đồng thời hỗ trợ tích hợp với các hệ thống khác.
5. **Usability (Tính dễ sử dụng):** Giao diện người dùng thân thiện, dễ sử dụng, giúp người dùng nhanh chóng làm quen và sử dụng hệ thống hiệu quả.
6. **Tuân thủ pháp luật:** Tuân thủ các quy định của Đạo luật Bảo vệ Dữ liệu và các quy định liên quan đến giam giữ bệnh nhân tâm thần.

## 2. Phân tích các ca sử dụng

### Kiến trúc đề xuất
Hệ thống Mentcare được thiết kế theo kiến trúc client-server, trong đó:
- **Client:** Các máy tính cá nhân của nhân viên y tế tại các phòng khám và bệnh viện sử dụng trình duyệt web (Firefox) để truy cập hệ thống.
- **Server:** Máy chủ trung tâm đặt tại trung tâm dữ liệu của cơ quan y tế khu vực, chạy hệ điều hành Linux và lưu trữ cơ sở dữ liệu bệnh nhân.

### Các cơ chế phân tích
1. **Cơ chế bảo mật và xác thực**
   - **Xác thực đa yếu tố:** Sử dụng hệ thống đăng nhập đa yếu tố với mật khẩu và câu hỏi bảo mật cá nhân.
   - **Kiểm soát truy cập theo vai trò:** Phân quyền truy cập dựa trên vai trò của người dùng (nhân viên lâm sàng, quản trị viên, quản lý hồ sơ y tế).
   - **Mã hóa dữ liệu:** Dữ liệu bệnh nhân được mã hóa cả khi lưu trữ và truyền tải để đảm bảo tính bảo mật.

2. **Cơ chế xử lý và lưu trữ dữ liệu**
   - **Cơ sở dữ liệu quan hệ:** Lưu trữ thông tin bệnh nhân và các dữ liệu liên quan trong cơ sở dữ liệu quan hệ, cho phép truy vấn và cập nhật hiệu quả.
   - **Cơ chế sao lưu:** Hệ thống sao lưu dữ liệu hàng ngày để đảm bảo khả năng khôi phục trong trường hợp xảy ra sự cố.

3. **Cơ chế giám sát và cảnh báo**
   - **Giám sát bệnh nhân:** Theo dõi lịch sử điều trị và tình trạng của bệnh nhân, phát hiện các dấu hiệu bất thường và phát cảnh báo cho nhân viên y tế.
   - **Cảnh báo tự động:** Hệ thống tự động gửi cảnh báo khi phát hiện bệnh nhân có nguy cơ tự làm hại hoặc khi cần thực hiện đánh giá giam giữ bắt buộc.

### Kết quả phân tích từng ca sử dụng

#### Ca sử dụng 1: Quản lý hồ sơ bệnh nhân
**Mô tả:** Nhân viên lâm sàng tạo, cập nhật và lưu trữ hồ sơ bệnh nhân.
**Các bước thực hiện:**
1. Nhân viên lâm sàng đăng nhập vào hệ thống.
2. Tìm kiếm hoặc tạo mới hồ sơ bệnh nhân.
3. Nhập thông tin cá nhân, chẩn đoán, và điều trị vào biểu mẫu.
4. Lưu hồ sơ bệnh nhân vào cơ sở dữ liệu.

#### Ca sử dụng 2: Giám sát bệnh nhân
**Mô tả:** Hệ thống giám sát tình trạng bệnh nhân và phát cảnh báo khi phát hiện bất thường.
**Các bước thực hiện:**
1. Hệ thống tự động kiểm tra lịch sử điều trị và các yếu tố rủi ro của bệnh nhân.
2. Phát hiện tình trạng bất thường (ví dụ: không tuân thủ lịch hẹn, dấu hiệu tự làm hại).
3. Gửi cảnh báo đến nhân viên lâm sàng qua email hoặc thông báo trên hệ thống.

#### Ca sử dụng 3: Quản lý giam giữ bắt buộc
**Mô tả:** Quản lý các trường hợp bệnh nhân bị giam giữ bắt buộc theo quy định của Đạo luật Sức khỏe Tâm thần.
**Các bước thực hiện:**
1. Nhân viên lâm sàng nhập thông tin đánh giá giam giữ vào hệ thống.
2. Hệ thống theo dõi và nhắc nhở về lịch trình đánh giá giam giữ.
3. Gửi thông báo và tài liệu liên quan đến các bên liên quan (bệnh nhân, người thân, quản lý cơ sở giam giữ).

#### Ca sử dụng 4: Báo cáo hành chính
**Mô tả:** Quản trị viên tạo các báo cáo định kỳ về số lượng bệnh nhân, chẩn đoán, điều trị và chi phí.
**Các bước thực hiện:**
1. Quản trị viên đăng nhập vào hệ thống.
2. Chọn loại báo cáo cần tạo (báo cáo quản lý, báo cáo lâm sàng).
3. Hệ thống tự động tạo báo cáo từ cơ sở dữ liệu và lưu trữ hoặc gửi email cho người nhận.

#### Ca sử dụng 5: Tích hợp hệ thống
**Mô tả:** Hệ thống tích hợp với các hệ thống khác như hệ thống thông tin thuốc, hệ thống hồ sơ bệnh nhân quốc gia và hệ thống quản lý lịch hẹn.
**Các bước thực hiện:**
1. Cấu hình tích hợp với các hệ thống ngoại vi.
2. Hệ thống tự động trao đổi dữ liệu với các hệ thống khác theo định kỳ hoặc theo yêu cầu.
3. Đồng bộ hóa thông tin giữa các hệ thống để đảm bảo tính nhất quán và chính xác.

## 3. Xác định các phần tử thiết kế
## 4. Thiết kế hệ thống con
## 5. Thiết kế các lớp
## 6. Kết luận

