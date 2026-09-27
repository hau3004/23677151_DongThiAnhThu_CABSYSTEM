# UC01 – QUẢN LÝ TÀI KHOẢN

| ID       | Tiêu chí      | Test case                                                     | Expected Result                    | Trace                     |
| -------- | ------------- | ------------------------------------------------------------- | ---------------------------------- | ------------------------- |
| TC01-001 | Valid         | Customer đăng ký tài khoản hợp lệ                             | Tài khoản Customer được tạo        | FR-01, BR-01, AC-01       |
| TC01-002 | Valid         | Driver tự đăng ký tài khoản hợp lệ                            | Tài khoản Driver được tạo          | FR-01, BR-15, AC-01       |
| TC01-003 | Valid         | Operator tạo tài khoản Driver                                 | Tài khoản Driver được tạo          | FR-01, BR-15, AC-01       |
| TC01-004 | Valid         | Customer đăng nhập bằng thông tin hợp lệ                      | Đăng nhập thành công               | FR-02, AC-01              |
| TC01-005 | Valid         | Driver đăng nhập bằng thông tin hợp lệ                        | Đăng nhập thành công               | FR-02, AC-01              |
| TC01-006 | Valid         | Operator đăng nhập bằng thông tin hợp lệ                      | Đăng nhập thành công               | FR-02, AC-01              |
| TC01-007 | Valid         | User xem thông tin cá nhân                                    | Thông tin cá nhân được hiển thị    | FR-03                     |
| TC01-008 | Valid         | User cập nhật thông tin cá nhân hợp lệ                        | Thông tin cá nhân được cập nhật    | FR-03                     |
| TC01-009 | Invalid       | Đăng nhập bằng thông tin xác thực không hợp lệ                | Đăng nhập thất bại                 | FR-02, EC-17              |
| TC01-010 | Invalid       | Đăng ký bằng dữ liệu không hợp lệ theo API                    | Request bị từ chối                 | FR-01, API Authentication |
| TC01-011 | Invalid       | Cập nhật hồ sơ bằng dữ liệu không hợp lệ theo API             | Request bị từ chối                 | FR-03, API Authentication |
| TC01-012 | Authorization | Customer truy cập chức năng không thuộc quyền                 | Request bị từ chối                 | BRL-03, FR-41             |
| TC01-013 | Authorization | Driver truy cập chức năng không thuộc quyền                   | Request bị từ chối                 | BRL-03, FR-41             |
| TC01-014 | Authorization | Operator truy cập chức năng không được cấp quyền              | Request bị từ chối                 | BRL-03, FR-41             |
| TC01-015 | Exception     | User chưa đăng nhập thực hiện chức năng yêu cầu xác thực      | Request bị từ chối                 | BRL-01, EC-17             |
| TC01-016 | Exception     | Thông tin xác thực không hợp lệ khi gọi API yêu cầu đăng nhập | Request bị từ chối                 | FR-02, API Authentication |
| TC01-017 | Data          | Kiểm tra dữ liệu sau khi cập nhật hồ sơ                       | Dữ liệu mới được lưu đúng          | FR-03                     |
| TC01-018 | Data          | Kiểm tra loại tài khoản sau khi tạo                           | Tài khoản được tạo đúng vai trò    | FR-01, BRL-03             |
| TC01-019 | Audit         | User thực hiện thao tác quan trọng trên tài khoản             | Thao tác được ghi nhận để truy vết | FR-42                     |
| TC01-020 | Consistency   | User đăng nhập sau khi tài khoản được tạo                     | Tài khoản vừa tạo đăng nhập được   | FR-01, FR-02, AC-01       |

---

# UC02 – QUẢN LÝ HỒ SƠ TÀI XẾ

