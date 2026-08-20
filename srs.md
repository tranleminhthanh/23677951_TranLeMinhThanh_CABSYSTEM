
Bước 1 : đọc và phân tích yêu cầu sơ khảo của khách hàng ở giai đoạn 1 

Đúng. Với **Bước 1: Đọc và phân tích yêu cầu sơ khởi của khách hàng ở giai đoạn 1**, bạn chưa cần đi sâu vào Use Case hay thiết kế hệ thống. Mục tiêu là **đọc tình huống → bóc tách những gì khách hàng đang yêu cầu → xác định phạm vi ban đầu và những điểm cần làm rõ**.

Bạn có thể phân tích như sau:

### 1. Xác định bài toán / vấn đề hiện tại

Công ty ABC đang cung cấp dịch vụ đặt xe trực tuyến nhưng hệ thống hiện tại có các hạn chế:

* Phân công tài xế còn **thủ công**.
* Khách hàng **khó theo dõi trạng thái chuyến đi**.
* Thông tin **thanh toán chưa được quản lý tập trung**.
* Bộ phận vận hành gặp khó khăn khi **mở rộng hệ thống**.
* Hệ thống hiện tại chưa đáp ứng tốt khi số lượng khách hàng và tài xế tăng.

→ **Vấn đề kinh doanh:** ABC cần một nền tảng đặt xe mới có khả năng tự động hóa quy trình, phục vụ số lượng lớn người dùng và dễ mở rộng trong tương lai.

---

### 2. Xác định mục tiêu của hệ thống mới

Từ yêu cầu khách hàng, mục tiêu chính của CAB System là:

> Xây dựng nền tảng đặt xe trực tuyến hỗ trợ toàn bộ quy trình từ **đặt xe → tìm tài xế → thực hiện chuyến → tính cước → thanh toán → đánh giá**, đồng thời hỗ trợ quản lý vận hành và có kiến trúc linh hoạt để mở rộng.

Có thể chia thành các mục tiêu nhỏ:

| Mục tiêu               | Ý nghĩa                                  |
| ---------------------- | ---------------------------------------- |
| Đặt xe trực tuyến      | Khách hàng chủ động tạo yêu cầu          |
| Tự động tìm tài xế     | Giảm việc phân công thủ công             |
| Theo dõi chuyến đi     | Khách hàng biết trạng thái chuyến        |
| Quản lý tài xế         | Theo dõi trạng thái, phương tiện, vị trí |
| Tính cước & thanh toán | Quản lý số tiền và giao dịch             |
| Thông báo              | Cập nhật các sự kiện quan trọng          |
| Quản trị vận hành      | Nhân viên theo dõi và xử lý chuyến       |
| Báo cáo                | Theo dõi doanh thu, chuyến, hiệu quả     |
| Bảo mật                | Bảo vệ dữ liệu và kiểm soát quyền        |
| Khả năng mở rộng       | Dễ thêm dịch vụ, thanh toán, thông báo   |

---

### 3. Xác định các tác nhân chính

Khách hàng đã nêu rõ **3 nhóm người dùng chính**:

**1. Khách hàng**

* Đăng ký / đăng nhập
* Cập nhật thông tin
* Đặt xe
* Theo dõi chuyến
* Xem lịch sử
* Thanh toán
* Đánh giá tài xế

**2. Tài xế**

* Đăng ký hoặc được tạo tài khoản
* Cập nhật hồ sơ, phương tiện
* Bật trạng thái sẵn sàng
* Nhận thông báo chuyến
* Chấp nhận / từ chối chuyến
* Cập nhật trạng thái chuyến
* Cung cấp vị trí

**3. Nhân viên vận hành**

* Quản lý khách hàng
* Quản lý tài xế
* Quản lý phương tiện
* Theo dõi chuyến
* Xử lý chuyến lỗi
* Tra cứu giao dịch
* Xem báo cáo
* Thực hiện các thao tác theo quyền được cấp

Ngoài ra còn có **các hệ thống bên ngoài** cần chú ý:

* **Nhà cung cấp thanh toán bên ngoài**
* **Nhà cung cấp dịch vụ thông báo** có thể được tích hợp
* Có thể có các dịch vụ bản đồ/vị trí nếu hệ thống sử dụng để xác định khoảng cách và vị trí tài xế.

---

### 4. Xác định quy trình nghiệp vụ tổng quát

Đọc toàn bộ yêu cầu, có thể sơ bộ nhận ra quy trình chính:

**Khách hàng tạo yêu cầu đặt xe**

↓

**Hệ thống tìm tài xế phù hợp**

