# Software Requirements Specification (SRS) - CAB System
# 1. STAKEHOLDERS

Stakeholders của hệ thống CAB System gồm các bên có liên quan trực tiếp
đến việc sử dụng, vận hành, quản lý và cung cấp dịch vụ cho hệ thống.

| STT | Stakeholder | Vai trò / Mối quan tâm |
|---|---|---|
| 1 | Khách hàng | Đăng ký tài khoản, đặt xe, theo dõi chuyến đi, thanh toán và đánh giá tài xế. |
| 2 | Tài xế | Nhận và thực hiện chuyến xe, cập nhật trạng thái chuyến, thông tin phương tiện và vị trí. |
| 3 | Nhân viên vận hành | Quản lý khách hàng, tài xế, phương tiện và chuyến đi; theo dõi và xử lý các trường hợp phát sinh. |
| 4 | Ban lãnh đạo Công ty ABC | Theo dõi doanh thu, số lượng chuyến, tỷ lệ hoàn thành, tỷ lệ hủy và hiệu quả hoạt động của tài xế. |
| 5 | Nhà cung cấp thanh toán | Xử lý các giao dịch thanh toán điện tử cho hệ thống CAB. |
| 6 | Nhà cung cấp dịch vụ thông báo | Cung cấp các kênh gửi thông báo đến khách hàng và tài xế. |
## 2. STAKEHOLDER MATRIX (Ma trận Bên liên quan)

```mermaid
quadrantChart
    title Ma trận Stakeholder (Power vs Interest)

    x-axis "Mức độ quan tâm Thấp" --> "Mức độ quan tâm Cao"
    y-axis "Quyền lực / Ảnh hưởng Thấp" --> "Quyền lực / Ảnh hưởng Cao"

    quadrant-1 "Thỏa mãn nhu cầu (Keep Satisfied)"
    quadrant-2 "Quản lý chặt chẽ (Manage Closely)"
    quadrant-3 "Theo dõi tối thiểu (Monitor)"
    quadrant-4 "Cung cấp thông tin (Keep Informed)"

    "Ban lãnh đạo": [0.85, 0.90]
    "Nhân viên vận hành": [0.65, 0.55]
    "Khách hàng": [0.85, 0.35]
    "Tài xế": [0.75, 0.30]
    "Đối tác thanh toán": [0.30, 0.65]
    "Đối tác thông báo": [0.25, 0.55]
```

## 3. BUSINESS GOALS (Mục tiêu Kinh doanh)

| STT | Business Goal | Mục tiêu |
|---|---|---|
| 1 | **Nâng cao trải nghiệm đặt xe** | Xây dựng nền tảng CAB giúp khách hàng dễ dàng đăng ký, đặt xe, theo dõi chuyến đi, thanh toán và đánh giá tài xế. |
| 2 | **Tự động hóa việc tìm và phân công tài xế** | Tự động tìm tài xế phù hợp dựa trên vị trí, trạng thái sẵn sàng và các tiêu chí vận hành; tiếp tục tìm tài xế khác khi tài xế được đề xuất không phản hồi hoặc từ chối. |
| 3 | **Nâng cao hiệu quả vận hành** | Cung cấp công cụ để nhân viên vận hành quản lý khách hàng, tài xế, phương tiện và chuyến đi; theo dõi và xử lý các trường hợp phát sinh. |
| 4 | **Quản lý thanh toán và doanh thu** | Hỗ trợ tính cước và thanh toán bằng tiền mặt hoặc phương thức điện tử, đồng thời quản lý thông tin giao dịch và doanh thu. |
| 5 | **Cung cấp thông tin và theo dõi hoạt động** | Cung cấp thông báo về trạng thái chuyến đi, thanh toán và các sự kiện liên quan; hỗ trợ báo cáo về số chuyến, doanh thu, tỷ lệ hoàn thành, tỷ lệ hủy và hiệu quả tài xế. |
| 6 | **Đảm bảo khả năng mở rộng của nền tảng** | Xây dựng hệ thống có khả năng phục vụ số lượng lớn khách hàng và tài xế, cho phép mở rộng từng thành phần và bổ sung chức năng mới trong tương lai. |
| 7 | **Đảm bảo an toàn và bảo mật** | Bảo vệ thông tin cá nhân, thông tin phương tiện, dữ liệu vị trí và dữ liệu giao dịch; kiểm soát quyền truy cập và lưu vết các thao tác quan trọng. |
| 8 | **Đảm bảo tính ổn định và liên tục của hệ thống** | Hạn chế việc lỗi ở một thành phần như thanh toán hoặc thông báo làm ảnh hưởng đến toàn bộ nền tảng đặt xe. |
## 4. MINIMUM VIABLE PRODUCT (MVP) MODULES