| ID       | Tiêu chí      | Test case                                                        | Expected Result                                | Trace                     |
| -------- | ------------- | ---------------------------------------------------------------- | ---------------------------------------------- | ------------------------- |
| TC02-001 | Valid         | Driver xem hồ sơ cá nhân                                         | Hồ sơ Driver được hiển thị                     | FR-03, BR-15              |
| TC02-002 | Valid         | Driver cập nhật thông tin cá nhân                                | Hồ sơ được cập nhật                            | FR-03, BR-15              |
| TC02-003 | Valid         | Driver xem thông tin phương tiện                                 | Thông tin phương tiện được hiển thị            | FR-04                     |
| TC02-004 | Valid         | Driver cập nhật thông tin phương tiện                            | Thông tin phương tiện được cập nhật            | FR-04                     |
| TC02-005 | Valid         | Driver chuyển sang trạng thái SẴN SÀNG                           | Trạng thái readiness được cập nhật             | FR-04, BRL-02             |
| TC02-006 | Valid         | Driver chuyển sang trạng thái KHÔNG SẴNG                         | Trạng thái readiness được cập nhật             | FR-04                     |
| TC02-007 | Business Rule | Driver cập nhật readiness trước khi nhận request                 | Trạng thái readiness được dùng khi xét Driver  | FR-04, BRL-02             |
| TC02-008 | Business Rule | Driver ở trạng thái KHÔNG SẴNG khi hệ thống tìm Driver           | Driver không được xem là Driver phù hợp        | FR-11, BRL-02             |
| TC02-009 | Invalid       | Cập nhật hồ sơ bằng dữ liệu không hợp lệ theo API                | Request bị từ chối                             | FR-03, API Authentication |
| TC02-010 | Invalid       | Cập nhật phương tiện bằng dữ liệu không hợp lệ theo API          | Request bị từ chối                             | FR-04, API Authentication |
| TC02-011 | Authorization | Customer truy cập chức năng quản lý hồ sơ Driver                 | Request bị từ chối                             | BRL-03, FR-41             |
| TC02-012 | Authorization | Driver truy cập phương tiện không thuộc phạm vi quản lý của mình | Request bị từ chối                             | FR-04, BR-15              |
| TC02-013 | Exception     | Driver cập nhật phương tiện không tồn tại                        | Request bị từ chối                             | FR-04                     |
| TC02-014 | Data          | Kiểm tra thông tin phương tiện sau khi cập nhật                  | Dữ liệu phương tiện được lưu đúng              | FR-04                     |
| TC02-015 | Data          | Kiểm tra readiness sau khi cập nhật                              | Readiness được lưu đúng                        | FR-04                     |
| TC02-016 | Data          | Kiểm tra thông tin phương tiện thuộc Driver sau cập nhật         | Thông tin phương tiện được quản lý đúng Driver | FR-04, BR-15              |
| TC02-017 | Consistency   | Driver chuyển SẴN SÀNG rồi hệ thống tìm Driver                   | Driver có thể được xét trong quá trình tìm     | FR-11, BRL-02             |
| TC02-018 | Consistency   | Driver chuyển KHÔNG SẴNG rồi hệ thống tìm Driver                 | Driver không được chọn khi không phù hợp       | FR-11, BRL-02             |
| TC02-019 | Audit         | Driver cập nhật thông tin quan trọng                             | Thao tác được ghi nhận để truy vết             | FR-42                     |
| TC02-020 | Integration   | Thông tin Driver được sử dụng trong quá trình phân công          | Hệ thống sử dụng thông tin Driver phù hợp      | FR-04, FR-11              |

---

# UC03 – QUẢN LÝ CHUYẾN ĐI

| ID       | Tiêu chí      | Test case                                            | Expected Result                                                        | Trace                |
| -------- | ------------- | ---------------------------------------------------- | ---------------------------------------------------------------------- | -------------------- |
| TC03-001 | Valid         | Customer nhập điểm đón, điểm đến, loại xe và Book    | Booking request được tạo                                               | FR-05, FR-08, AC-03  |
| TC03-002 | Valid         | Customer xem giá dự kiến trước khi xác nhận Book     | Giá dự kiến được hiển thị                                              | FR-06, AC-04         |
| TC03-003 | Valid         | Customer chọn tiền mặt trước khi Book                | Phương thức thanh toán được ghi nhận                                   | FR-07, BRL-07        |
| TC03-004 | Valid         | Customer chọn điện tử trước khi Book                 | Phương thức thanh toán được ghi nhận                                   | FR-07, BRL-07        |
| TC03-005 | Valid         | Customer Book sau khi chọn phương thức thanh toán    | Booking request được tạo                                               | FR-08, BRL-08        |
| TC03-006 | Valid         | Hệ thống tìm được Driver phù hợp                     | Request được gửi cho Driver phù hợp                                    | FR-11, FR-12, AC-05  |
| TC03-007 | Valid         | Driver chấp nhận chuyến                              | Chuyến được xác nhận và Customer nhận thông tin Driver                 | BRL-12, AC-08        |
| TC03-008 | Valid         | Customer theo dõi trạng thái chuyến                  | Trạng thái chuyến được hiển thị                                        | FR-09, AC-09         |
| TC03-009 | Valid         | Customer theo dõi vị trí Driver                      | Vị trí Driver được cập nhật                                            | FR-17, AC-09         |
| TC03-010 | Valid         | Driver cập nhật ARRIVED                              | Trạng thái chuyến được cập nhật                                        | FR-16, BRL-14        |
| TC03-011 | Valid         | Driver cập nhật PICKED_UP                            | Trạng thái chuyến được cập nhật                                        | FR-16, BRL-14        |
| TC03-012 | Valid         | Driver cập nhật IN_PROGRESS                          | Trạng thái chuyến được cập nhật                                        | FR-16, BRL-14        |
| TC03-013 | Valid         | Driver cập nhật COMPLETED                            | Chuyến được ghi nhận hoàn thành                                        | FR-16, FR-19, AC-11  |
| TC03-014 | Business Rule | Driver từ chối request                               | Hệ thống tiếp tục tìm Driver khác                                      | FR-14, BRL-11, AC-07 |
| TC03-015 | Business Rule | Driver không phản hồi                                | Hệ thống tiếp tục tìm Driver khác; Customer không phải đặt lại yêu cầu | FR-14, BRL-11, AC-07 |
| TC03-016 | Business Rule | Không còn Driver phù hợp                             | Customer được thông báo và quá trình tìm kết thúc                      | FR-13, FR-27, AC-06  |
| TC03-017 | Business Rule | Customer hủy chuyến trong trường hợp policy cho phép | Chuyến được hủy theo policy                                            | FR-18, BRL-13, AC-10 |
| TC03-018 | Invalid       | Customer Book khi thiếu dữ liệu booking bắt buộc     | Request không được tạo                                                 | FR-05, BRL-05, EC-01 |
| TC03-019 | Invalid       | Customer Book khi chưa đăng nhập                     | Booking không được tạo                                                 | BRL-01, EC-17        |
| TC03-020 | Data          | Customer xem lịch sử chuyến                          | Lịch sử chuyến được trả về                                             | FR-10                |

