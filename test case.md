
# UC01 – QUẢN LÝ TÀI KHOẢN

| ID       | Tiêu chí     | Test case                                                      | Kết quả mong đợi                   | Trace               |
| -------- | ------------ | -------------------------------------------------------------- | ---------------------------------- | ------------------- |
| TC01-001 | Hợp lệ       | Khách hàng đăng ký tài khoản hợp lệ                            | Tài khoản khách hàng được tạo      | FR-01, BR-01, AC-01 |
| TC01-002 | Hợp lệ       | Tài xế tự đăng ký tài khoản hợp lệ                             | Tài khoản tài xế được tạo          | FR-01, BR-15, AC-01 |
| TC01-003 | Hợp lệ       | Nhân viên vận hành tạo tài khoản tài xế                        | Tài khoản tài xế được tạo          | FR-01, BR-15, AC-01 |
| TC01-004 | Hợp lệ       | Khách hàng đăng nhập bằng thông tin hợp lệ                     | Đăng nhập thành công               | FR-02, AC-01        |
| TC01-005 | Hợp lệ       | Tài xế đăng nhập bằng thông tin hợp lệ                         | Đăng nhập thành công               | FR-02, AC-01        |
| TC01-006 | Hợp lệ       | Nhân viên vận hành đăng nhập bằng thông tin hợp lệ             | Đăng nhập thành công               | FR-02, AC-01        |
| TC01-007 | Hợp lệ       | Người dùng xem thông tin cá nhân                               | Thông tin cá nhân được hiển thị    | FR-03               |
| TC01-008 | Hợp lệ       | Người dùng cập nhật thông tin cá nhân hợp lệ                   | Thông tin cá nhân được cập nhật    | FR-03               |
| TC01-009 | Không hợp lệ | Đăng nhập bằng thông tin xác thực không hợp lệ                 | Đăng nhập thất bại                 | FR-02, EC-17        |
| TC01-010 | Không hợp lệ | Đăng ký bằng dữ liệu không hợp lệ theo API                     | Yêu cầu bị từ chối                 | FR-01, API Xác thực |
| TC01-011 | Không hợp lệ | Cập nhật hồ sơ bằng dữ liệu không hợp lệ theo API              | Yêu cầu bị từ chối                 | FR-03, API Xác thực |
| TC01-012 | Phân quyền   | Khách hàng truy cập chức năng không thuộc quyền                | Yêu cầu bị từ chối                 | BRL-03, FR-41       |
| TC01-013 | Phân quyền   | Tài xế truy cập chức năng không thuộc quyền                    | Yêu cầu bị từ chối                 | BRL-03, FR-41       |
| TC01-014 | Phân quyền   | Nhân viên vận hành truy cập chức năng không được cấp quyền     | Yêu cầu bị từ chối                 | BRL-03, FR-41       |
| TC01-015 | Ngoại lệ     | Người dùng chưa đăng nhập thực hiện chức năng yêu cầu xác thực | Yêu cầu bị từ chối                 | BRL-01, EC-17       |
| TC01-016 | Ngoại lệ     | Thông tin xác thực không hợp lệ khi gọi API yêu cầu đăng nhập  | Yêu cầu bị từ chối                 | FR-02, API Xác thực |
| TC01-017 | Dữ liệu      | Kiểm tra dữ liệu sau khi cập nhật hồ sơ                        | Dữ liệu mới được lưu đúng          | FR-03               |
| TC01-018 | Dữ liệu      | Kiểm tra loại tài khoản sau khi tạo                            | Tài khoản được tạo đúng vai trò    | FR-01, BRL-03       |
| TC01-019 | Kiểm toán    | Người dùng thực hiện thao tác quan trọng trên tài khoản        | Thao tác được ghi nhận để truy vết | FR-42               |
| TC01-020 | Nhất quán    | Người dùng đăng nhập sau khi tài khoản được tạo                | Tài khoản vừa tạo đăng nhập được   | FR-01, FR-02, AC-01 |

---

# UC02 – QUẢN LÝ HỒ SƠ TÀI XẾ