| STT | Module | Mô tả |
|---|---|---|
| 1 | Quản lý tài khoản & hồ sơ | Đăng ký, đăng nhập, cập nhật thông tin cá nhân cho Khách hàng và Tài xế; Tài xế cập nhật hồ sơ phương tiện. |
| 2 | Đặt xe & Theo dõi chuyến | Nhập điểm đón, điểm đến, chọn loại xe, gửi yêu cầu đặt xe; theo dõi trạng thái chuyến theo thời gian thực; xem lịch sử chuyến đi. |
| 3 | Tìm & Phân công tài xế | Tự động tìm tài xế phù hợp theo vị trí và trạng thái sẵn sàng; xử lý khi tài xế không phản hồi/từ chối; thông báo khi không tìm được tài xế. |
| 4 | Thực hiện chuyến đi | Tài xế cập nhật trạng thái chuyến: đã đến điểm đón, đã đón khách, đang di chuyển, hoàn thành chuyến. |
| 5 | Tính cước & Thanh toán | Tính cước sau khi hoàn thành chuyến; thanh toán bằng tiền mặt hoặc tích hợp thanh toán điện tử bên ngoài; xử lý khi giao dịch thất bại. |
| 6 | Thông báo | Gửi thông báo cho khách hàng và tài xế theo các sự kiện của chuyến đi. |
| 7 | Đánh giá tài xế | Khách hàng đánh giá tài xế sau khi hoàn thành chuyến. |
| 8 | Quản trị vận hành | Giao diện cho Nhân viên vận hành quản lý khách hàng, tài xế, phương tiện, chuyến đi và xem báo cáo. |
## 5. ACTORS

| STT | Actor | Mô tả |
|---|---|---|
| 1 | Khách hàng (Customer) | Đăng ký/đăng nhập, cập nhật hồ sơ, tạo yêu cầu đặt xe, theo dõi chuyến, xem lịch sử, thanh toán và đánh giá tài xế. |
| 2 | Tài xế (Driver) | Đăng ký/cập nhật hồ sơ và phương tiện, chuyển trạng thái sẵn sàng, nhận/từ chối chuyến, cập nhật trạng thái chuyến và vị trí. |
| 3 | Nhân viên vận hành (Operator) | Quản lý khách hàng, tài xế, phương tiện, chuyến đi; xử lý sự cố; tra cứu lịch sử và xem báo cáo. |
| 4 | Ban lãnh đạo (Manager) | Xem báo cáo doanh thu, số chuyến, tỷ lệ hoàn thành/hủy và hiệu quả tài xế. |

| 5 | Nhà cung cấp thanh toán (Payment Gateway) | Xử lý giao dịch thanh toán điện tử và trả kết quả giao dịch về hệ thống CAB. |
| 6 | Nhà cung cấp dịch vụ thông báo (Notification Provider) | Gửi thông báo đến khách hàng và tài xế theo yêu cầu của hệ thống. |
## 7. BUSINESS REQUIREMENTS

| ID | Business Requirement | Mô tả |
|---|---|---|
| BR-01 | Quản lý tài khoản khách hàng | Hệ thống phải cho phép Khách hàng đăng ký, đăng nhập và quản lý thông tin cá nhân để sử dụng dịch vụ đặt xe. |
| BR-02 | Tạo yêu cầu đặt xe | Hệ thống phải cho phép Khách hàng tạo yêu cầu đặt xe bằng cách cung cấp điểm đón, điểm đến và loại xe. |
| BR-03 | Tự động tìm và phân công tài xế | Hệ thống phải tự động tìm và phân công Tài xế phù hợp dựa trên vị trí và trạng thái sẵn sàng. |
| BR-04 | Xử lý từ chối hoặc không phản hồi | Hệ thống phải tiếp tục tìm Tài xế khác khi Tài xế được đề xuất không phản hồi hoặc từ chối chuyến. |
| BR-05 | Theo dõi và cập nhật chuyến đi | Hệ thống phải cho phép Khách hàng và Tài xế theo dõi và cập nhật trạng thái chuyến đi trong suốt quá trình thực hiện. |
| BR-06 | Tính cước và thanh toán | Hệ thống phải tính cước chuyến đi và hỗ trợ thanh toán bằng tiền mặt hoặc phương thức thanh toán điện tử. |
| BR-07 | Tích hợp thanh toán điện tử | Hệ thống phải tích hợp với nhà cung cấp thanh toán để xử lý giao dịch và phản hồi kết quả thanh toán. |
| BR-08 | Thông báo sự kiện chuyến đi | Hệ thống phải gửi thông báo đến Khách hàng và Tài xế khi xảy ra các sự kiện quan trọng của chuyến đi. |
| BR-09 | Đánh giá tài xế | Hệ thống phải cho phép Khách hàng đánh giá Tài xế sau khi chuyến đi hoàn thành. |
| BR-10 | Quản lý vận hành | Hệ thống phải cung cấp cho Nhân viên vận hành các chức năng quản lý khách hàng, tài xế, phương tiện và chuyến đi. |
| BR-11 | Báo cáo hoạt động | Hệ thống phải cung cấp báo cáo về số chuyến, doanh thu, tỷ lệ hoàn thành, tỷ lệ hủy và hiệu quả hoạt động của Tài xế. |
| BR-12 | Báo cáo cho ban lãnh đạo | Hệ thống phải cho phép Ban lãnh đạo truy cập các báo cáo cần thiết để theo dõi và đánh giá hoạt động kinh doanh. |
| BR-13 | Bảo vệ dữ liệu | Hệ thống phải bảo vệ thông tin cá nhân, dữ liệu vị trí và thông tin giao dịch của người dùng. |
| BR-14 | Khả năng mở rộng | Hệ thống phải có khả năng mở rộng để đáp ứng số lượng lớn Khách hàng và Tài xế trong tương lai. |
| BR-15 | Quản lý hồ sơ tài xế | Hệ thống phải cho phép Tài xế cập nhật thông tin cá nhân, thông tin phương tiện và trạng thái sẵn sàng nhận chuyến. |
| BR-16 | Theo dõi và xử lý sự cố | Hệ thống phải cho phép Nhân viên vận hành theo dõi các chuyến đang diễn ra và xử lý các trường hợp phát sinh trong quá trình vận hành. |
| BR-17 | Thông báo khi không tìm được tài xế | Hệ thống phải thông báo cho Khách hàng khi không tìm được Tài xế phù hợp cho yêu cầu đặt xe. |
| BR-18 | Xử lý thanh toán thất bại | Hệ thống phải xử lý trường hợp giao dịch thanh toán điện tử thất bại và thông báo kết quả cho Khách hàng. |
## 8. BUSINESS PROCESS MODELING