---

# UC04 – THANH TOÁN

| ID       | Tiêu chí      | Test case                                                       | Expected Result                                                   | Trace                        |
| -------- | ------------- | --------------------------------------------------------------- | ----------------------------------------------------------------- | ---------------------------- |
| TC04-001 | Valid         | Chuyến hoàn thành và chọn tiền mặt                              | Customer thanh toán cho Driver                                    | FR-21, BRL-18                |
| TC04-002 | Valid         | Driver xác nhận đã nhận tiền mặt                                | Thanh toán được ghi nhận                                          | FR-22, BRL-19, AC-13         |
| TC04-003 | Valid         | Chuyến hoàn thành và chọn điện tử                               | Giao dịch được gửi đến Payment Gateway                            | FR-23, AC-14                 |
| TC04-004 | Valid         | Payment Gateway trả SUCCESS                                     | Payment được ghi nhận thành công                                  | FR-24, BRL-20, AC-14         |
| TC04-005 | Valid         | Payment Gateway trả FAILED                                      | Payment được ghi nhận thất bại                                    | FR-24, BRL-21                |
| TC04-006 | Valid         | Actual fare đã được xác định và Customer thanh toán điện tử     | Giao dịch được xử lý với số tiền phải thanh toán                  | FR-20, FR-23                 |
| TC04-007 | Business Rule | Customer thanh toán tiền mặt trước khi chuyến hoàn thành        | Không ghi nhận thanh toán hoàn tất                                | FR-21, BRL-18                |
| TC04-008 | Business Rule | Driver xác nhận tiền mặt khi chuyến chưa hoàn thành             | Không ghi nhận xác nhận thanh toán hợp lệ                         | FR-22, BRL-19                |
| TC04-009 | Business Rule | Thanh toán điện tử thất bại và Customer thực hiện lại/xử lý lại | Hệ thống cho phép thực hiện lại/xử lý lại theo chính sách công ty | FR-25, BRL-22, AC-15         |
| TC04-010 | Business Rule | Thanh toán điện tử thất bại                                     | Customer được thông báo kết quả thất bại                          | FR-25, FR-29, AC-15          |
| TC04-011 | Invalid       | Payment Gateway trả kết quả không hợp lệ                        | Kết quả không hợp lệ không được ghi nhận như payment hợp lệ       | FR-24                        |
| TC04-012 | Invalid       | Payment result thiếu dữ liệu bắt buộc theo API                  | Request bị từ chối                                                | FR-24, API Payment           |
| TC04-013 | Exception     | Payment Gateway không phản hồi                                  | Lỗi Payment Gateway được xử lý phù hợp                            | EC-04                        |
| TC04-014 | Exception     | Payment Gateway xảy ra lỗi kết nối                              | Lỗi kết nối được xử lý phù hợp                                    | EC-04                        |
| TC04-015 | Exception     | Thanh toán điện tử thất bại sau chuyến hoàn thành               | Payment thất bại được ghi nhận và Customer được thông báo         | EC-03, FR-25                 |
| TC04-016 | Data          | Kiểm tra trạng thái payment sau SUCCESS                         | Payment status được ghi nhận thành công                           | FR-26, BRL-20                |
| TC04-017 | Data          | Kiểm tra trạng thái payment sau FAILED                          | Payment status được ghi nhận thất bại                             | FR-26, BRL-21                |
| TC04-018 | Data          | Kiểm tra số tiền thanh toán sau actual fare                     | Số tiền thanh toán được ghi nhận phù hợp                          | FR-20, FR-26                 |
| TC04-019 | Consistency   | Thanh toán điện tử chỉ sau khi chuyến hoàn thành                | Payment điện tử không được xử lý trước điều kiện này              | FR-23, BRL-20                |
| TC04-020 | Consistency   | Cash payment sau completion và Driver xác nhận                  | Thanh toán tiền mặt được ghi nhận khi đủ điều kiện                | FR-21, FR-22, BRL-18, BRL-19 |

---

# UC05 – GỬI THÔNG BÁO