| ID       | Tiêu chí          | Test case                                                        | Kết quả mong đợi                                | Trace               |
| -------- | ----------------- | ---------------------------------------------------------------- | ----------------------------------------------- | ------------------- |
| TC02-001 | Hợp lệ            | Tài xế xem hồ sơ cá nhân                                         | Hồ sơ tài xế được hiển thị                      | FR-03, BR-15        |
| TC02-002 | Hợp lệ            | Tài xế cập nhật thông tin cá nhân                                | Hồ sơ được cập nhật                             | FR-03, BR-15        |
| TC02-003 | Hợp lệ            | Tài xế xem thông tin phương tiện                                 | Thông tin phương tiện được hiển thị             | FR-04               |
| TC02-004 | Hợp lệ            | Tài xế cập nhật thông tin phương tiện                            | Thông tin phương tiện được cập nhật             | FR-04               |
| TC02-005 | Hợp lệ            | Tài xế chuyển sang trạng thái SẴN SÀNG                           | Trạng thái sẵn sàng được cập nhật               | FR-04, BRL-02       |
| TC02-006 | Hợp lệ            | Tài xế chuyển sang trạng thái KHÔNG SẴN SÀNG                     | Trạng thái sẵn sàng được cập nhật               | FR-04               |
| TC02-007 | Quy tắc nghiệp vụ | Tài xế cập nhật trạng thái sẵn sàng trước khi nhận yêu cầu       | Trạng thái sẵn sàng được sử dụng khi xét tài xế | FR-04, BRL-02       |
| TC02-008 | Quy tắc nghiệp vụ | Tài xế ở trạng thái KHÔNG SẴN SÀNG khi hệ thống tìm tài xế       | Tài xế không được xem là tài xế phù hợp         | FR-11, BRL-02       |
| TC02-009 | Không hợp lệ      | Cập nhật hồ sơ bằng dữ liệu không hợp lệ theo API                | Yêu cầu bị từ chối                              | FR-03, API Xác thực |
| TC02-010 | Không hợp lệ      | Cập nhật phương tiện bằng dữ liệu không hợp lệ theo API          | Yêu cầu bị từ chối                              | FR-04, API Xác thực |
| TC02-011 | Phân quyền        | Khách hàng truy cập chức năng quản lý hồ sơ tài xế               | Yêu cầu bị từ chối                              | BRL-03, FR-41       |
| TC02-012 | Phân quyền        | Tài xế truy cập phương tiện không thuộc phạm vi quản lý của mình | Yêu cầu bị từ chối                              | FR-04, BR-15        |
| TC02-013 | Ngoại lệ          | Tài xế cập nhật phương tiện không tồn tại                        | Yêu cầu bị từ chối                              | FR-04               |
| TC02-014 | Dữ liệu           | Kiểm tra thông tin phương tiện sau khi cập nhật                  | Dữ liệu phương tiện được lưu đúng               | FR-04               |
| TC02-015 | Dữ liệu           | Kiểm tra trạng thái sẵn sàng sau khi cập nhật                    | Trạng thái sẵn sàng được lưu đúng               | FR-04               |
| TC02-016 | Dữ liệu           | Kiểm tra thông tin phương tiện thuộc tài xế sau khi cập nhật     | Thông tin phương tiện được quản lý đúng tài xế  | FR-04, BR-15        |
| TC02-017 | Nhất quán         | Tài xế chuyển sang SẴN SÀNG rồi hệ thống tìm tài xế              | Tài xế có thể được xét trong quá trình tìm      | FR-11, BRL-02       |
| TC02-018 | Nhất quán         | Tài xế chuyển sang KHÔNG SẴN SÀNG rồi hệ thống tìm tài xế        | Tài xế không được chọn khi không phù hợp        | FR-11, BRL-02       |
| TC02-019 | Kiểm toán         | Tài xế cập nhật thông tin quan trọng                             | Thao tác được ghi nhận để truy vết              | FR-42               |
| TC02-020 | Tích hợp          | Thông tin tài xế được sử dụng trong quá trình phân công          | Hệ thống sử dụng thông tin tài xế phù hợp       | FR-04, FR-11        |

---

# UC03 – QUẢN LÝ CHUYẾN ĐI

| ID       | Tiêu chí          | Test case                                                  | Kết quả mong đợi                                                         | Trace                |
| -------- | ----------------- | ---------------------------------------------------------- | ------------------------------------------------------------------------ | -------------------- |
| TC03-001 | Hợp lệ            | Khách hàng nhập điểm đón, điểm đến, loại xe và đặt xe      | Yêu cầu đặt xe được tạo                                                  | FR-05, FR-08, AC-03  |
| TC03-002 | Hợp lệ            | Khách hàng xem giá dự kiến trước khi xác nhận đặt xe       | Giá dự kiến được hiển thị                                                | FR-06, AC-04         |
| TC03-003 | Hợp lệ            | Khách hàng chọn tiền mặt trước khi đặt xe                  | Phương thức thanh toán được ghi nhận                                     | FR-07, BRL-07        |
| TC03-004 | Hợp lệ            | Khách hàng chọn thanh toán điện tử trước khi đặt xe        | Phương thức thanh toán được ghi nhận                                     | FR-07, BRL-07        |
| TC03-005 | Hợp lệ            | Khách hàng đặt xe sau khi chọn phương thức thanh toán      | Yêu cầu đặt xe được tạo                                                  | FR-08, BRL-08        |
| TC03-006 | Hợp lệ            | Hệ thống tìm được tài xế phù hợp                           | Yêu cầu được gửi cho tài xế phù hợp                                      | FR-11, FR-12, AC-05  |
| TC03-007 | Hợp lệ            | Tài xế chấp nhận chuyến                                    | Chuyến được xác nhận và khách hàng nhận thông tin tài xế                 | BRL-12, AC-08        |
| TC03-008 | Hợp lệ            | Khách hàng theo dõi trạng thái chuyến                      | Trạng thái chuyến được hiển thị                                          | FR-09, AC-09         |
| TC03-009 | Hợp lệ            | Khách hàng theo dõi vị trí tài xế                          | Vị trí tài xế được cập nhật                                              | FR-17, AC-09         |
| TC03-010 | Hợp lệ            | Tài xế cập nhật trạng thái ĐÃ ĐẾN                          | Trạng thái chuyến được cập nhật                                          | FR-16, BRL-14        |
| TC03-011 | Hợp lệ            | Tài xế cập nhật trạng thái ĐÃ ĐÓN KHÁCH                    | Trạng thái chuyến được cập nhật                                          | FR-16, BRL-14        |
| TC03-012 | Hợp lệ            | Tài xế cập nhật trạng thái ĐANG THỰC HIỆN CHUYẾN           | Trạng thái chuyến được cập nhật                                          | FR-16, BRL-14        |
| TC03-013 | Hợp lệ            | Tài xế cập nhật trạng thái HOÀN THÀNH                      | Chuyến được ghi nhận hoàn thành                                          | FR-16, FR-19, AC-11  |
| TC03-014 | Quy tắc nghiệp vụ | Tài xế từ chối yêu cầu                                     | Hệ thống tiếp tục tìm tài xế khác                                        | FR-14, BRL-11, AC-07 |
| TC03-015 | Quy tắc nghiệp vụ | Tài xế không phản hồi                                      | Hệ thống tiếp tục tìm tài xế khác; khách hàng không phải đặt lại yêu cầu | FR-14, BRL-11, AC-07 |
| TC03-016 | Quy tắc nghiệp vụ | Không còn tài xế phù hợp                                   | Khách hàng được thông báo và quá trình tìm kết thúc                      | FR-13, FR-27, AC-06  |
| TC03-017 | Quy tắc nghiệp vụ | Khách hàng hủy chuyến trong trường hợp chính sách cho phép | Chuyến được hủy theo chính sách                                          | FR-18, BRL-13, AC-10 |
| TC03-018 | Không hợp lệ      | Khách hàng đặt xe khi thiếu dữ liệu đặt xe bắt buộc        | Yêu cầu không được tạo                                                   | FR-05, BRL-05, EC-01 |
| TC03-019 | Không hợp lệ      | Khách hàng đặt xe khi chưa đăng nhập                       | Đặt xe không được thực hiện                                              | BRL-01, EC-17        |
| TC03-020 | Dữ liệu           | Khách hàng xem lịch sử chuyến                              | Lịch sử chuyến được trả về                                               | FR-10                |