Quy trình đặt xe của CAB System được xây dựng theo mô hình đặt xe trực tuyến thực tế. Khách hàng nhập thông tin hành trình, lựa chọn loại xe, hệ thống tính và hiển thị giá dự kiến, sau đó khách hàng lựa chọn phương thức thanh toán và xác nhận đặt xe. Hệ thống tiếp nhận yêu cầu, tìm và phân công Tài xế. Sau khi Tài xế chấp nhận, chuyến xe được thực hiện. Đối với thanh toán tiền mặt, Khách hàng thanh toán cho Tài xế sau khi hoàn thành chuyến. Đối với thanh toán điện tử, giao dịch được thực hiện ngay sau khi Khách hàng xác nhận đặt xe. Cuối cùng, Khách hàng có thể đánh giá Tài xế.

```mermaid
flowchart TD
    A([Bắt đầu]) --> B[Khách hàng đăng nhập]
    B --> C[Nhập điểm đón và điểm đến]
    C --> D[Chọn loại xe]
    D --> E[Hệ thống tính và hiển thị giá dự kiến]
    E --> F[Khách hàng chọn phương thức thanh toán]
    F --> G[Khách hàng ấn Đặt xe]

    G --> H{Phương thức thanh toán?}

    H -- Tiền mặt --> I[Tạo yêu cầu đặt xe]

    H -- Thanh toán điện tử --> J[Gửi giao dịch đến Payment Gateway]
    J --> K{Thanh toán thành công?}

    K -- Không --> L[Thông báo thanh toán thất bại]
    L --> Z([Kết thúc])

    K -- Có --> M[Xác nhận thanh toán]
    M --> I

    I --> N[Hệ thống tìm Tài xế phù hợp]
    N --> O{Có Tài xế phù hợp?}

    O -- Không --> N
    O -- Có --> P[Gửi yêu cầu chuyến xe cho Tài xế]

    P --> Q{Tài xế chấp nhận?}

    Q -- Không / Không phản hồi --> N
    Q -- Có --> R[Thông báo thông tin Tài xế cho Khách hàng]

    R --> S{Khách hàng hủy chuyến?}

    S -- Có --> T[Xử lý hủy chuyến theo chính sách]
    T --> Z

    S -- Không --> U[Tài xế di chuyển đến điểm đón]
    U --> V[Tài xế cập nhật đã đến điểm đón]
    V --> W[Tài xế đón khách]
    W --> X[Tài xế cập nhật đang thực hiện chuyến]
    X --> Y[Di chuyển đến điểm đến]
    Y --> AA[Hoàn thành chuyến]

    AA --> AB{Phương thức thanh toán?}

    AB -- Tiền mặt --> AC[Khách hàng trả tiền cho Tài xế]
    AC --> AD[Tài xế xác nhận đã nhận tiền]
    AD --> AE[Ghi nhận hoàn tất thanh toán]

    AB -- Thanh toán điện tử --> AE

    AE --> AF[Gửi thông báo hoàn thành chuyến]
    AF --> AG[Khách hàng đánh giá Tài xế]
    AG --> Z([Kết thúc])
```
## 9. FUNCTIONAL REQUIREMENTS