| ID       | Tiêu chí      | Test case                                                      | Expected Result                          | Trace                |
| -------- | ------------- | -------------------------------------------------------------- | ---------------------------------------- | -------------------- |
| TC05-001 | Valid         | Driver chấp nhận chuyến                                        | Customer nhận thông tin Driver cần thiết | FR-28, AC-08         |
| TC05-002 | Valid         | Không tìm được Driver                                          | Customer nhận thông báo                  | FR-27, AC-06         |
| TC05-003 | Valid         | Payment điện tử có kết quả                                     | Customer nhận kết quả thanh toán         | FR-29                |
| TC05-004 | Valid         | Chuyến hoàn thành                                              | Customer nhận thông báo hoàn thành       | FR-30, AC-16         |
| TC05-005 | Valid         | Gửi notification đến Customer                                  | Notification được gửi đến đúng Customer  | BRL-23               |
| TC05-006 | Valid         | Gửi notification đến Driver                                    | Notification được gửi đến đúng Driver    | BRL-23               |
| TC05-007 | Business Rule | Driver chấp nhận chuyến                                        | Phát sinh notification cho Customer      | BR-08, BRL-23        |
| TC05-008 | Business Rule | Không tìm được Driver                                          | Phát sinh notification cho Customer      | BR-17, BRL-23        |
| TC05-009 | Business Rule | Payment điện tử FAILED                                         | Phát sinh notification cho Customer      | FR-25, FR-29, BRL-23 |
| TC05-010 | Business Rule | Trip COMPLETED                                                 | Phát sinh notification hoàn thành        | FR-30, BRL-23        |
| TC05-011 | Invalid       | Notification request thiếu recipient theo API                  | Request bị từ chối                       | API Notification     |
| TC05-012 | Invalid       | Notification request thiếu dữ liệu nội dung cần thiết theo API | Request bị từ chối                       | API Notification     |
| TC05-013 | Authorization | User chưa đăng nhập gọi API notification yêu cầu xác thực      | Request bị từ chối                       | BRL-03, FR-41        |
| TC05-014 | Authorization | User truy cập notification không thuộc quyền của mình          | Request bị từ chối                       | BRL-03, FR-41        |
| TC05-015 | Exception     | Notification Provider không phản hồi                           | Lỗi Provider được xử lý phù hợp          | EC-15                |
| TC05-016 | Exception     | Notification Provider trả lỗi gửi                              | Kết quả lỗi được xử lý phù hợp           | EC-15                |
| TC05-017 | Data          | Notification gửi cho Customer                                  | Đúng đối tượng nhận notification         | BRL-23               |
| TC05-018 | Data          | Notification gửi cho Driver                                    | Đúng đối tượng nhận notification         | BRL-23               |
| TC05-019 | Consistency   | Payment FAILED → notification Customer                         | Kết quả payment thất bại được thông báo  | FR-25, FR-29         |
| TC05-020 | Consistency   | Trip COMPLETED → notification completion                       | Sự kiện hoàn thành được thông báo        | FR-30                |

---

# UC06 – ĐÁNH GIÁ TÀI XẾ

| ID       | Tiêu chí      | Test case                                          | Expected Result                                        | Trace                |
| -------- | ------------- | -------------------------------------------------- | ------------------------------------------------------ | -------------------- |
| TC06-001 | Valid         | Customer đánh giá Driver sau chuyến hoàn thành     | Rating được lưu                                        | FR-31, AC-17         |
| TC06-002 | Valid         | Customer gửi rating kèm nội dung                   | Rating và nội dung được lưu                            | FR-31, FR-32         |
| TC06-003 | Valid         | Customer đánh giá Driver của chuyến                | Rating được liên kết với chuyến tương ứng              | FR-32                |
| TC06-004 | Valid         | Customer đánh giá chuyến đã hoàn thành             | Rating được lưu                                        | FR-31, FR-32, BRL-24 |
| TC06-005 | Business Rule | Customer đánh giá khi trip chưa hoàn thành         | Request bị từ chối                                     | BRL-24, EC-16        |
| TC06-006 | Business Rule | Customer đánh giá trip chưa hoàn thành             | Request bị từ chối                                     | BRL-24, EC-16        |
| TC06-007 | Business Rule | Customer đánh giá sau completion                   | Cho phép đánh giá                                      | BRL-24               |
| TC06-008 | Data          | Kiểm tra thông tin liên kết của rating sau khi lưu | Rating được liên kết đúng với trip, Customer và Driver | FR-32                |
| TC06-009 | Invalid       | Thiếu dữ liệu rating bắt buộc theo API             | Request bị từ chối                                     | FR-31, API Rating    |
| TC06-010 | Invalid       | TripId không tồn tại khi gửi rating                | Request bị từ chối                                     | FR-32                |
| TC06-011 | Authorization | Customer khác đánh giá trip không thuộc mình       | Request bị từ chối                                     | BRL-03, FR-32        |
| TC06-012 | Authorization | Driver tự thực hiện chức năng đánh giá             | Request bị từ chối                                     | BRL-03               |
| TC06-013 | Authorization | User chưa đăng nhập gửi rating                     | Request bị từ chối                                     | BRL-03, FR-41        |
| TC06-014 | Data          | Kiểm tra rating được liên kết với đúng trip        | Rating liên kết đúng trip                              | FR-32                |
| TC06-015 | Data          | Kiểm tra rating thuộc Customer thực hiện đánh giá  | Rating thuộc đúng Customer                             | FR-31, FR-32         |
| TC06-016 | Data          | Kiểm tra rating liên quan đúng Driver              | Rating liên quan Driver của chuyến                     | FR-32                |
| TC06-017 | Data          | Kiểm tra nội dung rating được lưu                  | Nội dung được lưu đúng                                 | FR-32                |
| TC06-018 | Exception     | Rating gửi cho trip không xác định được            | Không tạo rating sai đối tượng                         | FR-32, EC-16         |
| TC06-019 | Consistency   | Trip hoàn thành → Customer được phép rating        | Luồng rating đúng điều kiện                            | BRL-24               |
| TC06-020 | Consistency   | Rating sau completion được lưu vào hệ thống        | Rating được lưu đúng                                   | FR-31, FR-32         |