---

# UC04 – THANH TOÁN

| ID       | Tiêu chí          | Test case                                                         | Kết quả mong đợi                                                  | Trace                        |
| -------- | ----------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- | ---------------------------- |
| TC04-001 | Hợp lệ            | Chuyến hoàn thành và chọn tiền mặt                                | Khách hàng thanh toán cho tài xế                                  | FR-21, BRL-18                |
| TC04-002 | Hợp lệ            | Tài xế xác nhận đã nhận tiền mặt                                  | Thanh toán được ghi nhận                                          | FR-22, BRL-19, AC-13         |
| TC04-003 | Hợp lệ            | Chuyến hoàn thành và chọn thanh toán điện tử                      | Giao dịch được gửi đến Cổng thanh toán                            | FR-23, AC-14                 |
| TC04-004 | Hợp lệ            | Cổng thanh toán trả kết quả THÀNH CÔNG                            | Thanh toán được ghi nhận thành công                               | FR-24, BRL-20, AC-14         |
| TC04-005 | Hợp lệ            | Cổng thanh toán trả kết quả THẤT BẠI                              | Thanh toán được ghi nhận thất bại                                 | FR-24, BRL-21                |
| TC04-006 | Hợp lệ            | Cước thực tế đã được xác định và khách hàng thanh toán điện tử    | Giao dịch được xử lý với số tiền phải thanh toán                  | FR-20, FR-23                 |
| TC04-007 | Quy tắc nghiệp vụ | Khách hàng thanh toán tiền mặt trước khi chuyến hoàn thành        | Không ghi nhận thanh toán hoàn tất                                | FR-21, BRL-18                |
| TC04-008 | Quy tắc nghiệp vụ | Tài xế xác nhận tiền mặt khi chuyến chưa hoàn thành               | Không ghi nhận xác nhận thanh toán hợp lệ                         | FR-22, BRL-19                |
| TC04-009 | Quy tắc nghiệp vụ | Thanh toán điện tử thất bại và khách hàng thực hiện lại/xử lý lại | Hệ thống cho phép thực hiện lại/xử lý lại theo chính sách công ty | FR-25, BRL-22, AC-15         |
| TC04-010 | Quy tắc nghiệp vụ | Thanh toán điện tử thất bại                                       | Khách hàng được thông báo kết quả thất bại                        | FR-25, FR-29, AC-15          |
| TC04-011 | Không hợp lệ      | Cổng thanh toán trả kết quả không hợp lệ                          | Kết quả không hợp lệ không được ghi nhận như thanh toán hợp lệ    | FR-24                        |
| TC04-012 | Không hợp lệ      | Kết quả thanh toán thiếu dữ liệu bắt buộc theo API                | Yêu cầu bị từ chối                                                | FR-24, API Thanh toán        |
| TC04-013 | Ngoại lệ          | Cổng thanh toán không phản hồi                                    | Lỗi Cổng thanh toán được xử lý phù hợp                            | EC-04                        |
| TC04-014 | Ngoại lệ          | Cổng thanh toán xảy ra lỗi kết nối                                | Lỗi kết nối được xử lý phù hợp                                    | EC-04                        |
| TC04-015 | Ngoại lệ          | Thanh toán điện tử thất bại sau khi chuyến hoàn thành             | Thanh toán thất bại được ghi nhận và khách hàng được thông báo    | EC-03, FR-25                 |
| TC04-016 | Dữ liệu           | Kiểm tra trạng thái thanh toán sau kết quả THÀNH CÔNG             | Trạng thái thanh toán được ghi nhận thành công                    | FR-26, BRL-20                |
| TC04-017 | Dữ liệu           | Kiểm tra trạng thái thanh toán sau kết quả THẤT BẠI               | Trạng thái thanh toán được ghi nhận thất bại                      | FR-26, BRL-21                |
| TC04-018 | Dữ liệu           | Kiểm tra số tiền thanh toán sau khi xác định cước thực tế         | Số tiền thanh toán được ghi nhận phù hợp                          | FR-20, FR-26                 |
| TC04-019 | Nhất quán         | Thanh toán điện tử chỉ được thực hiện sau khi chuyến hoàn thành   | Thanh toán điện tử không được xử lý trước điều kiện này           | FR-23, BRL-20                |
| TC04-020 | Nhất quán         | Thanh toán tiền mặt sau khi hoàn thành và tài xế xác nhận         | Thanh toán tiền mặt được ghi nhận khi đủ điều kiện                | FR-21, FR-22, BRL-18, BRL-19 |

---

# UC05 – GỬI THÔNG BÁO