↓

**Tài xế nhận / từ chối chuyến**

↓

Nếu từ chối → **hệ thống tìm tài xế khác**

↓

Nếu nhận → **thông báo cho khách hàng**

↓

**Tài xế đến điểm đón**

↓

**Đón khách**

↓

**Thực hiện chuyến**

↓

**Hoàn thành chuyến**

↓

**Hệ thống tính cước**

↓

**Khách hàng thanh toán**

↓

**Đánh giá tài xế**

Đây mới là **quy trình sơ bộ**, chưa phải quy trình nghiệp vụ hoàn chỉnh vì còn nhiều quy tắc chưa được khách hàng xác định.

---

### 5. Xác định các yêu cầu chức năng sơ bộ

Từ tình huống, có thể gom thành các nhóm:

**Quản lý tài khoản**

* Đăng ký
* Đăng nhập
* Cập nhật thông tin cá nhân
* Xác thực người dùng

**Đặt xe**

* Nhập điểm đón
* Nhập điểm đến
* Chọn loại xe
* Gửi yêu cầu đặt xe

**Tìm và phân công tài xế**

* Xác định tài xế phù hợp
* Ưu tiên tài xế gần khách hàng
* Gửi yêu cầu cho tài xế
* Xử lý tài xế từ chối / không phản hồi
* Tìm tài xế tiếp theo

**Quản lý chuyến đi**

* Theo dõi trạng thái
* Cập nhật trạng thái chuyến
* Theo dõi vị trí tài xế
* Xử lý chuyến bị lỗi
* Hủy chuyến

**Tính cước & thanh toán**

* Tính số tiền phải trả
* Thanh toán tiền mặt
* Thanh toán điện tử
* Kết nối nhà cung cấp thanh toán
* Xử lý thanh toán thất bại
* Tra cứu giao dịch

**Thông báo**

* Thông báo tiếp nhận yêu cầu
* Thông báo tài xế nhận chuyến
* Thông báo tài xế đến
* Thông báo hoàn thành
* Thông báo kết quả thanh toán

**Đánh giá**

* Khách hàng đánh giá tài xế sau chuyến

**Quản trị**

* Quản lý khách hàng
* Quản lý tài xế
* Quản lý phương tiện
* Quản lý chuyến đi
* Phân quyền nhân viên
* Báo cáo

---

### 6. Xác định yêu cầu phi chức năng

Đây là phần **rất quan trọng** trong đề bài vì khách hàng nói khá nhiều về nó.

Có thể phân loại:

| Nhóm                       | Yêu cầu                                                      |
| -------------------------- | ------------------------------------------------------------ |
| Hiệu năng                  | Hoạt động ổn định khi nhu cầu tăng cao                       |
| Khả năng mở rộng           | Có thể mở rộng độc lập các thành phần                        |
| Độ tin cậy                 | Lỗi thanh toán/thông báo không làm toàn hệ thống dừng        |
| Bảo mật                    | Bảo vệ thông tin cá nhân, vị trí, giao dịch                  |
| Phân quyền                 | Kiểm soát thao tác của nhân viên                             |
| Audit                      | Lưu vết các thao tác quan trọng                              |
| Khả năng bảo trì           | Có thể thay đổi/thêm thành phần kỹ thuật                     |
| Khả năng mở rộng chức năng | Thêm dịch vụ, phương thức thanh toán, nhà cung cấp thông báo |

---

### 7. Xác định các quy tắc nghiệp vụ đã biết

Ví dụ:

* Chỉ người dùng đã được **xác thực** mới sử dụng chức năng yêu cầu tài khoản.
* Tài xế phải ở trạng thái **sẵn sàng** mới có thể nhận chuyến.
* Tài xế được lựa chọn dựa trên **vị trí, trạng thái và tiêu chí vận hành**.
* Nếu tài xế từ chối hoặc không phản hồi → hệ thống **tiếp tục tìm tài xế khác**.
* Nếu không tìm được tài xế → **thông báo cho khách hàng**.
* Sau khi chuyến hoàn thành → hệ thống **tính cước**.
* Khách hàng có thể thanh toán bằng **tiền mặt hoặc điện tử**.
* Thông tin nhạy cảm của phương thức thanh toán **không được lưu trực tiếp trong CAB**.
* Thao tác quản trị phải được **kiểm soát quyền truy cập**.

---

### 8. Quan trọng nhất: xác định những điểm CHƯA RÕ

Đây chính là phần BA cần làm ở bước tiếp theo.

Khách hàng **chưa xác định**:

1. **Cách tính cước** như thế nào?

   * Theo km?
   * Theo thời gian?
   * Theo loại xe?
   * Có phụ phí không?

2. **Tiêu chí ưu tiên tài xế**?

   * Gần nhất?
   * Thời gian chờ?
   * Đánh giá?
   * Loại xe?

3. **Tài xế phải phản hồi trong bao lâu?**

4. **Chính sách hủy chuyến**?

   * Ai được hủy?
   * Hủy trước/sau khi tài xế đến có khác nhau không?
   * Có phí hủy không?

5. **Mất kết nối mạng xử lý thế nào?**

6. **Lưu trữ dữ liệu trong bao lâu?**

7. **Thanh toán thất bại** thì cho phép thử lại bao nhiêu lần và trong thời gian nào?

8. **Quyền của từng loại nhân viên vận hành** cụ thể ra sao?

9. **Các loại xe/dịch vụ** hiện tại và tương lai gồm những gì?

10. **Nhà cung cấp thanh toán và thông báo** nào sẽ được sử dụng?

---

## Kết luận của Bước 1

Bạn có thể hiểu ngắn gọn Bước 1 theo công thức:

> **Yêu cầu khách hàng → Vấn đề → Mục tiêu → Actor → Quy trình → Chức năng → Phi chức năng → Business Rules → Điểm chưa rõ**

Và **chưa nên nhảy ngay sang thiết kế database, giao diện hay kiến trúc hệ thống**.

Đặc biệt, trong bài CAB này, BA phải chú ý rằng khách hàng **cố tình để một số yêu cầu chưa rõ**. Vì vậy, việc phát hiện ra các câu như **“cách tính cước chưa chốt”, “tiêu chí ưu tiên tài xế chưa chốt”, “chính sách hủy chưa chốt”** chính là kết quả quan trọng của giai đoạn phân tích sơ khởi.
Bước 2 : xác định các stake holder , lập bảng gồm 2 cột cột thứ nhất tên stake holder cột thứ hai là vai trò 
lập vẽ ma trận stake holder matric -> cho biết tầm quan trọng của vai trò stake holder trong hệ thống 
vẽ ma trận dùng công cụ mermaid dùng để vẽ các sơ đồ lược đồ markdown


Được. Với Bước 2, từ yêu cầu CAB System bạn đưa, ta cần xác định Stakeholder → vai trò → mức độ quan trọng.

1. Bảng Stakeholder và vai trò
Stakeholder	Vai trò
Khách hàng	Người sử dụng hệ thống để đăng ký, đặt xe, theo dõi chuyến, thanh toán và đánh giá tài xế.
Tài xế	Nhận và thực hiện chuyến xe, cập nhật trạng thái chuyến, trạng thái hoạt động và vị trí.
Nhân viên vận hành	Theo dõi chuyến đi, quản lý khách hàng, tài xế, phương tiện và hỗ trợ xử lý các trường hợp phát sinh.
Quản lý / Ban giám đốc	Đưa ra yêu cầu, định hướng phát triển hệ thống, theo dõi báo cáo, doanh thu và hiệu quả hoạt động.
Nhân viên quản trị hệ thống	Quản lý tài khoản, phân quyền và các thao tác quản trị hệ thống.
Nhà cung cấp dịch vụ thanh toán	Xử lý các giao dịch thanh toán điện tử bên ngoài hệ thống CAB.
Nhà cung cấp dịch vụ thông báo	Cung cấp kênh gửi thông báo đến khách hàng và tài xế.
Business Analyst	Thu thập, phân tích, làm rõ và đặc tả yêu cầu giữa khách hàng và đội phát triển.
Đội phát triển hệ thống	Phân tích kỹ thuật, xây dựng, kiểm thử và triển khai hệ thống CAB.
Lưu ý

Nếu giảng viên yêu cầu Stakeholder của hệ thống, không nhất thiết phải đưa BA và đội phát triển vào ma trận mức độ quan trọng của người sử dụng/nghiệp vụ. Nhưng nếu đề yêu cầu xác định tất cả các bên liên quan đến dự án, thì nên đưa vào.

Để ma trận dễ hiểu, mình đề xuất tập trung vào 8 stakeholder có tác động trực tiếp đến hệ thống:

Khách hàng
Tài xế
Nhân viên vận hành
Quản lý/Ban giám đốc
Quản trị hệ thống
Nhà cung cấp thanh toán
Nhà cung cấp thông báo
Đội phát triển hệ thống
2. Stakeholder Matrix

Ma trận thường sử dụng 2 tiêu chí:

Mức độ quyền lực / ảnh hưởng (Power)
Mức độ quan tâm (Interest)

Từ đó chia thành 4 nhóm:

	Quan tâm thấp	Quan tâm cao
Ảnh hưởng cao	Keep Satisfied – Duy trì hài lòng	Manage Closely – Quản lý chặt chẽ
Ảnh hưởng thấp	Monitor – Theo dõi	Keep Informed – Cập nhật thông tin

Với CAB System, có thể phân loại như sau:

🔴 Manage Closely – Ảnh hưởng cao, quan tâm cao

Quản lý / Ban giám đốc

Quyết định mục tiêu, phạm vi và định hướng hệ thống.
Có quyền quyết định cao.

Nhân viên vận hành

Sử dụng hệ thống thường xuyên.
Trực tiếp vận hành và xử lý sự cố chuyến.

Khách hàng

Là người sử dụng chính.
Nhu cầu của khách hàng ảnh hưởng trực tiếp đến các chức năng đặt xe.

Tài xế

Là người sử dụng chính.
Quy trình tìm và phân công tài xế phụ thuộc trực tiếp vào tài xế.

→ Đây là 4 stakeholder quan trọng nhất cần BA trao đổi thường xuyên.

🟡 Keep Satisfied – Ảnh hưởng cao, quan tâm thấp

Nhà cung cấp thanh toán

Có ảnh hưởng lớn đến chức năng thanh toán nhưng không trực tiếp sử dụng toàn bộ CAB System.

🟢 Keep Informed – Ảnh hưởng thấp, quan tâm cao

Quản trị hệ thống

Quan tâm đến việc quản lý tài khoản, quyền và vận hành kỹ thuật nhưng quyền quyết định nghiệp vụ thấp hơn Ban giám đốc.

Đội phát triển hệ thống

Quan tâm cao đến yêu cầu và hoạt động hệ thống nhưng không phải bên quyết định nghiệp vụ cuối cùng.

⚪ Monitor – Ảnh hưởng thấp, quan tâm thấp

Nhà cung cấp thông báo

Ở giai đoạn hiện tại chỉ cung cấp dịch vụ tích hợp thông báo, mức độ ảnh hưởng đến nghiệp vụ tổng thể thấp hơn các stakeholder chính.

Tuy nhiên, đây là phân loại sơ bộ. Sau khi phỏng vấn các bên liên quan, BA có thể điều chỉnh vị trí stakeholder.

3. Ma trận Stakeholder Matrix bằng Mermaid

Bạn có thể copy đoạn dưới đây vào nơi hỗ trợ Mermaid:


Cách đọc ma trận
                    MỨC ĐỘ ẢNH HƯỞNG
                           CAO
                            ↑
             │             │
 Keep         │ Manage      │
 Satisfied    │ Closely     │
              │             │
              │             │
──────────────┼─────────────┼──────────→ QUAN TÂM
              │             │
 Monitor      │ Keep        │
              │ Informed    │
              │             │
                           THẤP

Trong đó:

Manage Closely
→ Khách hàng, Tài xế, Nhân viên vận hành, Ban giám đốc.

Keep Satisfied
→ Nhà cung cấp thanh toán.

Keep Informed
→ Quản trị hệ thống, Đội phát triển.

Monitor
→ Nhà cung cấp thông báo.

4. Ý nghĩa của ma trận đối với BA

Điểm quan trọng của ma trận không chỉ là vẽ cho đẹp, mà phải thể hiện được BA sẽ ưu tiên làm việc với ai.

Có thể kết luận:

Khách hàng, tài xế, nhân viên vận hành và Ban giám đốc là nhóm stakeholder có mức độ ảnh hưởng và quan tâm cao, vì vậy BA cần ưu tiên phỏng vấn, thu thập và xác nhận yêu cầu với nhóm này. Nhà cung cấp thanh toán cần được phối hợp để xác định yêu cầu tích hợp. Đội phát triển và quản trị hệ thống cần được cập nhật yêu cầu để đảm bảo giải pháp có khả năng triển khai và mở rộng.

Một điểm cần sửa nhẹ so với cách phân loại trên: nếu giảng viên hiểu “ảnh hưởng” theo nghĩa ảnh hưởng đến thành công kỹ thuật của hệ thống, thì đội phát triển và nhà cung cấp thanh toán có thể được đặt cao hơn. Vì vậy khi nộp bài, bạn nên ghi rõ tiêu chí ma trận là “quyền lực/ảnh hưởng đối với quyết định và nghiệp vụ” để cách phân loại có cơ sở.