---

# UC07 – QUẢN LÝ VẬN HÀNH

| ID       | Tiêu chí      | Test case                                            | Expected Result                                                        | Trace            |
| -------- | ------------- | ---------------------------------------------------- | ---------------------------------------------------------------------- | ---------------- |
| TC07-001 | Valid         | Operator xem danh sách phương tiện                   | Danh sách phương tiện được hiển thị                                    | FR-35, BR-10     |
| TC07-002 | Valid         | Operator tra cứu phương tiện                         | Thông tin phương tiện phù hợp được trả về                              | FR-35            |
| TC07-003 | Valid         | Operator xem danh sách chuyến                        | Danh sách chuyến được hiển thị                                         | FR-36, BR-10     |
| TC07-004 | Valid         | Operator tra cứu một chuyến                          | Thông tin chuyến được hiển thị                                         | FR-36            |
| TC07-005 | Valid         | Operator theo dõi trạng thái chuyến                  | Trạng thái chuyến được cung cấp                                        | FR-36            |
| TC07-006 | Valid         | Operator ghi nhận/xử lý sự cố liên quan chuyến       | Sự cố được ghi nhận/xử lý                                              | FR-37, BR-16     |
| TC07-007 | Business Rule | Operator thực hiện chức năng vận hành được cấp quyền | Chức năng được thực hiện                                               | BRL-03, FR-41    |
| TC07-008 | Business Rule | Operator theo dõi chuyến đang thực hiện              | Thông tin chuyến được cung cấp                                         | FR-36            |
| TC07-009 | Invalid       | Tra cứu phương tiện không tồn tại                    | Không trả dữ liệu phương tiện không tồn tại                            | FR-35            |
| TC07-010 | Invalid       | Tra cứu chuyến không tồn tại                         | Không trả dữ liệu chuyến không tồn tại                                 | FR-36            |
| TC07-011 | Invalid       | Ghi nhận sự cố bằng dữ liệu không hợp lệ theo API    | Request bị từ chối                                                     | FR-37, API Admin |
| TC07-012 | Authorization | Customer truy cập chức năng vận hành                 | Request bị từ chối                                                     | BRL-03, FR-41    |
| TC07-013 | Authorization | Driver truy cập chức năng vận hành của Operator      | Request bị từ chối                                                     | BRL-03, FR-41    |
| TC07-014 | Authorization | Operator không có permission thực hiện chức năng     | Request bị từ chối                                                     | FR-41            |
| TC07-015 | Authorization | User không có quyền truy cập chức năng vận hành      | Request bị từ chối                                                     | FR-41            |
| TC07-016 | Exception     | Component quản lý chuyến gặp lỗi                     | Chức năng không liên quan tiếp tục hoạt động theo yêu cầu của hệ thống | EC-18            |
| TC07-017 | Exception     | Component quản lý phương tiện gặp lỗi                | Chức năng không liên quan tiếp tục hoạt động theo yêu cầu của hệ thống | EC-18            |
| TC07-018 | Data          | Operator tra cứu thông tin phương tiện               | Dữ liệu phương tiện được trả về phù hợp                                | FR-35            |
| TC07-019 | Data          | Operator tra cứu thông tin chuyến                    | Dữ liệu chuyến được trả về phù hợp                                     | FR-36            |
| TC07-020 | Audit         | Operator thực hiện thao tác quan trọng               | Thao tác được ghi nhận để truy vết                                     | FR-42            |

---

# UC08 – XỬ LÝ SỰ CỐ