| ID       | Tiêu chí          | Test case                                                       | Kết quả mong đợi                           | Trace                |
| -------- | ----------------- | --------------------------------------------------------------- | ------------------------------------------ | -------------------- |
| TC05-001 | Hợp lệ            | Tài xế chấp nhận chuyến                                         | Khách hàng nhận thông tin tài xế cần thiết | FR-28, AC-08         |
| TC05-002 | Hợp lệ            | Không tìm được tài xế                                           | Khách hàng nhận thông báo                  | FR-27, AC-06         |
| TC05-003 | Hợp lệ            | Thanh toán điện tử có kết quả                                   | Khách hàng nhận kết quả thanh toán         | FR-29                |
| TC05-004 | Hợp lệ            | Chuyến hoàn thành                                               | Khách hàng nhận thông báo hoàn thành       | FR-30, AC-16         |
| TC05-005 | Hợp lệ            | Gửi thông báo đến khách hàng                                    | Thông báo được gửi đến đúng khách hàng     | BRL-23               |
| TC05-006 | Hợp lệ            | Gửi thông báo đến tài xế                                        | Thông báo được gửi đến đúng tài xế         | BRL-23               |
| TC05-007 | Quy tắc nghiệp vụ | Tài xế chấp nhận chuyến                                         | Phát sinh thông báo cho khách hàng         | BR-08, BRL-23        |
| TC05-008 | Quy tắc nghiệp vụ | Không tìm được tài xế                                           | Phát sinh thông báo cho khách hàng         | BR-17, BRL-23        |
| TC05-009 | Quy tắc nghiệp vụ | Thanh toán điện tử THẤT BẠI                                     | Phát sinh thông báo cho khách hàng         | FR-25, FR-29, BRL-23 |
| TC05-010 | Quy tắc nghiệp vụ | Chuyến HOÀN THÀNH                                               | Phát sinh thông báo hoàn thành             | FR-30, BRL-23        |
| TC05-011 | Không hợp lệ      | Yêu cầu gửi thông báo thiếu người nhận theo API                 | Yêu cầu bị từ chối                         | API Thông báo        |
| TC05-012 | Không hợp lệ      | Yêu cầu gửi thông báo thiếu dữ liệu nội dung cần thiết theo API | Yêu cầu bị từ chối                         | API Thông báo        |
| TC05-013 | Phân quyền        | Người dùng chưa đăng nhập gọi API thông báo yêu cầu xác thực    | Yêu cầu bị từ chối                         | BRL-03, FR-41        |
| TC05-014 | Phân quyền        | Người dùng truy cập thông báo không thuộc quyền của mình        | Yêu cầu bị từ chối                         | BRL-03, FR-41        |
| TC05-015 | Ngoại lệ          | Nhà cung cấp thông báo không phản hồi                           | Lỗi nhà cung cấp được xử lý phù hợp        | EC-15                |
| TC05-016 | Ngoại lệ          | Nhà cung cấp thông báo trả lỗi gửi                              | Kết quả lỗi được xử lý phù hợp             | EC-15                |
| TC05-017 | Dữ liệu           | Thông báo gửi cho khách hàng                                    | Đúng đối tượng nhận thông báo              | BRL-23               |
| TC05-018 | Dữ liệu           | Thông báo gửi cho tài xế                                        | Đúng đối tượng nhận thông báo              | BRL-23               |
| TC05-019 | Nhất quán         | Thanh toán THẤT BẠI → thông báo khách hàng                      | Kết quả thanh toán thất bại được thông báo | FR-25, FR-29         |
| TC05-020 | Nhất quán         | Chuyến HOÀN THÀNH → thông báo hoàn thành                        | Sự kiện hoàn thành được thông báo          | FR-30                |

---

# UC06 – ĐÁNH GIÁ TÀI XẾ

| ID       | Tiêu chí          | Test case                                             | Kết quả mong đợi                                             | Trace                |
| -------- | ----------------- | ----------------------------------------------------- | ------------------------------------------------------------ | -------------------- |
| TC06-001 | Hợp lệ            | Khách hàng đánh giá tài xế sau khi chuyến hoàn thành  | Đánh giá được lưu                                            | FR-31, AC-17         |
| TC06-002 | Hợp lệ            | Khách hàng gửi đánh giá kèm nội dung                  | Đánh giá và nội dung được lưu                                | FR-31, FR-32         |
| TC06-003 | Hợp lệ            | Khách hàng đánh giá tài xế của chuyến                 | Đánh giá được liên kết với chuyến tương ứng                  | FR-32                |
| TC06-004 | Hợp lệ            | Khách hàng đánh giá chuyến đã hoàn thành              | Đánh giá được lưu                                            | FR-31, FR-32, BRL-24 |
| TC06-005 | Quy tắc nghiệp vụ | Khách hàng đánh giá khi chuyến chưa hoàn thành        | Yêu cầu bị từ chối                                           | BRL-24, EC-16        |
| TC06-006 | Quy tắc nghiệp vụ | Khách hàng đánh giá chuyến chưa hoàn thành            | Yêu cầu bị từ chối                                           | BRL-24, EC-16        |
| TC06-007 | Quy tắc nghiệp vụ | Khách hàng đánh giá sau khi chuyến hoàn thành         | Cho phép đánh giá                                            | BRL-24               |
| TC06-008 | Dữ liệu           | Kiểm tra thông tin liên kết của đánh giá sau khi lưu  | Đánh giá được liên kết đúng với chuyến, khách hàng và tài xế | FR-32                |
| TC06-009 | Không hợp lệ      | Thiếu dữ liệu đánh giá bắt buộc theo API              | Yêu cầu bị từ chối                                           | FR-31, API Đánh giá  |
| TC06-010 | Không hợp lệ      | Mã chuyến không tồn tại khi gửi đánh giá              | Yêu cầu bị từ chối                                           | FR-32                |
| TC06-011 | Phân quyền        | Khách hàng khác đánh giá chuyến không thuộc mình      | Yêu cầu bị từ chối                                           | BRL-03, FR-32        |
| TC06-012 | Phân quyền        | Tài xế tự thực hiện chức năng đánh giá                | Yêu cầu bị từ chối                                           | BRL-03               |
| TC06-013 | Phân quyền        | Người dùng chưa đăng nhập gửi đánh giá                | Yêu cầu bị từ chối                                           | BRL-03, FR-41        |
| TC06-014 | Dữ liệu           | Kiểm tra đánh giá được liên kết với đúng chuyến       | Đánh giá liên kết đúng chuyến                                | FR-32                |
| TC06-015 | Dữ liệu           | Kiểm tra đánh giá thuộc khách hàng thực hiện đánh giá | Đánh giá thuộc đúng khách hàng                               | FR-31, FR-32         |
| TC06-016 | Dữ liệu           | Kiểm tra đánh giá liên quan đúng tài xế               | Đánh giá liên quan đến tài xế của chuyến                     | FR-32                |
| TC06-017 | Dữ liệu           | Kiểm tra nội dung đánh giá được lưu                   | Nội dung được lưu đúng                                       | FR-32                |
| TC06-018 | Ngoại lệ          | Đánh giá gửi cho chuyến không xác định được           | Không tạo đánh giá sai đối tượng                             | FR-32, EC-16         |
| TC06-019 | Nhất quán         | Chuyến hoàn thành → khách hàng được phép đánh giá     | Luồng đánh giá đúng điều kiện                                | BRL-24               |
| TC06-020 | Nhất quán         | Đánh giá sau khi hoàn thành được lưu vào hệ thống     | Đánh giá được lưu đúng                                       | FR-31, FR-32         |

