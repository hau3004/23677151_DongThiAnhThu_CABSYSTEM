## 1. Test Cases Đăng ký tài khoản

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| **TC-REG-001** | Đăng ký tài khoản | Đăng ký với đầy đủ thông tin hợp lệ | Người dùng chưa có tài khoản | 1. Mở chức năng đăng ký<br>2. Nhập thông tin<br>3. Submit | `fullName = Nguyễn Văn A`<br>`phone = 0901234567`<br>`email = user01@gmail.com`<br>`password = Pass123` | Đăng ký thành công, hệ thống trả thông tin `UserResponse` | High |
| **TC-REG-002** | Đăng ký tài khoản | Đăng ký Customer với email hợp lệ | Email chưa tồn tại | 1. Nhập đầy đủ thông tin<br>2. Submit | `fullName` hợp lệ<br>`phone` hợp lệ<br>`email` hợp lệ<br>`password` hợp lệ | Tạo tài khoản Customer thành công | High |
| **TC-REG-003** | Đăng ký tài khoản | Đăng ký Driver với thông tin hợp lệ | Email và phone chưa tồn tại | 1. Nhập thông tin Driver<br>2. Submit request | `fullName` hợp lệ<br>`phone` hợp lệ<br>`email` hợp lệ<br>`password` hợp lệ | Tạo tài khoản Driver thành công | High |
| **TC-REG-004** | Đăng ký tài khoản | Đăng ký bằng số điện thoại và email chưa từng sử dụng | Người dùng chưa đăng ký trước đó | 1. Nhập phone mới<br>2. Nhập email mới<br>3. Submit | Phone và email chưa tồn tại | Hệ thống tạo tài khoản thành công | High |
| **TC-REG-005** | Đăng ký tài khoản | Đăng ký bằng email đã tồn tại | Email đã được sử dụng | 1. Nhập thông tin<br>2. Submit | `email = user01@gmail.com` | Hệ thống từ chối đăng ký và trả HTTP `409 Conflict` | High |
| **TC-REG-006** | Đăng ký tài khoản | Đăng ký bằng số điện thoại đã tồn tại | Phone đã được sử dụng | 1. Nhập thông tin<br>2. Submit | `phone = 0901234567` | Hệ thống từ chối đăng ký và trả HTTP `409 Conflict` | High |
| **TC-REG-007** | Đăng ký tài khoản | Đăng ký khi thiếu một thông tin bắt buộc | Người dùng chưa có tài khoản | 1. Bỏ một field bắt buộc<br>2. Submit | Thiếu `fullName` hoặc `phone` hoặc `email` hoặc `password` | Request bị từ chối do thiếu field bắt buộc | High |
| **TC-REG-008** | Đăng ký tài khoản | Đăng ký với email và phone đã tồn tại | Email và phone đã tồn tại | 1. Nhập email đã tồn tại<br>2. Nhập phone đã tồn tại<br>3. Submit | Email + phone đã tồn tại | Hệ thống không tạo tài khoản mới và trả lỗi `409 Conflict` | High |
| **TC-REG-009** | Đăng ký tài khoản | Nhập `fullName` ở giá trị biên hợp lệ | Người dùng chưa có tài khoản | 1. Nhập `fullName` ở giới hạn hợp lệ<br>2. Nhập các field còn lại<br>3. Submit | `fullName` = giá trị ngắn nhất được schema cho phép | Request được xử lý thành công nếu dữ liệu đáp ứng schema | Medium |
| **TC-REG-010** | Đăng ký tài khoản | Nhập `fullName` có độ dài lớn | Người dùng chưa có tài khoản | 1. Nhập `fullName` dài<br>2. Nhập các field còn lại<br>3. Submit | `fullName` = chuỗi có độ dài lớn | Hệ thống xử lý theo giới hạn được định nghĩa trong schema | Medium |
| **TC-REG-011** | Đăng ký tài khoản | Nhập phone ở giá trị biên hợp lệ | Người dùng chưa có tài khoản | 1. Nhập phone ở giới hạn hợp lệ<br>2. Nhập các field còn lại<br>3. Submit | `phone` = giá trị biên hợp lệ | Request được xử lý nếu đáp ứng rule validation | Medium |
| **TC-REG-012** | Đăng ký tài khoản | Nhập password ở giá trị biên | Người dùng chưa có tài khoản | 1. Nhập password ở giới hạn hỗ trợ<br>2. Nhập các field còn lại<br>3. Submit | `password` = giá trị biên hợp lệ | Hệ thống xử lý theo rule password được định nghĩa | Medium |
| **TC-REG-013** | Đăng ký tài khoản | Bỏ trống `fullName` | Người dùng chưa có tài khoản | 1. Để `fullName` rỗng<br>2. Nhập các field còn lại<br>3. Submit | `fullName = ""` | Request bị từ chối vì `fullName` là field bắt buộc | High |
| **TC-REG-014** | Đăng ký tài khoản | Bỏ trống `phone` | Người dùng chưa có tài khoản | 1. Để `phone` rỗng<br>2. Nhập các field còn lại<br>3. Submit | `phone = ""` | Request bị từ chối vì `phone` là field bắt buộc | High |
| **TC-REG-015** | Đăng ký tài khoản | Bỏ trống `email` | Người dùng chưa có tài khoản | 1. Để `email` rỗng<br>2. Nhập các field còn lại<br>3. Submit | `email = ""` | Request bị từ chối vì `email` là field bắt buộc | High |
| **TC-REG-016** | Đăng ký tài khoản | Bỏ trống `password` | Người dùng chưa có tài khoản | 1. Để `password` rỗng<br>2. Nhập các field còn lại<br>3. Submit | `password = ""` | Request bị từ chối vì `password` là field bắt buộc | High |
| **TC-REG-017** | Đăng ký tài khoản | Nhập email sai định dạng | Người dùng chưa có tài khoản | 1. Nhập email sai format<br>2. Nhập các field còn lại<br>3. Submit | `email = abc@` | Request bị từ chối do email không đúng format `email` | High |
| **TC-REG-018** | Đăng ký tài khoản | Nhập phone sai định dạng | Người dùng chưa có tài khoản | 1. Nhập phone sai format<br>2. Nhập các field còn lại<br>3. Submit | `phone = phone123` | Request bị từ chối nếu phone không đáp ứng validation của hệ thống | High |
| **TC-REG-019** | Đăng ký tài khoản | Nhập password không đáp ứng format | Người dùng chưa có tài khoản | 1. Nhập password không hợp lệ<br>2. Nhập các field còn lại<br>3. Submit | `password = 12345` | Request bị validation nếu password không đáp ứng rule/schema | Medium |
| **TC-REG-020** | Đăng ký tài khoản | Gửi request với field sai kiểu dữ liệu | Người dùng chưa có tài khoản | 1. Tạo request sai kiểu dữ liệu<br>2. Submit API request | `fullName = 123`<br>`phone = true` | Request bị từ chối do sai kiểu dữ liệu theo schema | High |
## 2. Test Cases Đăng nhập tài khoản 

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| **TC-LOGIN-001** | Đăng nhập | Đăng nhập với email và password hợp lệ | Tài khoản tồn tại và hoạt động | Nhập email, password → Login | Email hợp lệ + password đúng | Đăng nhập thành công, hệ thống trả JWT token | High |
| **TC-LOGIN-002** | Đăng nhập | Customer đăng nhập thành công | Tài khoản Customer tồn tại | Nhập thông tin → Login | Email Customer + password đúng | Đăng nhập thành công và trả thông tin xác thực | High |
| **TC-LOGIN-003** | Đăng nhập | Driver đăng nhập thành công | Tài khoản Driver tồn tại | Nhập thông tin → Login | Email Driver + password đúng | Đăng nhập thành công | High |
| **TC-LOGIN-004** | Đăng nhập | Đăng nhập bằng thông tin xác thực hợp lệ | Tài khoản hợp lệ | Gửi POST `/auth/login` | Email + password hợp lệ | API trả HTTP 200 và JWT | High |
| **TC-LOGIN-005** | Đăng nhập | Đăng nhập với email không tồn tại | Email chưa được đăng ký | Nhập email và password → Login | Email không tồn tại | Hệ thống từ chối và trả HTTP 401 | High |
| **TC-LOGIN-006** | Đăng nhập | Đăng nhập với password sai | Email tồn tại | Nhập email + password sai | Email đúng, password sai | Hệ thống trả HTTP 401 | High |
| **TC-LOGIN-007** | Đăng nhập | Đăng nhập với cả email và password sai | Không yêu cầu tài khoản hợp lệ | Nhập thông tin → Login | Email sai + password sai | Hệ thống trả HTTP 401 | High |
| **TC-LOGIN-008** | Đăng nhập | Đăng nhập bằng tài khoản không ở trạng thái hoạt động | Tài khoản có trạng thái không hoạt động | Nhập thông tin → Login | Email + password đúng | Hệ thống không cho phép đăng nhập nếu tài khoản không được phép truy cập | High |
| **TC-LOGIN-009** | Đăng nhập | Email ở giá trị biên hợp lệ | Tài khoản tồn tại | Nhập email và password → Login | Email hợp lệ ở giới hạn dữ liệu hỗ trợ | Hệ thống xử lý đăng nhập | Medium |
| **TC-LOGIN-010** | Đăng nhập | Password ở giá trị biên hợp lệ | Tài khoản tồn tại | Nhập password → Login | Password ở giới hạn được hệ thống hỗ trợ | Hệ thống xử lý request | Medium |
| **TC-LOGIN-011** | Đăng nhập | Email có độ dài lớn nhưng vẫn hợp lệ theo schema | Tài khoản tương ứng tồn tại | Nhập email → Login | Email dài hợp lệ | Hệ thống xử lý theo schema | Medium |
| **TC-LOGIN-012** | Đăng nhập | Request có kích thước dữ liệu lớn trong giới hạn hệ thống | Tài khoản hợp lệ | Gửi request | Email/password hợp lệ ở giới hạn hỗ trợ | Hệ thống xử lý request bình thường | Low |
| **TC-LOGIN-013** | Đăng nhập | Bỏ trống email | Tài khoản tồn tại | Để email trống → Login | `email = ""` | Request bị từ chối | High |
| **TC-LOGIN-014** | Đăng nhập | Bỏ trống password | Tài khoản tồn tại | Để password trống → Login | `password = ""` | Request bị từ chối | High |
| **TC-LOGIN-015** | Đăng nhập | Bỏ trống cả email và password | Không yêu cầu đăng nhập trước | Submit form rỗng | `email = ""`, `password = ""` | Request bị từ chối | High |
| **TC-LOGIN-016** | Đăng nhập | Gửi request body rỗng | Không có thông tin đăng nhập | Gửi `{}` | Empty request body | Request bị từ chối | High |
| **TC-LOGIN-017** | Đăng nhập | Email sai định dạng | Không cần tài khoản hợp lệ | Nhập email sai format → Login | `email = abc@` | Request bị từ chối do email không đúng format | High |
| **TC-LOGIN-018** | Đăng nhập | Email không phải kiểu string | Không cần tài khoản hợp lệ | Gửi API request | `email = 12345` | Request bị từ chối do sai kiểu dữ liệu | High |
| **TC-LOGIN-019** | Đăng nhập | Password không đúng kiểu dữ liệu | Không cần tài khoản hợp lệ | Gửi API request | `password = 12345` | Request bị từ chối nếu không đáp ứng schema | High |
| **TC-LOGIN-020** | Đăng nhập | Gửi request với field sai kiểu dữ liệu | Không cần tài khoản hợp lệ | Gửi API request | `email = true`<br>`password = 123` | Request bị từ chối validation | High |