| ID       | Tiêu chí      | Test case                                                          | Expected Result                              | Trace            |
| -------- | ------------- | ------------------------------------------------------------------ | -------------------------------------------- | ---------------- |
| TC08-001 | Valid         | Operator ghi nhận sự cố liên quan chuyến đi                        | Sự cố được ghi nhận                          | FR-37            |
| TC08-002 | Valid         | Operator xử lý sự cố liên quan chuyến đi                           | Thao tác xử lý sự cố được thực hiện          | FR-37, BR-16     |
| TC08-003 | Valid         | Operator ghi nhận trường hợp mất kết nối trong quá trình chuyến đi | Sự cố được ghi nhận để Operator xử lý        | FR-37, EC-09     |
| TC08-004 | Valid         | Operator ghi nhận trường hợp không tính được cước thực tế          | Sự cố được ghi nhận để xử lý                 | FR-37, EC-12     |
| TC08-005 | Valid         | Operator ghi nhận trường hợp chưa thanh toán tiền mặt              | Sự cố được ghi nhận để xử lý                 | FR-37, EC-13     |
| TC08-006 | Valid         | Operator ghi nhận trường hợp Driver chưa xác nhận tiền mặt         | Sự cố được ghi nhận để xử lý                 | FR-37, EC-14     |
| TC08-007 | Business Rule | Operator xử lý sự cố khi có quyền phù hợp                          | Thao tác được phép thực hiện                 | FR-41            |
| TC08-008 | Business Rule | Operator ghi nhận sự cố của một chuyến cụ thể                      | Sự cố được ghi nhận gắn với thông tin chuyến | FR-37            |
| TC08-009 | Invalid       | Ghi nhận sự cố bằng dữ liệu không hợp lệ theo API                  | Request bị từ chối                           | FR-37, API Admin |
| TC08-010 | Invalid       | Ghi nhận sự cố cho trip không tồn tại                              | Request bị từ chối                           | FR-37            |
| TC08-011 | Authorization | Customer thực hiện chức năng xử lý sự cố                           | Request bị từ chối                           | BRL-03, FR-41    |
| TC08-012 | Authorization | Driver thực hiện chức năng xử lý sự cố của Operator                | Request bị từ chối                           | BRL-03, FR-41    |
| TC08-013 | Authorization | Operator không có permission xử lý sự cố                           | Request bị từ chối                           | FR-41            |
| TC08-014 | Authorization | User không có quyền thực hiện xử lý sự cố                          | Request bị từ chối                           | FR-41            |
| TC08-015 | Exception     | Trip bị mất kết nối trong quá trình thực hiện                      | Sự cố được ghi nhận để Operator xử lý        | EC-09, FR-37     |
| TC08-016 | Exception     | Không cập nhật được location                                       | Sự cố được ghi nhận để Operator xử lý        | EC-10, FR-37     |
| TC08-017 | Exception     | Không cập nhật được trip status                                    | Sự cố được ghi nhận để Operator xử lý        | EC-11, FR-37     |
| TC08-018 | Exception     | Notification Provider lỗi                                          | Lỗi được ghi nhận để Operator xử lý          | EC-15, FR-37     |
| TC08-019 | Exception     | Component hệ thống gặp lỗi                                         | Trường hợp lỗi được ghi nhận để xử lý        | EC-18            |
| TC08-020 | Audit         | Operator xử lý sự cố                                               | Thao tác được ghi nhận để truy vết           | FR-42            |

---

# UC09 – QUẢN LÝ BÁO CÁO HOẠT ĐỘNG

| ID       | Tiêu chí      | Test case                                          | Expected Result                            | Trace              |
| -------- | ------------- | -------------------------------------------------- | ------------------------------------------ | ------------------ |
| TC09-001 | Valid         | Manager xem báo cáo hoạt động                      | Báo cáo được trả về                        | FR-38              |
| TC09-002 | Valid         | Manager xem tổng số chuyến                         | Tổng số chuyến được cung cấp               | FR-38              |
| TC09-003 | Valid         | Manager xem tổng doanh thu                         | Tổng doanh thu được cung cấp               | FR-38              |
| TC09-004 | Valid         | Manager xem tỷ lệ hoàn thành                       | Tỷ lệ hoàn thành được cung cấp             | FR-38              |
| TC09-005 | Valid         | Manager xem tỷ lệ hủy                              | Tỷ lệ hủy được cung cấp                    | FR-38              |
| TC09-006 | Valid         | Manager xem hiệu quả Driver                        | Thông tin hiệu quả Driver được cung cấp    | FR-38              |
| TC09-007 | Valid         | Manager xem báo cáo theo khoảng thời gian hợp lệ   | Báo cáo được trả về theo khoảng thời gian  | FR-38, API Reports |
| TC09-008 | Valid         | Manager xem báo cáo business                       | Báo cáo business được trả về               | FR-39, BR-12       |
| TC09-009 | API           | Gọi endpoint báo cáo không truyền khoảng thời gian | API xử lý theo contract đã chốt            | API Reports        |
| TC09-010 | Invalid       | Khoảng thời gian báo cáo không hợp lệ theo API     | Request bị từ chối                         | API Reports        |
| TC09-011 | Invalid       | Request báo cáo không hợp lệ theo API              | API trả lỗi phù hợp                        | API Reports        |
| TC09-012 | Authorization | Customer truy cập báo cáo Manager                  | Request bị từ chối                         | FR-41, API Reports |
| TC09-013 | Authorization | Driver truy cập báo cáo Manager                    | Request bị từ chối                         | FR-41, API Reports |
| TC09-014 | Authorization | User không có quyền Manager gọi endpoint Manager   | Request bị từ chối                         | FR-41, API Reports |
| TC09-015 | Authorization | Operator gọi endpoint chỉ dành cho Manager         | Request bị từ chối                         | FR-41, API Reports |
| TC09-016 | Data          | Báo cáo có dữ liệu chuyến                          | Các chỉ số chuyến được cung cấp            | FR-38              |
| TC09-017 | Data          | Báo cáo có dữ liệu doanh thu                       | Tổng doanh thu được cung cấp               | FR-38              |
| TC09-018 | Data          | Báo cáo có dữ liệu Driver                          | Thông tin Driver performance được cung cấp | FR-38              |
| TC09-019 | API           | Khoảng thời gian không có dữ liệu                  | API trả response theo contract đã chốt     | API Reports        |
| TC09-020 | Exception     | Report service gặp lỗi                             | API trả lỗi phù hợp                        | API Reports        |