---

# UC07 – QUẢN LÝ VẬN HÀNH

| ID       | Tiêu chí          | Test case                                                      | Kết quả mong đợi                                                           | Trace               |
| -------- | ----------------- | -------------------------------------------------------------- | -------------------------------------------------------------------------- | ------------------- |
| TC07-001 | Hợp lệ            | Nhân viên vận hành xem danh sách phương tiện                   | Danh sách phương tiện được hiển thị                                        | FR-35, BR-10        |
| TC07-002 | Hợp lệ            | Nhân viên vận hành tra cứu phương tiện                         | Thông tin phương tiện phù hợp được trả về                                  | FR-35               |
| TC07-003 | Hợp lệ            | Nhân viên vận hành xem danh sách chuyến                        | Danh sách chuyến được hiển thị                                             | FR-36, BR-10        |
| TC07-004 | Hợp lệ            | Nhân viên vận hành tra cứu một chuyến                          | Thông tin chuyến được hiển thị                                             | FR-36               |
| TC07-005 | Hợp lệ            | Nhân viên vận hành theo dõi trạng thái chuyến                  | Trạng thái chuyến được cung cấp                                            | FR-36               |
| TC07-006 | Hợp lệ            | Nhân viên vận hành ghi nhận/xử lý sự cố liên quan chuyến       | Sự cố được ghi nhận/xử lý                                                  | FR-37, BR-16        |
| TC07-007 | Quy tắc nghiệp vụ | Nhân viên vận hành thực hiện chức năng vận hành được cấp quyền | Chức năng được thực hiện                                                   | BRL-03, FR-41       |
| TC07-008 | Quy tắc nghiệp vụ | Nhân viên vận hành theo dõi chuyến đang thực hiện              | Thông tin chuyến được cung cấp                                             | FR-36               |
| TC07-009 | Không hợp lệ      | Tra cứu phương tiện không tồn tại                              | Không trả dữ liệu phương tiện không tồn tại                                | FR-35               |
| TC07-010 | Không hợp lệ      | Tra cứu chuyến không tồn tại                                   | Không trả dữ liệu chuyến không tồn tại                                     | FR-36               |
| TC07-011 | Không hợp lệ      | Ghi nhận sự cố bằng dữ liệu không hợp lệ theo API              | Yêu cầu bị từ chối                                                         | FR-37, API Quản trị |
| TC07-012 | Phân quyền        | Khách hàng truy cập chức năng vận hành                         | Yêu cầu bị từ chối                                                         | BRL-03, FR-41       |
| TC07-013 | Phân quyền        | Tài xế truy cập chức năng vận hành của nhân viên vận hành      | Yêu cầu bị từ chối                                                         | BRL-03, FR-41       |
| TC07-014 | Phân quyền        | Nhân viên vận hành không có quyền thực hiện chức năng          | Yêu cầu bị từ chối                                                         | FR-41               |
| TC07-015 | Phân quyền        | Người dùng không có quyền truy cập chức năng vận hành          | Yêu cầu bị từ chối                                                         | FR-41               |
| TC07-016 | Ngoại lệ          | Thành phần quản lý chuyến gặp lỗi                              | Các chức năng không liên quan tiếp tục hoạt động theo yêu cầu của hệ thống | EC-18               |
| TC07-017 | Ngoại lệ          | Thành phần quản lý phương tiện gặp lỗi                         | Các chức năng không liên quan tiếp tục hoạt động theo yêu cầu của hệ thống | EC-18               |
| TC07-018 | Dữ liệu           | Nhân viên vận hành tra cứu thông tin phương tiện               | Dữ liệu phương tiện được trả về phù hợp                                    | FR-35               |
| TC07-019 | Dữ liệu           | Nhân viên vận hành tra cứu thông tin chuyến                    | Dữ liệu chuyến được trả về phù hợp                                         | FR-36               |
| TC07-020 | Kiểm toán         | Nhân viên vận hành thực hiện thao tác quan trọng               | Thao tác được ghi nhận để truy vết                                         | FR-42               |

---

# UC08 – XỬ LÝ SỰ CỐ