### 9.1. Quản lý tài khoản và hồ sơ

| ID | Functional Requirement | Mô tả |
|---|---|---|
| FR-01 | Đăng ký tài khoản | Hệ thống phải cho phép Khách hàng và Tài xế đăng ký tài khoản để sử dụng hệ thống. |
| FR-02 | Đăng nhập | Hệ thống phải cho phép Khách hàng, Tài xế và Nhân viên vận hành đăng nhập bằng tài khoản hợp lệ. |
| FR-03 | Quản lý thông tin cá nhân | Hệ thống phải cho phép người dùng xem và cập nhật thông tin cá nhân. |
| FR-04 | Quản lý hồ sơ Tài xế | Hệ thống phải cho phép Tài xế cập nhật thông tin phương tiện và trạng thái sẵn sàng nhận chuyến. |

### 9.2. Đặt xe và theo dõi chuyến

| ID | Functional Requirement | Mô tả |
|---|---|---|
| FR-05 | Nhập thông tin chuyến xe | Hệ thống phải cho phép Khách hàng nhập điểm đón, điểm đến và lựa chọn loại xe. |
| FR-06 | Tính giá dự kiến | Hệ thống phải tính và hiển thị giá dự kiến của chuyến xe trước khi Khách hàng xác nhận đặt xe. |
| FR-07 | Chọn phương thức thanh toán | Hệ thống phải cho phép Khách hàng lựa chọn phương thức thanh toán tiền mặt hoặc thanh toán điện tử trước khi đặt xe. |
| FR-08 | Xác nhận đặt xe | Hệ thống phải tiếp nhận yêu cầu khi Khách hàng ấn Đặt xe và xử lý theo phương thức thanh toán đã chọn. |
| FR-09 | Theo dõi trạng thái chuyến | Hệ thống phải cho phép Khách hàng theo dõi trạng thái chuyến xe từ khi tìm Tài xế đến khi hoàn thành chuyến. |
| FR-10 | Xem lịch sử chuyến | Hệ thống phải cho phép Khách hàng xem lịch sử các chuyến xe đã thực hiện. |

### 9.3. Tìm và phân công Tài xế

| ID | Functional Requirement | Mô tả |
|---|---|---|
| FR-11 | Tìm Tài xế phù hợp | Hệ thống phải tự động tìm Tài xế phù hợp dựa trên vị trí và trạng thái sẵn sàng nhận chuyến. |
| FR-12 | Gửi yêu cầu chuyến xe | Hệ thống phải gửi yêu cầu chuyến xe đến Tài xế phù hợp. |
| FR-13 | Tiếp tục tìm Tài xế | Hệ thống phải tiếp tục tìm Tài xế khác khi chưa tìm được Tài xế phù hợp và không kết thúc yêu cầu đặt xe. |
| FR-14 | Xử lý Tài xế từ chối hoặc không phản hồi | Hệ thống phải tiếp tục tìm Tài xế khác khi Tài xế được gửi yêu cầu từ chối hoặc không phản hồi. |
| FR-15 | Thông báo thông tin Tài xế | Hệ thống phải thông báo thông tin Tài xế cho Khách hàng sau khi Tài xế chấp nhận chuyến. |

### 9.4. Thực hiện chuyến đi

| ID | Functional Requirement | Mô tả |
|---|---|---|
| FR-16 | Cập nhật trạng thái chuyến | Hệ thống phải cho phép Tài xế cập nhật trạng thái chuyến gồm: đã đến điểm đón, đã đón khách, đang thực hiện chuyến và hoàn thành chuyến. |
| FR-17 | Cập nhật vị trí Tài xế | Hệ thống phải cập nhật vị trí của Tài xế để Khách hàng theo dõi trong quá trình thực hiện chuyến. |
| FR-18 | Hủy chuyến | Hệ thống phải cho phép Khách hàng hủy chuyến và xử lý việc hủy theo chính sách của doanh nghiệp. |
| FR-19 | Ghi nhận hoàn thành chuyến | Hệ thống phải ghi nhận chuyến xe hoàn thành khi Tài xế kết thúc chuyến. |

### 9.5. Tính cước và thanh toán

