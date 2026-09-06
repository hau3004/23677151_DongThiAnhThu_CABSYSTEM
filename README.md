# 23677151_DongThiAnhThu_CABSYSTEM
flowchart LR
    CAB(("CAB System"))

    subgraph INTERNAL["Internal Stakeholders"]
        BGĐ["Ban giám đốc"]
        OPR["Nhân viên vận hành"]
        ADM["Quản trị viên"]
        KT["Kế toán / Tài chính"]
        CSKH["CSKH"]
        QL["Quản lý / Điều hành"]
        BA["Business Analyst"]
        DEV["Development Team"]
        IT["DevOps / IT"]
    end

    subgraph USERS["End Users"]
        KH["Khách hàng"]
        TX["Tài xế"]
    end

    subgraph EXTERNAL["External Stakeholders"]
        PAY["Payment Provider"]
        MAP["Map / Location Provider"]
        NOTI["Notification Provider"]
    end

    KH --> CAB
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

    BGĐ --> QL
    BGĐ --> BA

    style CAB fill:#2563eb,color:#fff,stroke:#1e40af,stroke-width:3px
    style INTERNAL fill:#dcfce7,stroke:#16a34a
    style USERS fill:#dbeafe,stroke:#2563eb
    style EXTERNAL fill:#fef3c7,stroke:#d97706

    CAB --> NOTI