---

# UC10 – TRA CỨU LỊCH SỬ GIAO DỊCH

| ID       | Tiêu chí      | Test case                                            | Expected Result                      | Trace         |
| -------- | ------------- | ---------------------------------------------------- | ------------------------------------ | ------------- |
| TC10-001 | Valid         | Operator tra cứu lịch sử giao dịch                   | Lịch sử giao dịch được trả về        | FR-40, BR-12  |
| TC10-002 | Valid         | Operator tra cứu giao dịch liên quan một trip        | Giao dịch phù hợp được trả về        | FR-40         |
| TC10-003 | Valid         | Tra cứu giao dịch thành công                         | Giao dịch thành công được hiển thị   | FR-40         |
| TC10-004 | Valid         | Tra cứu giao dịch thất bại                           | Giao dịch thất bại được hiển thị     | FR-40         |
| TC10-005 | Valid         | Tra cứu lịch sử có nhiều giao dịch                   | Các giao dịch phù hợp được trả về    | FR-40         |
| TC10-006 | Invalid       | Tra cứu trip không tồn tại                           | Không trả giao dịch không tồn tại    | FR-40         |
| TC10-007 | Invalid       | Request tra cứu không hợp lệ theo API                | Request bị từ chối                   | API Admin     |
| TC10-008 | Authorization | Customer truy cập lịch sử giao dịch Operator         | Request bị từ chối                   | BRL-03, FR-41 |
| TC10-009 | Authorization | Driver truy cập lịch sử giao dịch Operator           | Request bị từ chối                   | BRL-03, FR-41 |
| TC10-010 | Authorization | Operator không có permission tra cứu                 | Request bị từ chối                   | FR-41         |
| TC10-011 | Authorization | User không có quyền Operator tra cứu                 | Request bị từ chối                   | FR-41         |
| TC10-012 | Data          | Lịch sử phản ánh payment SUCCESS                     | Giao dịch thành công được phản ánh   | FR-40, FR-26  |
| TC10-013 | Data          | Lịch sử phản ánh payment FAILED                      | Giao dịch thất bại được phản ánh     | FR-40, FR-26  |
| TC10-014 | Data          | Giao dịch được tra cứu theo trip                     | Giao dịch tương ứng trip được trả về | FR-40         |
| TC10-015 | Data          | Tra cứu lịch sử không làm thay đổi dữ liệu giao dịch | Dữ liệu giao dịch không bị thay đổi  | FR-40         |
| TC10-016 | Consistency   | Payment SUCCESS → tra cứu lịch sử                    | Lịch sử phản ánh kết quả thành công  | FR-24, FR-40  |
| TC10-017 | Consistency   | Payment FAILED → tra cứu lịch sử                     | Lịch sử phản ánh kết quả thất bại    | FR-24, FR-40  |
| TC10-018 | Exception     | Transaction service gặp lỗi                          | API trả lỗi phù hợp                  | API Admin     |
| TC10-019 | Audit         | Operator thực hiện tra cứu giao dịch                 | Thao tác được ghi nhận để truy vết   | FR-42         |
| TC10-020 | Data          | Tra cứu lại cùng giao dịch                           | Kết quả nhất quán với dữ liệu đã lưu | FR-40         |

---

# UC11 – QUẢN LÝ KHÁCH HÀNG