| ID | Functional Requirement | Mô tả |
|---|---|---|
| FR-20 | Tính cước thực tế | Hệ thống phải tính cước thực tế của chuyến xe sau khi chuyến xe hoàn thành. |
| FR-21 | Thanh toán tiền mặt | Hệ thống phải cho phép Khách hàng thanh toán tiền mặt cho Tài xế sau khi hoàn thành chuyến. |
| FR-22 | Xác nhận thanh toán tiền mặt | Hệ thống phải cho phép Tài xế xác nhận đã nhận tiền từ Khách hàng. |
| FR-23 | Gửi yêu cầu thanh toán điện tử | Hệ thống phải gửi giao dịch đến Payment Gateway khi Khách hàng chọn thanh toán điện tử và ấn Đặt xe. |
| FR-24 | Xử lý kết quả thanh toán điện tử | Hệ thống phải kiểm tra và ghi nhận kết quả thanh toán điện tử thành công hoặc thất bại. |
| FR-25 | Xử lý thanh toán thất bại | Hệ thống phải thông báo cho Khách hàng khi thanh toán điện tử thất bại và không tạo yêu cầu đặt xe. |
| FR-26 | Ghi nhận thanh toán | Hệ thống phải ghi nhận trạng thái thanh toán của chuyến xe sau khi thanh toán được hoàn tất. |

### 9.6. Thông báo

| ID | Functional Requirement | Mô tả |
|---|---|---|
| FR-27 | Thông báo đang tìm Tài xế | Hệ thống phải thông báo cho Khách hàng khi chưa tìm được Tài xế và hệ thống đang tiếp tục tìm kiếm. |
| FR-28 | Thông báo Tài xế nhận chuyến | Hệ thống phải thông báo cho Khách hàng thông tin Tài xế khi Tài xế chấp nhận chuyến. |
| FR-29 | Thông báo kết quả thanh toán | Hệ thống phải thông báo cho Khách hàng kết quả thanh toán điện tử thành công hoặc thất bại. |
| FR-30 | Thông báo hoàn thành chuyến | Hệ thống phải thông báo cho Khách hàng khi chuyến xe hoàn thành. |

### 9.7. Đánh giá Tài xế

| ID | Functional Requirement | Mô tả |
|---|---|---|
| FR-31 | Đánh giá Tài xế | Hệ thống phải cho phép Khách hàng đánh giá Tài xế sau khi chuyến xe hoàn thành. |
| FR-32 | Lưu đánh giá | Hệ thống phải lưu kết quả đánh giá gắn với chuyến xe tương ứng. |

### 9.8. Quản trị vận hành

| ID | Functional Requirement | Mô tả |
|---|---|---|
| FR-33 | Quản lý Khách hàng | Hệ thống phải cho phép Nhân viên vận hành tra cứu và quản lý thông tin Khách hàng. |
| FR-34 | Quản lý Tài xế | Hệ thống phải cho phép Nhân viên vận hành tra cứu và quản lý thông tin Tài xế. |
| FR-35 | Quản lý phương tiện | Hệ thống phải cho phép Nhân viên vận hành tra cứu và quản lý thông tin phương tiện. |
| FR-36 | Quản lý chuyến đi | Hệ thống phải cho phép Nhân viên vận hành tra cứu và theo dõi thông tin chuyến đi. |
| FR-37 | Xử lý sự cố | Hệ thống phải hỗ trợ Nhân viên vận hành theo dõi và xử lý các trường hợp phát sinh trong quá trình vận hành. |
| FR-38 | Báo cáo hoạt động | Hệ thống phải cung cấp báo cáo về số chuyến, doanh thu, tỷ lệ hoàn thành, tỷ lệ hủy và hiệu quả hoạt động của Tài xế. |
| FR-39 | Xem báo cáo quản lý | Hệ thống phải cho phép Ban lãnh đạo xem các báo cáo phục vụ theo dõi và đánh giá hoạt động kinh doanh. |
### 9.9. Mapping Business Requirements và Functional Requirements

| BR ID | Business Requirement | Functional Requirements liên quan |
|---|---|---|
| BR-01 | Quản lý tài khoản khách hàng | FR-01, FR-02, FR-03 |
| BR-02 | Tạo yêu cầu đặt xe | FR-05, FR-06, FR-07, FR-08 |
| BR-03 | Tự động tìm và phân công tài xế | FR-11, FR-12 |
| BR-04 | Xử lý từ chối hoặc không phản hồi | FR-14 |
| BR-05 | Theo dõi và cập nhật chuyến đi | FR-09, FR-16, FR-17, FR-19 |
| BR-06 | Tính cước và thanh toán | FR-20, FR-21, FR-22, FR-26 |
| BR-07 | Tích hợp thanh toán điện tử | FR-23, FR-24 |
| BR-08 | Thông báo sự kiện chuyến đi | FR-27, FR-28, FR-29, FR-30 |
| BR-09 | Đánh giá tài xế | FR-31, FR-32 |
| BR-10 | Quản lý vận hành | FR-33, FR-34, FR-35, FR-36, FR-37 |
| BR-11 | Báo cáo hoạt động | FR-38 |
| BR-12 | Báo cáo cho ban lãnh đạo | FR-39 |
| BR-13 | Bảo vệ dữ liệu | FR-02, FR-03 |
| BR-14 | Khả năng mở rộng | Yêu cầu phi chức năng, không ánh xạ trực tiếp đến FR |
| BR-15 | Quản lý hồ sơ tài xế | FR-03, FR-04 |
| BR-16 | Theo dõi và xử lý sự cố | FR-36, FR-37 |
| BR-17 | Thông báo khi không tìm được tài xế | FR-13, FR-27 |
| BR-18 | Xử lý thanh toán thất bại | FR-24, FR-25, FR-29 |
## 10. BUSINESS RULES