## 3. Test Cases Quản lý thông tin cá nhân

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| **TC-PROFILE-001** | Quản lý thông tin cá nhân | Xem thông tin cá nhân với tài khoản hợp lệ | User đã đăng nhập | 1. Gửi GET `/users/me` | JWT hợp lệ | Trả về HTTP 200 và thông tin cá nhân của user | High |
| **TC-PROFILE-002** | Quản lý thông tin cá nhân | Cập nhật fullName hợp lệ | User đã đăng nhập | 1. Gửi PUT `/users/me` | `fullName = "Nguyen Van A"` | Cập nhật fullName thành công | High |
| **TC-PROFILE-003** | Quản lý thông tin cá nhân | Cập nhật phone hợp lệ | User đã đăng nhập | 1. Gửi PUT `/users/me` | `phone = "0901234567"` | Cập nhật phone thành công | High |
| **TC-PROFILE-004** | Quản lý thông tin cá nhân | Cập nhật đồng thời fullName và phone hợp lệ | User đã đăng nhập | 1. Gửi PUT `/users/me` | `fullName = "Nguyen Van A"`<br>`phone = "0901234567"` | Cả hai thông tin được cập nhật thành công | High |
| **TC-PROFILE-005** | Quản lý thông tin cá nhân | Xem thông tin khi chưa đăng nhập | Chưa đăng nhập | 1. Gửi GET `/users/me` | Không có JWT | Trả về lỗi Unauthorized | High |
| **TC-PROFILE-006** | Quản lý thông tin cá nhân | Cập nhật thông tin khi chưa đăng nhập | Chưa đăng nhập | 1. Gửi PUT `/users/me` | `fullName = "Nguyen Van A"` | Request bị từ chối do chưa xác thực | High |
| **TC-PROFILE-007** | Quản lý thông tin cá nhân | Xem thông tin với JWT không hợp lệ | Có JWT không hợp lệ | 1. Gửi GET `/users/me` | JWT sai | Request bị từ chối | High |
| **TC-PROFILE-008** | Quản lý thông tin cá nhân | Cập nhật thông tin với JWT không hợp lệ | Có JWT không hợp lệ | 1. Gửi PUT `/users/me` | JWT sai, fullName hợp lệ | Request bị từ chối | High |
| **TC-PROFILE-009** | Quản lý thông tin cá nhân | Cập nhật fullName với giá trị biên hợp lệ | User đã đăng nhập | 1. Gửi PUT `/users/me` | `fullName` = giá trị string ngắn nhất được API chấp nhận | Cập nhật thành công nếu thỏa validation | Medium |
| **TC-PROFILE-010** | Quản lý thông tin cá nhân | Cập nhật fullName với giá trị dài tại giới hạn hỗ trợ | User đã đăng nhập | 1. Gửi PUT `/users/me` | `fullName` = string tại giới hạn hỗ trợ | Hệ thống xử lý theo giới hạn được định nghĩa | Medium |
| **TC-PROFILE-011** | Quản lý thông tin cá nhân | Cập nhật phone với giá trị biên hợp lệ | User đã đăng nhập | 1. Gửi PUT `/users/me` | `phone` = giá trị phone tại giới hạn hợp lệ | Cập nhật thành công nếu thỏa validation | Medium |
| **TC-PROFILE-012** | Quản lý thông tin cá nhân | Cập nhật phone vượt giới hạn hợp lệ | User đã đăng nhập | 1. Gửi PUT `/users/me` | `phone` vượt giới hạn | Hệ thống từ chối nếu vi phạm validation | Medium |
| **TC-PROFILE-013** | Quản lý thông tin cá nhân | Bỏ trống fullName khi cập nhật | User đã đăng nhập | 1. Gửi PUT `/users/me` | `fullName = ""` | Hệ thống xử lý theo validation của field | High |
| **TC-PROFILE-014** | Quản lý thông tin cá nhân | Bỏ trống phone khi cập nhật | User đã đăng nhập | 1. Gửi PUT `/users/me` | `phone = ""` | Hệ thống xử lý theo validation của field | High |
| **TC-PROFILE-015** | Quản lý thông tin cá nhân | Gửi request body rỗng | User đã đăng nhập | 1. Gửi PUT `/users/me` | `{}` | API xử lý request theo schema | Medium |
| **TC-PROFILE-016** | Quản lý thông tin cá nhân | Gửi request không có body | User đã đăng nhập | 1. Gửi PUT `/users/me` | Không có request body | API xử lý theo validation của request | Medium |
| **TC-PROFILE-017** | Quản lý thông tin cá nhân | Nhập fullName sai định dạng dữ liệu | User đã đăng nhập | 1. Gửi PUT `/users/me` | `fullName = 123456` | Request bị từ chối do fullName phải là string | High |
| **TC-PROFILE-018** | Quản lý thông tin cá nhân | Nhập phone sai định dạng dữ liệu | User đã đăng nhập | 1. Gửi PUT `/users/me` | `phone = 123456` dạng number | Request bị từ chối do phone phải là string | High |
| **TC-PROFILE-019** | Quản lý thông tin cá nhân | Nhập fullName dưới dạng object | User đã đăng nhập | 1. Gửi PUT `/users/me` | `fullName = {name:"A"}` | Request bị từ chối do sai schema | High |
| **TC-PROFILE-020** | Quản lý thông tin cá nhân | Nhập phone dưới dạng array | User đã đăng nhập | 1. Gửi PUT `/users/me` | `phone = ["0901234567"]` | Request bị từ chối do sai schema | High |
## 4. Test Cases Quản lý hồ sơ tài xế

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| **TC-DRIVER-001** | Quản lý hồ sơ tài xế | Xem thông tin phương tiện hiện tại | Tài xế đã đăng nhập | 1. Gửi GET `/drivers/me/vehicle` | JWT hợp lệ | Trả về HTTP 200 và thông tin phương tiện của tài xế | High |
| **TC-DRIVER-002** | Quản lý hồ sơ tài xế | Cập nhật loại phương tiện hợp lệ | Tài xế đã đăng nhập | 1. Gửi PUT `/drivers/me/vehicle` | `vehicleType = CAR_4_SEATS` | Cập nhật phương tiện thành công | High |
| **TC-DRIVER-003** | Quản lý hồ sơ tài xế | Cập nhật biển số xe hợp lệ | Tài xế đã đăng nhập | 1. Gửi PUT `/drivers/me/vehicle` | `licensePlate = 51A-12345` | Biển số xe được cập nhật thành công | High |
| **TC-DRIVER-004** | Quản lý hồ sơ tài xế | Cập nhật loại xe và biển số cùng lúc | Tài xế đã đăng nhập | 1. Gửi PUT `/drivers/me/vehicle` | `vehicleType = CAR_7_SEATS`<br>`licensePlate = 51B-67890` | Thông tin phương tiện được cập nhật thành công | High |
| **TC-DRIVER-005** | Quản lý hồ sơ tài xế | Xem hồ sơ phương tiện khi chưa đăng nhập | Chưa đăng nhập | 1. Gửi GET `/drivers/me/vehicle` | Không có JWT | Request bị từ chối do chưa xác thực | High |
| **TC-DRIVER-006** | Quản lý hồ sơ tài xế | Cập nhật phương tiện khi chưa đăng nhập | Chưa đăng nhập | 1. Gửi PUT `/drivers/me/vehicle` | `vehicleType = CAR_4_SEATS` | Request bị từ chối | High |
| **TC-DRIVER-007** | Quản lý hồ sơ tài xế | Cập nhật phương tiện bằng JWT không hợp lệ | Có JWT không hợp lệ | 1. Gửi PUT `/drivers/me/vehicle` | JWT sai | Request bị từ chối | High |
| **TC-DRIVER-008** | Quản lý hồ sơ tài xế | Customer truy cập API hồ sơ tài xế | Đăng nhập bằng tài khoản CUSTOMER | 1. Gửi GET `/drivers/me/vehicle` | JWT role = `CUSTOMER` | Request bị từ chối do không đúng quyền | High |
| **TC-DRIVER-009** | Quản lý hồ sơ tài xế | Chọn loại xe ở giá trị đầu tiên trong enum | Tài xế đã đăng nhập | 1. Gửi PUT `/drivers/me/vehicle` | `vehicleType = CAR_4_SEATS` | Loại xe được cập nhật thành công | Medium |
| **TC-DRIVER-010** | Quản lý hồ sơ tài xế | Chọn loại xe ở giá trị cuối trong enum | Tài xế đã đăng nhập | 1. Gửi PUT `/drivers/me/vehicle` | `vehicleType = MOTORBIKE` | Loại xe được cập nhật thành công | Medium |
| **TC-DRIVER-011** | Quản lý hồ sơ tài xế | Cập nhật vehicleStatus = ACTIVE | Tài xế đã đăng nhập | 1. Gửi PUT `/drivers/me/vehicle` | `vehicleStatus = ACTIVE` | Trạng thái phương tiện được ghi nhận ACTIVE | Medium |
| **TC-DRIVER-012** | Quản lý hồ sơ tài xế | Cập nhật vehicleStatus = INACTIVE | Tài xế đã đăng nhập | 1. Gửi PUT `/drivers/me/vehicle` | `vehicleStatus = INACTIVE` | Trạng thái phương tiện được ghi nhận INACTIVE | Medium |
| **TC-DRIVER-013** | Quản lý hồ sơ tài xế | Bỏ trống vehicleType | Tài xế đã đăng nhập | 1. Gửi PUT `/drivers/me/vehicle` | `vehicleType = ""` | Request bị xử lý theo validation; không cập nhật nếu field không hợp lệ | High |
| **TC-DRIVER-014** | Quản lý hồ sơ tài xế | Bỏ trống licensePlate | Tài xế đã đăng nhập | 1. Gửi PUT `/drivers/me/vehicle` | `licensePlate = ""` | Request bị xử lý theo validation; không cập nhật nếu field không hợp lệ | High |
| **TC-DRIVER-015** | Quản lý hồ sơ tài xế | Gửi request body rỗng | Tài xế đã đăng nhập | 1. Gửi PUT `/drivers/me/vehicle` | `{}` | API xử lý theo schema và validation | Medium |
| **TC-DRIVER-016** | Quản lý hồ sơ tài xế | Gửi request không có body | Tài xế đã đăng nhập | 1. Gửi PUT `/drivers/me/vehicle` | Empty body | API từ chối hoặc xử lý theo validation của request | Medium |
| **TC-DRIVER-017** | Quản lý hồ sơ tài xế | Nhập vehicleType sai định dạng | Tài xế đã đăng nhập | 1. Gửi PUT `/drivers/me/vehicle` | `vehicleType = CAR` | Request bị từ chối vì không thuộc enum vehicle type | High |
| **TC-DRIVER-018** | Quản lý hồ sơ tài xế | Nhập vehicleType sai kiểu dữ liệu | Tài xế đã đăng nhập | 1. Gửi PUT `/drivers/me/vehicle` | `vehicleType = 123` | Request bị từ chối do sai kiểu dữ liệu/schema | High |
| **TC-DRIVER-019** | Quản lý hồ sơ tài xế | Nhập licensePlate sai kiểu dữ liệu | Tài xế đã đăng nhập | 1. Gửi PUT `/drivers/me/vehicle` | `licensePlate = 12345` dạng number | Request bị từ chối do licensePlate phải là string | High |
| **TC-DRIVER-020** | Quản lý hồ sơ tài xế | Nhập licensePlate dưới dạng array | Tài xế đã đăng nhập | 1. Gửi PUT `/drivers/me/vehicle` | `licensePlate = ["51A-12345"]` | Request bị từ chối do sai schema | High |
## 5. Test Cases Cập nhật trạng thái sẵn sàng nhận chuyến

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| **TC-STATUS-001** | Cập nhật trạng thái sẵn sàng nhận chuyến | Cập nhật trạng thái sang AVAILABLE | Tài xế đã đăng nhập | 1. Gửi PATCH `/drivers/me/status` | `status = AVAILABLE` | Trạng thái tài xế được cập nhật thành AVAILABLE | High |
| **TC-STATUS-002** | Cập nhật trạng thái sẵn sàng nhận chuyến | Cập nhật trạng thái sang UNAVAILABLE | Tài xế đã đăng nhập | 1. Gửi PATCH `/drivers/me/status` | `status = UNAVAILABLE` | Trạng thái tài xế được cập nhật thành UNAVAILABLE | High |
| **TC-STATUS-003** | Cập nhật trạng thái sẵn sàng nhận chuyến | Chuyển từ UNAVAILABLE sang AVAILABLE | Tài xế đang UNAVAILABLE | 1. Gửi PATCH `/drivers/me/status` | `status = AVAILABLE` | Trạng thái chuyển thành AVAILABLE | High |
| **TC-STATUS-004** | Cập nhật trạng thái sẵn sàng nhận chuyến | Chuyển từ AVAILABLE sang UNAVAILABLE | Tài xế đang AVAILABLE | 1. Gửi PATCH `/drivers/me/status` | `status = UNAVAILABLE` | Trạng thái chuyển thành UNAVAILABLE | High |
| **TC-STATUS-005** | Cập nhật trạng thái sẵn sàng nhận chuyến | Cập nhật trạng thái khi chưa đăng nhập | Chưa đăng nhập | 1. Gửi PATCH `/drivers/me/status` | Không có JWT | Request bị từ chối do chưa xác thực | High |
| **TC-STATUS-006** | Cập nhật trạng thái sẵn sàng nhận chuyến | Cập nhật trạng thái bằng JWT không hợp lệ | JWT không hợp lệ | 1. Gửi PATCH `/drivers/me/status` | `status = AVAILABLE` | Request bị từ chối | High |
| **TC-STATUS-007** | Cập nhật trạng thái sẵn sàng nhận chuyến | Customer cập nhật trạng thái tài xế | Đăng nhập bằng CUSTOMER | 1. Gửi PATCH `/drivers/me/status` | `status = AVAILABLE` | Request bị từ chối do không đúng quyền | High |
| **TC-STATUS-008** | Cập nhật trạng thái sẵn sàng nhận chuyến | Gửi trạng thái không thuộc enum | Tài xế đã đăng nhập | 1. Gửi PATCH `/drivers/me/status` | `status = BUSY` | Request bị từ chối vì trạng thái không hợp lệ | High |
| **TC-STATUS-009** | Cập nhật trạng thái sẵn sàng nhận chuyến | Sử dụng giá trị AVAILABLE tại biên enum | Tài xế đã đăng nhập | 1. Gửi PATCH `/drivers/me/status` | `status = AVAILABLE` | Trạng thái được chấp nhận | Medium |
| **TC-STATUS-010** | Cập nhật trạng thái sẵn sàng nhận chuyến | Sử dụng giá trị UNAVAILABLE tại biên enum | Tài xế đã đăng nhập | 1. Gửi PATCH `/drivers/me/status` | `status = UNAVAILABLE` | Trạng thái được chấp nhận | Medium |
| **TC-STATUS-011** | Cập nhật trạng thái sẵn sàng nhận chuyến | Gửi chuỗi gần giống AVAILABLE | Tài xế đã đăng nhập | 1. Gửi PATCH `/drivers/me/status` | `status = AVAILABLE ` | Request bị từ chối nếu không khớp enum chính xác | Medium |
| **TC-STATUS-012** | Cập nhật trạng thái sẵn sàng nhận chuyến | Gửi chuỗi gần giống UNAVAILABLE | Tài xế đã đăng nhập | 1. Gửi PATCH `/drivers/me/status` | `status = UNAVAILABLE ` | Request bị từ chối nếu không khớp enum chính xác | Medium |
| **TC-STATUS-013** | Cập nhật trạng thái sẵn sàng nhận chuyến | Bỏ trống status | Tài xế đã đăng nhập | 1. Gửi PATCH `/drivers/me/status` | `status = ""` | Request bị từ chối do status rỗng/không hợp lệ | High |
| **TC-STATUS-014** | Cập nhật trạng thái sẵn sàng nhận chuyến | Không truyền status | Tài xế đã đăng nhập | 1. Gửi PATCH `/drivers/me/status` | Không có field `status` | Request bị từ chối do thiếu dữ liệu cần thiết | High |
| **TC-STATUS-015** | Cập nhật trạng thái sẵn sàng nhận chuyến | Gửi request body rỗng | Tài xế đã đăng nhập | 1. Gửi PATCH `/drivers/me/status` | `{}` | Request bị từ chối do thiếu status | High |
| **TC-STATUS-016** | Cập nhật trạng thái sẵn sàng nhận chuyến | Gửi request không có body | Tài xế đã đăng nhập | 1. Gửi PATCH `/drivers/me/status` | Empty body | Request bị từ chối do thiếu dữ liệu | High |
| **TC-STATUS-017** | Cập nhật trạng thái sẵn sàng nhận chuyến | status sai kiểu số | Tài xế đã đăng nhập | 1. Gửi PATCH `/drivers/me/status` | `status = 1` | Request bị từ chối do sai kiểu dữ liệu | High |
| **TC-STATUS-018** | Cập nhật trạng thái sẵn sàng nhận chuyến | status sai kiểu boolean | Tài xế đã đăng nhập | 1. Gửi PATCH `/drivers/me/status` | `status = true` | Request bị từ chối do sai kiểu dữ liệu | High |
| **TC-STATUS-019** | Cập nhật trạng thái sẵn sàng nhận chuyến | status sai kiểu array | Tài xế đã đăng nhập | 1. Gửi PATCH `/drivers/me/status` | `status = ["AVAILABLE"]` | Request bị từ chối do sai schema | High |
| **TC-STATUS-020** | Cập nhật trạng thái sẵn sàng nhận chuyến | status sai kiểu object | Tài xế đã đăng nhập | 1. Gửi PATCH `/drivers/me/status` | `status = {"value":"AVAILABLE"}` | Request bị từ chối do sai schema | High |
## 6. Test Cases Nhập thông tin chuyến

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| **TC-TRIP-001** | Nhập thông tin chuyến | Nhập đầy đủ điểm đón, điểm đến và loại xe hợp lệ | Customer đã đăng nhập | 1. Nhập điểm đón<br>2. Nhập điểm đến<br>3. Chọn loại xe | `Pickup = "Trường ĐH ABC"`<br>`Destination = "Chợ Bến Thành"`<br>`VehicleType = CAR_4_SEATS` | Thông tin chuyến được chấp nhận và có thể tiếp tục đặt xe | High |
| **TC-TRIP-002** | Nhập thông tin chuyến | Nhập thông tin chuyến với xe 7 chỗ | Customer đã đăng nhập | 1. Nhập pickup<br>2. Nhập destination<br>3. Chọn loại xe | `VehicleType = CAR_7_SEATS` | Loại xe được chấp nhận | High |
| **TC-TRIP-003** | Nhập thông tin chuyến | Nhập thông tin chuyến với xe máy | Customer đã đăng nhập | 1. Nhập pickup<br>2. Nhập destination<br>3. Chọn loại xe | `VehicleType = MOTORBIKE` | Loại xe được chấp nhận | High |
| **TC-TRIP-004** | Nhập thông tin chuyến | Nhập đầy đủ thông tin chuyến để thực hiện đặt xe | Customer đã đăng nhập | 1. Nhập pickup<br>2. Nhập destination<br>3. Chọn vehicle type<br>4. Tiếp tục | Pickup + Destination + VehicleType hợp lệ | Hệ thống ghi nhận thông tin chuyến và cho phép chuyển sang bước tiếp theo | High |
| **TC-TRIP-005** | Nhập thông tin chuyến | Nhập thông tin khi chưa đăng nhập | Chưa đăng nhập | 1. Truy cập chức năng nhập thông tin chuyến | Không có JWT | Hệ thống yêu cầu đăng nhập trước khi thực hiện | High |
| **TC-TRIP-006** | Nhập thông tin chuyến | Bỏ qua điểm đón | Customer đã đăng nhập | 1. Nhập destination<br>2. Chọn vehicle type<br>3. Tiếp tục | Pickup = thiếu | Hệ thống yêu cầu nhập điểm đón và không cho tiếp tục đặt xe | High |
| **TC-TRIP-007** | Nhập thông tin chuyến | Bỏ qua điểm đến | Customer đã đăng nhập | 1. Nhập pickup<br>2. Chọn vehicle type<br>3. Tiếp tục | Destination = thiếu | Hệ thống yêu cầu nhập điểm đến và không cho tiếp tục đặt xe | High |
| **TC-TRIP-008** | Nhập thông tin chuyến | Không chọn loại phương tiện | Customer đã đăng nhập | 1. Nhập pickup<br>2. Nhập destination<br>3. Không chọn vehicle type | VehicleType = thiếu | Hệ thống yêu cầu chọn loại phương tiện | High |
| **TC-TRIP-009** | Nhập thông tin chuyến | Chọn loại xe ở giá trị đầu tiên của enum | Customer đã đăng nhập | 1. Nhập đầy đủ thông tin<br>2. Chọn vehicle type | `CAR_4_SEATS` | Hệ thống chấp nhận loại xe | Medium |
| **TC-TRIP-010** | Nhập thông tin chuyến | Chọn loại xe ở giá trị cuối của enum | Customer đã đăng nhập | 1. Nhập đầy đủ thông tin<br>2. Chọn vehicle type | `MOTORBIKE` | Hệ thống chấp nhận loại xe | Medium |
| **TC-TRIP-011** | Nhập thông tin chuyến | Chọn từng loại phương tiện hợp lệ được hỗ trợ | Customer đã đăng nhập | 1. Nhập pickup/destination<br>2. Lần lượt chọn loại xe | `CAR_4_SEATS`<br>`CAR_7_SEATS`<br>`MOTORBIKE` | Các giá trị thuộc enum đều được chấp nhận | Medium |
| **TC-TRIP-012** | Nhập thông tin chuyến | Nhập điểm đón và điểm đến ở hai địa điểm khác nhau | Customer đã đăng nhập | 1. Nhập pickup<br>2. Nhập destination<br>3. Chọn xe | `Pickup ≠ Destination` | Hệ thống ghi nhận tuyến chuyến hợp lệ | Medium |
| **TC-TRIP-013** | Nhập thông tin chuyến | Bỏ trống điểm đón | Customer đã đăng nhập | 1. Để trống pickup<br>2. Nhập destination<br>3. Chọn xe<br>4. Tiếp tục | `Pickup = ""` | Hệ thống thông báo cần nhập điểm đón | High |
| **TC-TRIP-014** | Nhập thông tin chuyến | Bỏ trống điểm đến | Customer đã đăng nhập | 1. Nhập pickup<br>2. Để trống destination<br>3. Chọn xe<br>4. Tiếp tục | `Destination = ""` | Hệ thống thông báo cần nhập điểm đến | High |
| **TC-TRIP-015** | Nhập thông tin chuyến | Bỏ trống loại xe | Customer đã đăng nhập | 1. Nhập pickup<br>2. Nhập destination<br>3. Không chọn xe | `VehicleType = ""` | Hệ thống yêu cầu chọn loại xe | High |
| **TC-TRIP-016** | Nhập thông tin chuyến | Gửi yêu cầu tạo chuyến với các trường bắt buộc rỗng | Customer đã đăng nhập | 1. Gửi request tạo chuyến | `Pickup = ""`<br>`Destination = ""`<br>`VehicleType = ""` | Request không được tạo chuyến | High |
| **TC-TRIP-017** | Nhập thông tin chuyến | Nhập vehicleType sai định dạng | Customer đã đăng nhập | 1. Gửi request | `VehicleType = CAR` | Request bị từ chối vì không thuộc enum được hỗ trợ | High |
| **TC-TRIP-018** | Nhập thông tin chuyến | Nhập vehicleType sai kiểu dữ liệu | Customer đã đăng nhập | 1. Gửi request | `VehicleType = 123` | Request bị từ chối do sai kiểu dữ liệu | High |
| **TC-TRIP-019** | Nhập thông tin chuyến | Nhập pickup sai kiểu dữ liệu | Customer đã đăng nhập | 1. Gửi request | `Pickup = 12345` | Request bị từ chối do dữ liệu không đúng schema | High |
| **TC-TRIP-020** | Nhập thông tin chuyến | Nhập destination sai kiểu dữ liệu | Customer đã đăng nhập | 1. Gửi request | `Destination = {"address":"ABC"}` | Request bị từ chối do dữ liệu không đúng schema | High |
## 7. Test Cases Tính giá dự kiến

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| **TC-FARE-001** | Tính giá dự kiến | Tính giá dự kiến với thông tin chuyến hợp lệ | Customer đã đăng nhập | 1. Gửi POST `/trips/estimate`<br>2. Nhập đầy đủ thông tin chuyến | Pickup hợp lệ<br>Destination hợp lệ<br>VehicleType = `CAR_4_SEATS` | Hệ thống trả về HTTP `200` và thông tin giá dự kiến | High |
| **TC-FARE-002** | Tính giá dự kiến | Tính giá dự kiến với xe 7 chỗ | Customer đã đăng nhập | 1. Gửi POST `/trips/estimate`<br>2. Nhập thông tin chuyến | `VehicleType = CAR_7_SEATS` | Hệ thống tính và trả về giá dự kiến | High |
| **TC-FARE-003** | Tính giá dự kiến | Tính giá dự kiến với xe máy | Customer đã đăng nhập | 1. Gửi POST `/trips/estimate`<br>2. Nhập thông tin chuyến | `VehicleType = MOTORBIKE` | Hệ thống tính và trả về giá dự kiến | High |
| **TC-FARE-004** | Tính giá dự kiến | Tính giá dự kiến với tuyến đường hợp lệ | Customer đã đăng nhập | 1. Nhập pickup<br>2. Nhập destination<br>3. Gửi request estimate | Pickup ≠ Destination<br>VehicleType hợp lệ | Hệ thống trả về `EstimatedFare` tương ứng với chuyến | High |
| **TC-FARE-005** | Tính giá dự kiến | Tính giá khi chưa đăng nhập | Chưa đăng nhập | 1. Gửi POST `/trips/estimate` | Không có JWT | Request bị từ chối do chưa xác thực | High |
| **TC-FARE-006** | Tính giá dự kiến | Tính giá khi thiếu điểm đón | Customer đã đăng nhập | 1. Gửi request estimate | Thiếu pickup | Hệ thống không tính giá và yêu cầu bổ sung điểm đón | High |
| **TC-FARE-007** | Tính giá dự kiến | Tính giá khi thiếu điểm đến | Customer đã đăng nhập | 1. Gửi request estimate | Thiếu destination | Hệ thống không tính giá và yêu cầu bổ sung điểm đến | High |
| **TC-FARE-008** | Tính giá dự kiến | Tính giá với loại xe không hợp lệ | Customer đã đăng nhập | 1. Gửi request estimate | `VehicleType = BUS` | Request bị từ chối vì loại xe không được hỗ trợ | High |
| **TC-FARE-009** | Tính giá dự kiến | Tính giá với loại xe `CAR_4_SEATS` | Customer đã đăng nhập | 1. Gửi request estimate | `VehicleType = CAR_4_SEATS` | Hệ thống chấp nhận giá trị đầu tiên trong enum | Medium |
| **TC-FARE-010** | Tính giá dự kiến | Tính giá với loại xe `MOTORBIKE` | Customer đã đăng nhập | 1. Gửi request estimate | `VehicleType = MOTORBIKE` | Hệ thống chấp nhận giá trị cuối trong enum | Medium |
| **TC-FARE-011** | Tính giá dự kiến | Tính giá với từng loại phương tiện được hỗ trợ | Customer đã đăng nhập | 1. Gửi request lần lượt với từng loại xe | `CAR_4_SEATS`<br>`CAR_7_SEATS`<br>`MOTORBIKE` | Tất cả giá trị hợp lệ đều được hệ thống xử lý | Medium |
| **TC-FARE-012** | Tính giá dự kiến | Kiểm tra kết quả trả về có EstimatedFare | Customer đã đăng nhập | 1. Gửi request estimate hợp lệ | Pickup + Destination + VehicleType hợp lệ | Response có thông tin `EstimatedFare` | Medium |
| **TC-FARE-013** | Tính giá dự kiến | Gửi pickup rỗng | Customer đã đăng nhập | 1. Gửi POST `/trips/estimate` | `Pickup = ""` | Hệ thống không thể xác định tuyến và không cho tính giá | High |
| **TC-FARE-014** | Tính giá dự kiến | Gửi destination rỗng | Customer đã đăng nhập | 1. Gửi POST `/trips/estimate` | `Destination = ""` | Hệ thống không thể xác định tuyến và không cho tính giá | High |
| **TC-FARE-015** | Tính giá dự kiến | Gửi vehicleType rỗng | Customer đã đăng nhập | 1. Gửi POST `/trips/estimate` | `VehicleType = ""` | Hệ thống không tính giá do thiếu loại phương tiện | High |
| **TC-FARE-016** | Tính giá dự kiến | Gửi toàn bộ thông tin estimate rỗng | Customer đã đăng nhập | 1. Gửi POST `/trips/estimate` | `Pickup = ""`<br>`Destination = ""`<br>`VehicleType = ""` | Request bị từ chối và không trả về giá dự kiến hợp lệ | High |
| **TC-FARE-017** | Tính giá dự kiến | Nhập vehicleType sai định dạng | Customer đã đăng nhập | 1. Gửi request estimate | `VehicleType = CAR` | Request bị từ chối vì không thuộc enum hợp lệ | High |
| **TC-FARE-018** | Tính giá dự kiến | Nhập vehicleType sai kiểu dữ liệu | Customer đã đăng nhập | 1. Gửi request estimate | `VehicleType = 123` | Request bị từ chối do sai kiểu dữ liệu | High |
| **TC-FARE-019** | Tính giá dự kiến | Nhập pickup sai kiểu dữ liệu | Customer đã đăng nhập | 1. Gửi request estimate | `Pickup = 12345` | Request bị từ chối do sai schema | High |
| **TC-FARE-020** | Tính giá dự kiến | Nhập destination sai kiểu dữ liệu | Customer đã đăng nhập | 1. Gửi request estimate | `Destination = {"address":"ABC"}` | Request bị từ chối do sai schema | High |
## 8. Test Cases Chọn phương thức thanh toán

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| **TC-PAYMETHOD-001** | Chọn phương thức thanh toán | Chọn phương thức thanh toán tiền mặt | Customer đã đăng nhập và đã nhập thông tin chuyến | 1. Chọn phương thức thanh toán | `CASH` | Hệ thống chấp nhận phương thức CASH và cho phép tiếp tục đặt xe | High |
| **TC-PAYMETHOD-002** | Chọn phương thức thanh toán | Chọn phương thức thanh toán ví điện tử | Customer đã đăng nhập và đã nhập thông tin chuyến | 1. Chọn phương thức thanh toán | `E_WALLET` | Hệ thống chấp nhận phương thức E_WALLET | High |
| **TC-PAYMETHOD-003** | Chọn phương thức thanh toán | Chọn phương thức thanh toán thẻ tín dụng | Customer đã đăng nhập và đã nhập thông tin chuyến | 1. Chọn phương thức thanh toán | `CREDIT_CARD` | Hệ thống chấp nhận phương thức CREDIT_CARD | High |
| **TC-PAYMETHOD-004** | Chọn phương thức thanh toán | Chọn phương thức thanh toán hợp lệ trước khi xác nhận đặt xe | Customer đã đăng nhập, thông tin chuyến và giá dự kiến hợp lệ | 1. Chọn một phương thức thanh toán hợp lệ<br>2. Tiếp tục | `CASH` | Phương thức thanh toán được ghi nhận và có thể chuyển sang bước xác nhận đặt xe | High |
| **TC-PAYMETHOD-005** | Chọn phương thức thanh toán | Chọn phương thức thanh toán khi chưa đăng nhập | Chưa đăng nhập | 1. Truy cập chức năng chọn thanh toán | Không có JWT | Hệ thống yêu cầu đăng nhập | High |
| **TC-PAYMETHOD-006** | Chọn phương thức thanh toán | Chọn phương thức thanh toán không được hỗ trợ | Customer đã đăng nhập | 1. Chọn phương thức thanh toán | `BANK_TRANSFER` | Hệ thống từ chối phương thức thanh toán không được hỗ trợ | High |
| **TC-PAYMETHOD-007** | Chọn phương thức thanh toán | Chọn phương thức thanh toán sai enum | Customer đã đăng nhập | 1. Gửi request với payment method không hợp lệ | `PAYPAL` | Request bị từ chối do giá trị không thuộc enum | High |
| **TC-PAYMETHOD-008** | Chọn phương thức thanh toán | Chọn phương thức thanh toán bằng JWT không hợp lệ | JWT không hợp lệ | 1. Gửi request chọn phương thức thanh toán | `CASH` | Request bị từ chối | High |
| **TC-PAYMETHOD-009** | Chọn phương thức thanh toán | Chọn giá trị đầu tiên trong enum payment method | Customer đã đăng nhập | 1. Chọn phương thức thanh toán | `CASH` | Phương thức được chấp nhận | Medium |
| **TC-PAYMETHOD-010** | Chọn phương thức thanh toán | Chọn giá trị cuối trong enum payment method | Customer đã đăng nhập | 1. Chọn phương thức thanh toán | `CREDIT_CARD` | Phương thức được chấp nhận | Medium |
| **TC-PAYMETHOD-011** | Chọn phương thức thanh toán | Kiểm tra toàn bộ các phương thức thanh toán được hỗ trợ | Customer đã đăng nhập | 1. Lần lượt chọn từng phương thức | `CASH`<br>`E_WALLET`<br>`CREDIT_CARD` | Cả 3 phương thức đều được hệ thống chấp nhận | Medium |
| **TC-PAYMETHOD-012** | Chọn phương thức thanh toán | Thay đổi phương thức thanh toán trước khi xác nhận đặt xe | Customer đã đăng nhập, thông tin chuyến hợp lệ | 1. Chọn `CASH`<br>2. Đổi sang `E_WALLET` | `CASH → E_WALLET` | Phương thức thanh toán cuối cùng được ghi nhận là E_WALLET | Medium |
| **TC-PAYMETHOD-013** | Chọn phương thức thanh toán | Không chọn phương thức thanh toán | Customer đã đăng nhập | 1. Không chọn payment method<br>2. Tiếp tục | Payment method = empty | Hệ thống yêu cầu chọn phương thức thanh toán | High |
| **TC-PAYMETHOD-014** | Chọn phương thức thanh toán | Gửi payment method là chuỗi rỗng | Customer đã đăng nhập | 1. Gửi request | `paymentMethod = ""` | Request bị từ chối do phương thức thanh toán không hợp lệ | High |
| **TC-PAYMETHOD-015** | Chọn phương thức thanh toán | Gửi request body rỗng | Customer đã đăng nhập | 1. Gửi request | `{}` | Request bị từ chối do thiếu phương thức thanh toán | High |
| **TC-PAYMETHOD-016** | Chọn phương thức thanh toán | Gửi request không có payment method | Customer đã đăng nhập | 1. Gửi request không chứa field payment method | Không truyền `paymentMethod` | Request bị từ chối do thiếu dữ liệu | High |
| **TC-PAYMETHOD-017** | Chọn phương thức thanh toán | Nhập payment method sai kiểu số | Customer đã đăng nhập | 1. Gửi request | `paymentMethod = 1` | Request bị từ chối do sai kiểu dữ liệu | High |
| **TC-PAYMETHOD-018** | Chọn phương thức thanh toán | Nhập payment method sai kiểu boolean | Customer đã đăng nhập | 1. Gửi request | `paymentMethod = true` | Request bị từ chối do sai kiểu dữ liệu | High |
| **TC-PAYMETHOD-019** | Chọn phương thức thanh toán | Nhập payment method dạng array | Customer đã đăng nhập | 1. Gửi request | `paymentMethod = ["CASH"]` | Request bị từ chối do sai schema | High |
| **TC-PAYMETHOD-020** | Chọn phương thức thanh toán | Nhập payment method dạng object | Customer đã đăng nhập | 1. Gửi request | `paymentMethod = {"type":"CASH"}` | Request bị từ chối do sai schema | High |