| ID       | Tiêu chí      | Test case                                            | Expected Result                                  | Trace            |
| -------- | ------------- | ---------------------------------------------------- | ------------------------------------------------ | ---------------- |
| TC11-001 | Valid         | Operator xem danh sách Customer                      | Danh sách Customer được trả về                   | FR-33, BR-10     |
| TC11-002 | Valid         | Operator tra cứu Customer                            | Customer phù hợp được trả về                     | FR-33            |
| TC11-003 | Valid         | Operator xem thông tin Customer                      | Thông tin Customer được hiển thị                 | FR-33            |
| TC11-004 | Valid         | Operator quản lý Customer                            | Customer được quản lý theo quyền                 | FR-33, BR-10     |
| TC11-005 | Business Rule | Operator thực hiện quản lý Customer theo permission  | Chức năng được thực hiện khi có quyền            | BRL-03, FR-41    |
| TC11-006 | Invalid       | Tra cứu Customer không tồn tại                       | Không tìm thấy Customer                          | FR-33            |
| TC11-007 | Invalid       | Cập nhật Customer bằng dữ liệu không hợp lệ theo API | Request bị từ chối                               | FR-33, API Admin |
| TC11-008 | Authorization | Customer truy cập chức năng quản lý Customer         | Request bị từ chối                               | BRL-03, FR-41    |
| TC11-009 | Authorization | Driver truy cập chức năng quản lý Customer           | Request bị từ chối                               | BRL-03, FR-41    |
| TC11-010 | Authorization | Operator không có permission quản lý Customer        | Request bị từ chối                               | FR-41            |
| TC11-011 | Authorization | User không có quyền quản lý Customer                 | Request bị từ chối                               | FR-41            |
| TC11-012 | Data          | Customer được lưu đúng thông tin tài khoản           | Dữ liệu Customer được trả về đúng                | BR-01            |
| TC11-013 | Data          | Operator quản lý Customer đã tồn tại                 | Dữ liệu Customer tương ứng được xử lý            | FR-33            |
| TC11-014 | Data          | Operator tra cứu Customer sau khi cập nhật           | Dữ liệu mới được hiển thị                        | FR-33            |
| TC11-015 | Consistency   | Customer được cập nhật thành công                    | Thông tin sau cập nhật nhất quán với dữ liệu lưu | FR-33            |
| TC11-016 | Consistency   | Customer tồn tại được Operator tra cứu               | Kết quả tra cứu đúng Customer                    | FR-33            |
| TC11-017 | Exception     | Customer service trả lỗi                             | API trả lỗi phù hợp                              | API Admin        |
| TC11-018 | Audit         | Operator cập nhật Customer                           | Thao tác được ghi nhận để truy vết               | FR-42            |
| TC11-019 | Audit         | Operator tra cứu Customer                            | Thao tác quan trọng được truy vết                | FR-42            |
| TC11-020 | Authorization | Operator không được cấp quyền quản lý Customer       | Request bị từ chối                               | FR-41, AC-20     |

---

# UC12 – QUẢN LÝ TÀI XẾ

| ID       | Tiêu chí      | Test case                                             | Expected Result                        | Trace                     |
| -------- | ------------- | ----------------------------------------------------- | -------------------------------------- | ------------------------- |
| TC12-001 | Valid         | Operator xem danh sách Driver                         | Danh sách Driver được trả về           | FR-34, BR-10              |
| TC12-002 | Valid         | Operator tra cứu Driver                               | Driver phù hợp được trả về             | FR-34                     |
| TC12-003 | Valid         | Operator xem thông tin Driver                         | Thông tin Driver được hiển thị         | FR-34                     |
| TC12-004 | Valid         | Operator quản lý Driver                               | Driver được quản lý theo quyền         | FR-34, BR-10              |
| TC12-005 | Valid         | Operator tạo tài khoản Driver                         | Tài khoản Driver được tạo              | FR-01                     |
| TC12-006 | Valid         | Driver tự đăng ký tài khoản                           | Tài khoản Driver được tạo              | FR-01                     |
| TC12-007 | Business Rule | Driver cập nhật hồ sơ sau khi tạo tài khoản           | Hồ sơ Driver được cập nhật             | FR-03, BR-15              |
| TC12-008 | Business Rule | Driver cập nhật vehicle/readiness                     | Thông tin được cập nhật                | FR-04, BR-15              |
| TC12-009 | Business Rule | Operator quản lý Driver theo permission               | Chức năng được thực hiện khi có quyền  | FR-41                     |
| TC12-010 | Invalid       | Tra cứu Driver không tồn tại                          | Không tìm thấy Driver                  | FR-34                     |
| TC12-011 | Invalid       | Tạo Driver bằng dữ liệu không hợp lệ theo API         | Request bị từ chối                     | FR-01, API Authentication |
| TC12-012 | Invalid       | Cập nhật Driver bằng dữ liệu không hợp lệ theo API    | Request bị từ chối                     | FR-34, API Admin          |
| TC12-013 | Authorization | Customer quản lý Driver                               | Request bị từ chối                     | BRL-03, FR-41             |
| TC12-014 | Authorization | Driver truy cập chức năng quản lý Driver của Operator | Request bị từ chối                     | BRL-03, FR-41             |
| TC12-015 | Authorization | Operator không có permission quản lý Driver           | Request bị từ chối                     | FR-41                     |
| TC12-016 | Authorization | User không có quyền quản lý Driver                    | Request bị từ chối                     | FR-41                     |
| TC12-017 | Data          | Operator quản lý Driver và thông tin hồ sơ Driver     | Thông tin Driver được trả về phù hợp   | FR-34, BR-15              |
| TC12-018 | Data          | Driver có trạng thái readiness                        | Trạng thái readiness được lưu/cập nhật | FR-04, BRL-02             |
| TC12-019 | Consistency   | Driver được Operator tạo sau đó đăng nhập             | Tài khoản Driver hoạt động đúng        | FR-01, FR-02              |
| TC12-020 | Audit         | Operator cập nhật Driver                              | Thao tác được ghi nhận để truy vết     | FR-42                     |

---