### 10.1. Quản lý tài khoản và quyền

| ID | Business Rule | Mô tả |
|---|---|---|
| BRL-01 | Đăng nhập trước khi đặt xe | Khách hàng phải đăng nhập vào hệ thống trước khi có thể tạo yêu cầu đặt xe. |
| BRL-02 | Quản lý trạng thái Tài xế | Tài xế phải cập nhật trạng thái sẵn sàng nhận chuyến trước khi có thể nhận yêu cầu đặt xe. |
| BRL-03 | Phân quyền người dùng | Người dùng chỉ được thực hiện các chức năng phù hợp với vai trò và quyền được cấp. |
| BRL-04 | Bảo vệ thông tin người dùng | Hệ thống phải bảo vệ thông tin cá nhân, dữ liệu vị trí và thông tin giao dịch của Khách hàng và Tài xế. |

### 10.2. Đặt xe và tìm Tài xế

| ID | Business Rule | Mô tả |
|---|---|---|
| BRL-05 | Thông tin đặt xe bắt buộc | Khách hàng phải cung cấp điểm đón, điểm đến và loại xe trước khi đặt xe. |
| BRL-06 | Hiển thị giá dự kiến | Hệ thống phải tính và hiển thị giá dự kiến cho Khách hàng trước khi xác nhận đặt xe. |
| BRL-07 | Chọn phương thức thanh toán | Khách hàng phải lựa chọn phương thức thanh toán tiền mặt hoặc thanh toán điện tử trước khi ấn Đặt xe. |
| BRL-08 | Tạo yêu cầu đặt xe bằng tiền mặt | Nếu Khách hàng chọn tiền mặt, hệ thống phải tạo yêu cầu đặt xe ngay sau khi Khách hàng ấn Đặt xe. |
| BRL-09 | Thanh toán điện tử trước khi tìm Tài xế | Nếu Khách hàng chọn thanh toán điện tử, hệ thống phải gửi giao dịch đến Payment Gateway ngay sau khi Khách hàng ấn Đặt xe và chỉ tạo yêu cầu đặt xe khi thanh toán thành công. |
| BRL-10 | Thanh toán điện tử thất bại | Nếu giao dịch thanh toán điện tử thất bại, hệ thống phải thông báo cho Khách hàng và không tạo yêu cầu đặt xe. |
| BRL-11 | Tìm Tài xế phù hợp | Hệ thống chỉ gửi yêu cầu chuyến xe đến Tài xế đang ở trạng thái sẵn sàng và phù hợp với yêu cầu đặt xe. |
| BRL-12 | Tiếp tục tìm Tài xế | Nếu chưa tìm được Tài xế phù hợp, hệ thống phải tiếp tục tìm kiếm cho đến khi có Tài xế phù hợp hoặc yêu cầu đặt xe bị hủy. |
| BRL-13 | Tài xế từ chối hoặc không phản hồi | Nếu Tài xế từ chối hoặc không phản hồi yêu cầu, hệ thống phải tiếp tục tìm Tài xế khác. |
| BRL-14 | Xác nhận chuyến | Chuyến xe chỉ được xác nhận khi có Tài xế chấp nhận yêu cầu. |

### 10.3. Thực hiện và hủy chuyến

| ID | Business Rule | Mô tả |
|---|---|---|
| BRL-15 | Hủy chuyến | Khách hàng được phép hủy chuyến và việc hủy chuyến phải được xử lý theo chính sách của Công ty ABC. |
| BRL-16 | Cập nhật trạng thái chuyến | Tài xế phải cập nhật trạng thái chuyến theo trình tự: đã đến điểm đón → đã đón khách → đang thực hiện chuyến → hoàn thành chuyến. |
| BRL-17 | Cập nhật vị trí Tài xế | Vị trí của Tài xế phải được cập nhật trong quá trình thực hiện chuyến để Khách hàng có thể theo dõi. |
| BRL-18 | Ghi nhận hoàn thành chuyến | Hệ thống phải ghi nhận chuyến xe hoàn thành khi Tài xế kết thúc chuyến. |

### 10.4. Tính cước và thanh toán

