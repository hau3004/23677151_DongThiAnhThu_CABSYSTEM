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
