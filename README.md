# 23677151_DongThiAnhThu_CABSYSTEM
flowchart TB
    %% Business Stakeholders
    BGĐ["Ban giám đốc"]
    KH["Khách hàng"]
    TX["Tài xế"]
    OPR["Nhân viên vận hành"]
    ADM["Quản trị viên hệ thống"]
    KT["Kế toán / Tài chính"]
    CSKH["Chăm sóc khách hàng"]
    QL["Quản lý / Điều hành"]

    %% Technical Stakeholders
    BA["Business Analyst"]
    DEV["Development Team"]
    IT["DevOps / IT"]

    %% External Systems
    PAY["Payment Provider"]
    MAP["Map / Location Provider"]
    NOTI["Notification Provider"]

    %% Relationships
    BGĐ --> QL
    BGĐ --> BA

    KH --> CAB["CAB System"]
    TX --> CAB
    OPR --> CAB
    ADM --> CAB
    KT --> CAB
    CSKH --> CAB
    QL --> CAB

    BA --> CAB
    DEV --> CAB
    IT --> CAB

    CAB --> PAY
    CAB --> MAP
    CAB --> NOTI