| ID | Business Rule | Mô tả |
|---|---|---|
| BRL-19 | Tính cước thực tế | Sau khi chuyến xe hoàn thành, hệ thống phải tính và ghi nhận cước thực tế của chuyến xe. |
| BRL-20 | Thanh toán tiền mặt sau chuyến | Với phương thức tiền mặt, Khách hàng phải thanh toán cho Tài xế sau khi chuyến xe hoàn thành. |
| BRL-21 | Xác nhận thanh toán tiền mặt | Tài xế phải xác nhận đã nhận tiền từ Khách hàng sau khi thanh toán tiền mặt. |
| BRL-22 | Ghi nhận thanh toán điện tử | Với phương thức thanh toán điện tử, hệ thống phải ghi nhận giao dịch đã thanh toán sau khi Payment Gateway trả về kết quả thành công. |
| BRL-23 | Ghi nhận trạng thái thanh toán | Hệ thống phải ghi nhận trạng thái thanh toán của từng chuyến xe. |

### 10.5. Thông báo và đánh giá

| ID | Business Rule | Mô tả |
|---|---|---|
| BRL-24 | Thông báo sự kiện chuyến đi | Hệ thống phải gửi thông báo cho Khách hàng và Tài xế khi xảy ra các sự kiện quan trọng như đang tìm Tài xế, Tài xế nhận chuyến, thanh toán và hoàn thành chuyến. |
| BRL-25 | Đánh giá sau chuyến | Khách hàng chỉ được đánh giá Tài xế sau khi chuyến xe đã hoàn thành. |
## 11. NON-FUNCTIONAL REQUIREMENTS

### 11.1. Hiệu năng (Performance)

| ID | Non-Functional Requirement | Mô tả |
|---|---|---|
| NFR-01 | Thời gian phản hồi | Hệ thống phải phản hồi các thao tác thông thường của người dùng trong thời gian hợp lý và không gây gián đoạn quá trình sử dụng. |
| NFR-02 | Tốc độ xử lý đặt xe | Hệ thống phải xử lý yêu cầu đặt xe nhanh chóng sau khi Khách hàng xác nhận đặt xe, ngoại trừ thời gian phụ thuộc vào các dịch vụ bên ngoài như Payment Gateway. |
| NFR-03 | Cập nhật trạng thái chuyến | Hệ thống phải cập nhật trạng thái chuyến kịp thời để Khách hàng và Tài xế nhận biết được trạng thái hiện tại của chuyến xe. |
| NFR-04 | Cập nhật vị trí | Hệ thống phải cập nhật vị trí Tài xế định kỳ trong quá trình thực hiện chuyến để hỗ trợ Khách hàng theo dõi hành trình. |

### 11.2. Tính khả dụng và ổn định (Availability & Reliability)

| ID | Non-Functional Requirement | Mô tả |
|---|---|---|
| NFR-05 | Hoạt động liên tục | Hệ thống phải có khả năng hoạt động liên tục để phục vụ việc đặt xe và theo dõi chuyến. |
| NFR-06 | Xử lý lỗi | Khi một chức năng hoặc dịch vụ gặp lỗi, hệ thống phải thông báo trạng thái phù hợp và hạn chế ảnh hưởng đến các chức năng khác. |
| NFR-07 | Không mất dữ liệu | Hệ thống phải đảm bảo dữ liệu tài khoản, chuyến xe và giao dịch không bị mất trong quá trình xử lý thông thường. |
| NFR-08 | Phục hồi sau sự cố | Hệ thống phải có cơ chế sao lưu và phục hồi dữ liệu khi xảy ra sự cố hệ thống hoặc cơ sở dữ liệu. |
| NFR-09 | Xử lý giao dịch an toàn | Hệ thống phải đảm bảo một giao dịch thanh toán hoặc yêu cầu đặt xe không bị ghi nhận trùng khi xảy ra lỗi kết nối hoặc người dùng gửi lại yêu cầu. |

### 11.3. Bảo mật (Security)

| ID | Non-Functional Requirement | Mô tả |
|---|---|---|
| NFR-10 | Xác thực người dùng | Hệ thống phải xác thực người dùng trước khi cho phép truy cập các chức năng yêu cầu đăng nhập. |
| NFR-11 | Phân quyền truy cập | Hệ thống phải kiểm soát quyền truy cập dựa trên vai trò của Khách hàng, Tài xế, Nhân viên vận hành và Ban lãnh đạo. |
| NFR-12 | Bảo vệ mật khẩu | Mật khẩu người dùng phải được bảo vệ bằng cơ chế lưu trữ an toàn và không được lưu dưới dạng văn bản thuần. |
| NFR-13 | Bảo vệ dữ liệu truyền tải | Dữ liệu trao đổi giữa ứng dụng và máy chủ phải được truyền qua kết nối an toàn. |
| NFR-14 | Bảo vệ dữ liệu cá nhân | Hệ thống phải bảo vệ thông tin cá nhân, thông tin phương tiện và dữ liệu vị trí của Khách hàng và Tài xế khỏi truy cập trái phép. |
| NFR-15 | Bảo vệ dữ liệu thanh toán | Hệ thống phải hạn chế lưu trữ thông tin thanh toán nhạy cảm và phải xử lý dữ liệu thanh toán thông qua Payment Gateway phù hợp. |
| NFR-16 | Nhật ký hoạt động | Hệ thống phải ghi nhận các thao tác quan trọng để phục vụ kiểm tra, theo dõi và truy vết khi cần thiết. |