| ID       | Tiêu chí          | Test case                                                                    | Kết quả mong đợi                                | Trace               |
| -------- | ----------------- | ---------------------------------------------------------------------------- | ----------------------------------------------- | ------------------- |
| TC08-001 | Hợp lệ            | Nhân viên vận hành ghi nhận sự cố liên quan chuyến đi                        | Sự cố được ghi nhận                             | FR-37               |
| TC08-002 | Hợp lệ            | Nhân viên vận hành xử lý sự cố liên quan chuyến đi                           | Thao tác xử lý sự cố được thực hiện             | FR-37, BR-16        |
| TC08-003 | Hợp lệ            | Nhân viên vận hành ghi nhận trường hợp mất kết nối trong quá trình chuyến đi | Sự cố được ghi nhận để nhân viên vận hành xử lý | FR-37, EC-09        |
| TC08-004 | Hợp lệ            | Nhân viên vận hành ghi nhận trường hợp không tính được cước thực tế          | Sự cố được ghi nhận để xử lý                    | FR-37, EC-12        |
| TC08-005 | Hợp lệ            | Nhân viên vận hành ghi nhận trường hợp chưa thanh toán tiền mặt              | Sự cố được ghi nhận để xử lý                    | FR-37, EC-13        |
| TC08-006 | Hợp lệ            | Nhân viên vận hành ghi nhận trường hợp tài xế chưa xác nhận tiền mặt         | Sự cố được ghi nhận để xử lý                    | FR-37, EC-14        |
| TC08-007 | Quy tắc nghiệp vụ | Nhân viên vận hành xử lý sự cố khi có quyền phù hợp                          | Thao tác được phép thực hiện                    | FR-41               |
| TC08-008 | Quy tắc nghiệp vụ | Nhân viên vận hành ghi nhận sự cố của một chuyến cụ thể                      | Sự cố được ghi nhận gắn với thông tin chuyến    | FR-37               |
| TC08-009 | Không hợp lệ      | Ghi nhận sự cố bằng dữ liệu không hợp lệ theo API                            | Yêu cầu bị từ chối                              | FR-37, API Quản trị |
| TC08-010 | Không hợp lệ      | Ghi nhận sự cố cho chuyến không tồn tại                                      | Yêu cầu bị từ chối                              | FR-37               |
| TC08-011 | Phân quyền        | Khách hàng thực hiện chức năng xử lý sự cố                                   | Yêu cầu bị từ chối                              | BRL-03, FR-41       |
| TC08-012 | Phân quyền        | Tài xế thực hiện chức năng xử lý sự cố của nhân viên vận hành                | Yêu cầu bị từ chối                              | BRL-03, FR-41       |
| TC08-013 | Phân quyền        | Nhân viên vận hành không có quyền xử lý sự cố                                | Yêu cầu bị từ chối                              | FR-41               |
| TC08-014 | Phân quyền        | Người dùng không có quyền thực hiện xử lý sự cố                              | Yêu cầu bị từ chối                              | FR-41               |
| TC08-015 | Ngoại lệ          | Chuyến bị mất kết nối trong quá trình thực hiện                              | Sự cố được ghi nhận để nhân viên vận hành xử lý | EC-09, FR-37        |
| TC08-016 | Ngoại lệ          | Không cập nhật được vị trí                                                   | Sự cố được ghi nhận để nhân viên vận hành xử lý | EC-10, FR-37        |
| TC08-017 | Ngoại lệ          | Không cập nhật được trạng thái chuyến                                        | Sự cố được ghi nhận để nhân viên vận hành xử lý | EC-11, FR-37        |
| TC08-018 | Ngoại lệ          | Nhà cung cấp thông báo xảy ra lỗi                                            | Lỗi được ghi nhận để nhân viên vận hành xử lý   | EC-15, FR-37        |
| TC08-019 | Ngoại lệ          | Thành phần hệ thống gặp lỗi                                                  | Trường hợp lỗi được ghi nhận để xử lý           | EC-18               |
| TC08-020 | Kiểm toán         | Nhân viên vận hành xử lý sự cố                                               | Thao tác được ghi nhận để truy vết              | FR-42               |

---

# UC09 – QUẢN LÝ BÁO CÁO HOẠT ĐỘNG

| ID       | Tiêu chí     | Test case                                                  | Kết quả mong đợi                           | Trace              |
| -------- | ------------ | ---------------------------------------------------------- | ------------------------------------------ | ------------------ |
| TC09-001 | Hợp lệ       | Quản lý xem báo cáo hoạt động                              | Báo cáo được trả về                        | FR-38              |
| TC09-002 | Hợp lệ       | Quản lý xem tổng số chuyến                                 | Tổng số chuyến được cung cấp               | FR-38              |
| TC09-003 | Hợp lệ       | Quản lý xem tổng doanh thu                                 | Tổng doanh thu được cung cấp               | FR-38              |
| TC09-004 | Hợp lệ       | Quản lý xem tỷ lệ hoàn thành                               | Tỷ lệ hoàn thành được cung cấp             | FR-38              |
| TC09-005 | Hợp lệ       | Quản lý xem tỷ lệ hủy                                      | Tỷ lệ hủy được cung cấp                    | FR-38              |
| TC09-006 | Hợp lệ       | Quản lý xem hiệu quả tài xế                                | Thông tin hiệu quả tài xế được cung cấp    | FR-38              |
| TC09-007 | Hợp lệ       | Quản lý xem báo cáo theo khoảng thời gian hợp lệ           | Báo cáo được trả về theo khoảng thời gian  | FR-38, API Báo cáo |
| TC09-008 | Hợp lệ       | Quản lý xem báo cáo kinh doanh                             | Báo cáo kinh doanh được trả về             | FR-39, BR-12       |
| TC09-009 | API          | Gọi API báo cáo không truyền khoảng thời gian              | API xử lý theo hợp đồng API đã chốt        | API Báo cáo        |
| TC09-010 | Không hợp lệ | Khoảng thời gian báo cáo không hợp lệ theo API             | Yêu cầu bị từ chối                         | API Báo cáo        |
| TC09-011 | Không hợp lệ | Yêu cầu báo cáo không hợp lệ theo API                      | API trả lỗi phù hợp                        | API Báo cáo        |
| TC09-012 | Phân quyền   | Khách hàng truy cập báo cáo dành cho quản lý               | Yêu cầu bị từ chối                         | FR-41, API Báo cáo |
| TC09-013 | Phân quyền   | Tài xế truy cập báo cáo dành cho quản lý                   | Yêu cầu bị từ chối                         | FR-41, API Báo cáo |
| TC09-014 | Phân quyền   | Người dùng không có quyền quản lý gọi API dành cho quản lý | Yêu cầu bị từ chối                         | FR-41, API Báo cáo |
| TC09-015 | Phân quyền   | Nhân viên vận hành gọi API chỉ dành cho quản lý            | Yêu cầu bị từ chối                         | FR-41, API Báo cáo |
| TC09-016 | Dữ liệu      | Báo cáo có dữ liệu chuyến                                  | Các chỉ số chuyến được cung cấp            | FR-38              |
| TC09-017 | Dữ liệu      | Báo cáo có dữ liệu doanh thu                               | Tổng doanh thu được cung cấp               | FR-38              |
| TC09-018 | Dữ liệu      | Báo cáo có dữ liệu tài xế                                  | Thông tin hiệu quả tài xế được cung cấp    | FR-38              |
| TC09-019 | API          | Khoảng thời gian không có dữ liệu                          | API trả phản hồi theo hợp đồng API đã chốt | API Báo cáo        |
| TC09-020 | Ngoại lệ     | Dịch vụ báo cáo gặp lỗi                                    | API trả lỗi phù hợp                        | API Báo cáo        |

