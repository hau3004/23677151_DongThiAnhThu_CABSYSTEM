# 23677151_DongThiAnhThu_CABSYSTEM
flowchart LR

    CAB(("CAB System"))

    %% =========================
    %% END USERS
    %% =========================
    subgraph USERS["End Users"]
        KH["Khách hàng"]
        TX["Tài xế"]
    end

    %% =========================
    %% INTERNAL STAKEHOLDERS
    %% =========================
    subgraph INTERNAL["Internal Stakeholders"]
        BGĐ["Ban giám đốc"]
        OPR["Nhân viên vận hành"]
        ADM["Quản trị viên hệ thống"]
        KT["Kế toán / Tài chính"]
        CSKH["Chăm sóc khách hàng"]
        QL["Quản lý / Điều hành"]
    end

    %% =========================
    %% PROJECT TEAM
    %% =========================
    subgraph TEAM["Project Team"]
        BA["Business Analyst"]
        DEV["Development Team"]
        IT["DevOps / IT"]
    end

    %% =========================
    %% EXTERNAL PROVIDERS
    %% =========================
    subgraph EXTERNAL["External Providers"]
        PAY["Payment Provider"]
        MAP["Map / Location Provider"]
        NOTI["Notification Provider"]
    end

    %% =========================
    %% RELATIONSHIPS
    %% =========================

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

    %% =========================
    %% STYLES
    %% =========================

    style CAB fill:#2563EB,color:#FFFFFF,stroke:#1E40AF,stroke-width:3px

    style USERS fill:#DBEAFE,stroke:#2563EB,stroke-width:2px
    style INTERNAL fill:#DCFCE7,stroke:#16A34A,stroke-width:2px
    style TEAM fill:#F3E8FF,stroke:#9333EA,stroke-width:2px
    style EXTERNAL fill:#FEF3C7,stroke:#D97706,stroke-width:2px

    style KH fill:#FFFFFF,stroke:#2563EB
    style TX fill:#FFFFFF,stroke:#2563EB

    style BGĐ fill:#FFFFFF,stroke:#16A34A
    style OPR fill:#FFFFFF,stroke:#16A34A
    style ADM fill:#FFFFFF,stroke:#16A34A
    style KT fill:#FFFFFF,stroke:#16A34A
    style CSKH fill:#FFFFFF,stroke:#16A34A
    style QL fill:#FFFFFF,stroke:#16A34A

    style BA fill:#FFFFFF,stroke:#9333EA
    style DEV fill:#FFFFFF,stroke:#9333EA
    style IT fill:#FFFFFF,stroke:#9333EA

    style PAY fill:#FFFFFF,stroke:#D97706
    style MAP fill:#FFFFFF,stroke:#D97706
    style NOTI fill:#FFFFFF,stroke:#D97706

    ```mermaid
flowchart LR
...
```