### 11.4. Khả năng mở rộng (Scalability)

| ID | Non-Functional Requirement | Mô tả |
|---|---|---|
| NFR-17 | Mở rộng người dùng | Hệ thống phải có khả năng đáp ứng số lượng Khách hàng và Tài xế tăng lên trong tương lai mà không cần xây dựng lại toàn bộ hệ thống. |
| NFR-18 | Mở rộng chức năng | Hệ thống phải cho phép bổ sung các chức năng mới mà hạn chế ảnh hưởng đến các chức năng hiện có. |
| NFR-19 | Mở rộng dịch vụ tích hợp | Hệ thống phải có khả năng tích hợp thêm các nhà cung cấp thanh toán, thông báo hoặc dịch vụ hỗ trợ khác trong tương lai. |

### 11.5. Khả năng sử dụng (Usability)

| ID | Non-Functional Requirement | Mô tả |
|---|---|---|
| NFR-20 | Giao diện dễ sử dụng | Giao diện phải rõ ràng, trực quan và phù hợp với người dùng phổ thông. |
| NFR-21 | Quy trình đặt xe rõ ràng | Các bước đặt xe phải được trình bày theo trình tự dễ hiểu: nhập thông tin hành trình → chọn loại xe → xem giá dự kiến → chọn phương thức thanh toán → đặt xe. |
| NFR-22 | Hiển thị trạng thái rõ ràng | Hệ thống phải hiển thị rõ trạng thái chuyến xe, trạng thái tìm Tài xế và trạng thái thanh toán để người dùng dễ theo dõi. |
| NFR-23 | Thông báo lỗi dễ hiểu | Khi xảy ra lỗi, hệ thống phải hiển thị thông báo rõ ràng và dễ hiểu, giúp người dùng biết nguyên nhân hoặc hướng xử lý phù hợp. |

### 11.6. Khả năng bảo trì (Maintainability)

| ID | Non-Functional Requirement | Mô tả |
|---|---|---|
| NFR-24 | Dễ bảo trì và nâng cấp | Hệ thống phải được thiết kế theo các thành phần có chức năng rõ ràng để thuận tiện cho việc sửa lỗi, bảo trì và nâng cấp. |
| NFR-25 | Tài liệu kỹ thuật | Các thành phần chính của hệ thống như cơ sở dữ liệu, API và các module phải có tài liệu kỹ thuật cần thiết để hỗ trợ bảo trì và phát triển. |

### 11.7. Tương thích và tích hợp (Compatibility & Integration)

| ID | Non-Functional Requirement | Mô tả |
|---|---|---|
| NFR-26 | Tương thích thiết bị | Hệ thống phải có giao diện phù hợp với các thiết bị phổ biến mà Khách hàng và Tài xế sử dụng. |
| NFR-27 | Tương thích trình duyệt | Giao diện quản trị phải hoạt động ổn định trên các trình duyệt web phổ biến. |
| NFR-28 | Tích hợp Payment Gateway | Hệ thống phải hỗ trợ kết nối với Payment Gateway để gửi yêu cầu thanh toán và nhận kết quả giao dịch. |
| NFR-29 | Tích hợp Notification Provider | Hệ thống phải hỗ trợ kết nối với nhà cung cấp dịch vụ thông báo để gửi thông báo đến Khách hàng và Tài xế. |
## 11.8 TỔNG HỢP NON-FUNCTIONAL REQUIREMENTS
| Nhóm | Các NFR |
|---|---|
| **Hiệu năng (Performance)** | NFR-01, NFR-02, NFR-03, NFR-04 |
| **Tính khả dụng và ổn định (Availability & Reliability)** | NFR-05, NFR-06, NFR-07, NFR-08, NFR-09 |
| **Bảo mật (Security)** | NFR-10, NFR-11, NFR-12, NFR-13, NFR-14, NFR-15, NFR-16 |
| **Khả năng mở rộng (Scalability)** | NFR-17, NFR-18, NFR-19 |
| **Khả năng sử dụng (Usability)** | NFR-20, NFR-21, NFR-22, NFR-23 |
| **Khả năng bảo trì (Maintainability)** | NFR-24, NFR-25 |
| **Tương thích và tích hợp (Compatibility & Integration)** | NFR-26, NFR-27, NFR-28, NFR-29 |