---

# UC10 – TRA CỨU LỊCH SỬ GIAO DỊCH

| ID       | Tiêu chí     | Test case                                                         | Kết quả mong đợi                           | Trace         |
| -------- | ------------ | ----------------------------------------------------------------- | ------------------------------------------ | ------------- |
| TC10-001 | Hợp lệ       | Nhân viên vận hành tra cứu lịch sử giao dịch                      | Lịch sử giao dịch được trả về              | FR-40, BR-12  |
| TC10-002 | Hợp lệ       | Nhân viên vận hành tra cứu giao dịch liên quan một chuyến         | Giao dịch phù hợp được trả về              | FR-40         |
| TC10-003 | Hợp lệ       | Tra cứu giao dịch thành công                                      | Giao dịch thành công được hiển thị         | FR-40         |
| TC10-004 | Hợp lệ       | Tra cứu giao dịch thất bại                                        | Giao dịch thất bại được hiển thị           | FR-40         |
| TC10-005 | Hợp lệ       | Tra cứu lịch sử có nhiều giao dịch                                | Các giao dịch phù hợp được trả về          | FR-40         |
| TC10-006 | Không hợp lệ | Tra cứu chuyến không tồn tại                                      | Không trả giao dịch không tồn tại          | FR-40         |
| TC10-007 | Không hợp lệ | Yêu cầu tra cứu không hợp lệ theo API                             | Yêu cầu bị từ chối                         | API Quản trị  |
| TC10-008 | Phân quyền   | Khách hàng truy cập lịch sử giao dịch dành cho nhân viên vận hành | Yêu cầu bị từ chối                         | BRL-03, FR-41 |
| TC10-009 | Phân quyền   | Tài xế truy cập lịch sử giao dịch dành cho nhân viên vận hành     | Yêu cầu bị từ chối                         | BRL-03, FR-41 |
| TC10-010 | Phân quyền   | Nhân viên vận hành không có quyền tra cứu                         | Yêu cầu bị từ chối                         | FR-41         |
| TC10-011 | Phân quyền   | Người dùng không có quyền nhân viên vận hành thực hiện tra cứu    | Yêu cầu bị từ chối                         | FR-41         |
| TC10-012 | Dữ liệu      | Lịch sử phản ánh thanh toán THÀNH CÔNG                            | Giao dịch thành công được phản ánh         | FR-40, FR-26  |
| TC10-013 | Dữ liệu      | Lịch sử phản ánh thanh toán THẤT BẠI                              | Giao dịch thất bại được phản ánh           | FR-40, FR-26  |
| TC10-014 | Dữ liệu      | Giao dịch được tra cứu theo chuyến                                | Giao dịch tương ứng với chuyến được trả về | FR-40         |
| TC10-015 | Dữ liệu      | Tra cứu lịch sử không làm thay đổi dữ liệu giao dịch              | Dữ liệu giao dịch không bị thay đổi        | FR-40         |
| TC10-016 | Nhất quán    | Thanh toán THÀNH CÔNG → tra cứu lịch sử                           | Lịch sử phản ánh kết quả thành công        | FR-24, FR-40  |
| TC10-017 | Nhất quán    | Thanh toán THẤT BẠI → tra cứu lịch sử                             | Lịch sử phản ánh kết quả thất bại          | FR-24, FR-40  |
| TC10-018 | Ngoại lệ     | Dịch vụ giao dịch gặp lỗi                                         | API trả lỗi phù hợp                        | API Quản trị  |
| TC10-019 | Kiểm toán    | Nhân viên vận hành thực hiện tra cứu giao dịch                    | Thao tác được ghi nhận để truy vết         | FR-42         |
| TC10-020 | Dữ liệu      | Tra cứu lại cùng giao dịch                                        | Kết quả nhất quán với dữ liệu đã lưu       | FR-40         |

---

# UC11 – QUẢN LÝ KHÁCH HÀNG

| ID       | Tiêu chí          | Test case                                                           | Kết quả mong đợi                                 | Trace               |
| -------- | ----------------- | ------------------------------------------------------------------- | ------------------------------------------------ | ------------------- |
| TC11-001 | Hợp lệ            | Nhân viên vận hành xem danh sách khách hàng                         | Danh sách khách hàng được trả về                 | FR-33, BR-10        |
| TC11-002 | Hợp lệ            | Nhân viên vận hành tra cứu khách hàng                               | Khách hàng phù hợp được trả về                   | FR-33               |
| TC11-003 | Hợp lệ            | Nhân viên vận hành xem thông tin khách hàng                         | Thông tin khách hàng được hiển thị               | FR-33               |
| TC11-004 | Hợp lệ            | Nhân viên vận hành quản lý khách hàng                               | Khách hàng được quản lý theo quyền               | FR-33, BR-10        |
| TC11-005 | Quy tắc nghiệp vụ | Nhân viên vận hành thực hiện quản lý khách hàng theo quyền được cấp | Chức năng được thực hiện khi có quyền            | BRL-03, FR-41       |
| TC11-006 | Không hợp lệ      | Tra cứu khách hàng không tồn tại                                    | Không tìm thấy khách hàng                        | FR-33               |
| TC11-007 | Không hợp lệ      | Cập nhật khách hàng bằng dữ liệu không hợp lệ theo API              | Yêu cầu bị từ chối                               | FR-33, API Quản trị |
| TC11-008 | Phân quyền        | Khách hàng truy cập chức năng quản lý khách hàng                    | Yêu cầu bị từ chối                               | BRL-03, FR-41       |
| TC11-009 | Phân quyền        | Tài xế truy cập chức năng quản lý khách hàng                        | Yêu cầu bị từ chối                               | BRL-03, FR-41       |
| TC11-010 | Phân quyền        | Nhân viên vận hành không có quyền quản lý khách hàng                | Yêu cầu bị từ chối                               | FR-41               |
| TC11-011 | Phân quyền        | Người dùng không có quyền quản lý khách hàng                        | Yêu cầu bị từ chối                               | FR-41               |
| TC11-012 | Dữ liệu           | Khách hàng được lưu đúng thông tin tài khoản                        | Dữ liệu khách hàng được trả về đúng              | BR-01               |
| TC11-013 | Dữ liệu           | Nhân viên vận hành quản lý khách hàng đã tồn tại                    | Dữ liệu khách hàng tương ứng được xử lý          | FR-33               |
| TC11-014 | Dữ liệu           | Nhân viên vận hành tra cứu khách hàng sau khi cập nhật              | Dữ liệu mới được hiển thị                        | FR-33               |
| TC11-015 | Nhất quán         | Khách hàng được cập nhật thành công                                 | Thông tin sau cập nhật nhất quán với dữ liệu lưu | FR-33               |
| TC11-016 | Nhất quán         | Khách hàng tồn tại được nhân viên vận hành tra cứu                  | Kết quả tra cứu đúng khách hàng                  | FR-33               |
| TC11-017 | Ngoại lệ          | Dịch vụ khách hàng trả lỗi                                          | API trả lỗi phù hợp                              | API Quản trị        |
| TC11-018 | Kiểm toán         | Nhân viên vận hành cập nhật khách hàng                              | Thao tác được ghi nhận để truy vết               | FR-42               |
| TC11-019 | Kiểm toán         | Nhân viên vận hành tra cứu khách hàng                               | Thao tác quan trọng được truy vết                | FR-42               |
| TC11-020 | Phân quyền        | Nhân viên vận hành không được cấp quyền quản lý khách hàng          | Yêu cầu bị từ chối                               | FR-41, AC-20        |

---

# UC12 – QUẢN LÝ TÀI XẾ

| ID       | Tiêu chí          | Test case                                                       | Kết quả mong đợi                      | Trace               |
| -------- | ----------------- | --------------------------------------------------------------- | ------------------------------------- | ------------------- |
| TC12-001 | Hợp lệ            | Nhân viên vận hành xem danh sách tài xế                         | Danh sách tài xế được trả về          | FR-34, BR-10        |
| TC12-002 | Hợp lệ            | Nhân viên vận hành tra cứu tài xế                               | Tài xế phù hợp được trả về            | FR-34               |
| TC12-003 | Hợp lệ            | Nhân viên vận hành xem thông tin tài xế                         | Thông tin tài xế được hiển thị        | FR-34               |
| TC12-004 | Hợp lệ            | Nhân viên vận hành quản lý tài xế                               | Tài xế được quản lý theo quyền        | FR-34, BR-10        |
| TC12-005 | Hợp lệ            | Nhân viên vận hành tạo tài khoản tài xế                         | Tài khoản tài xế được tạo             | FR-01               |
| TC12-006 | Hợp lệ            | Tài xế tự đăng ký tài khoản                                     | Tài khoản tài xế được tạo             | FR-01               |
| TC12-007 | Quy tắc nghiệp vụ | Tài xế cập nhật hồ sơ sau khi tạo tài khoản                     | Hồ sơ tài xế được cập nhật            | FR-03, BR-15        |
| TC12-008 | Quy tắc nghiệp vụ | Tài xế cập nhật phương tiện/trạng thái sẵn sàng                 | Thông tin được cập nhật               | FR-04, BR-15        |
| TC12-009 | Quy tắc nghiệp vụ | Nhân viên vận hành quản lý tài xế theo quyền được cấp           | Chức năng được thực hiện khi có quyền | FR-41               |
| TC12-010 | Không hợp lệ      | Tra cứu tài xế không tồn tại                                    | Không tìm thấy tài xế                 | FR-34               |
| TC12-011 | Không hợp lệ      | Tạo tài xế bằng dữ liệu không hợp lệ theo API                   | Yêu cầu bị từ chối                    | FR-01, API Xác thực |
| TC12-012 | Không hợp lệ      | Cập nhật tài xế bằng dữ liệu không hợp lệ theo API              | Yêu cầu bị từ chối                    | FR-34, API Quản trị |
| TC12-013 | Phân quyền        | Khách hàng quản lý tài xế                                       | Yêu cầu bị từ chối                    | BRL-03, FR-41       |
| TC12-014 | Phân quyền        | Tài xế truy cập chức năng quản lý tài xế của nhân viên vận hành | Yêu cầu bị từ chối                    | BRL-03, FR-41       |
| TC12-015 | Phân quyền        | Nhân viên vận hành không có quyền quản lý tài xế                | Yêu cầu bị từ chối                    | FR-41               |
| TC12-016 | Phân quyền        | Người dùng không có quyền quản lý tài xế                        | Yêu cầu bị từ chối                    | FR-41               |
| TC12-017 | Dữ liệu           | Nhân viên vận hành quản lý tài xế và thông tin hồ sơ tài xế     | Thông tin tài xế được trả về phù hợp  | FR-34, BR-15        |
| TC12-018 | Dữ liệu           | Tài xế có trạng thái sẵn sàng                                   | Trạng thái sẵn sàng được lưu/cập nhật | FR-04, BRL-02       |
| TC12-019 | Nhất quán         | Tài xế được nhân viên vận hành tạo sau đó đăng nhập             | Tài khoản tài xế hoạt động đúng       | FR-01, FR-02        |
| TC12-020 | Kiểm toán         | Nhân viên vận hành cập nhật tài xế                              | Thao tác được ghi nhận để truy vết    | FR-42               |

---


