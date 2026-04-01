flowchart LR
    APP["TTE Application
Document Upload / Access"]:::app

    DB1["MariaDB Master
Jakarta"]:::dbmaster
    DB2["MariaDB Slave
Cikarang"]:::dbslave
    DB3["MariaDB Slave
Batam"]:::dbslave
    DB4["MariaDB Slave
Bandung"]:::dbslave

    M1["MinIO Primary
Jakarta"]:::storage
    M2["MinIO Replica
Cikarang"]:::storage
    M3["MinIO Replica
Batam"]:::storage
    M4["MinIO Replica
Bandung"]:::storage

    APP --> DB1
    APP --> M1

    DB1 --> DB2
    DB1 --> DB3
    DB1 --> DB4

    M1 --> M2
    M1 --> M3
    M1 --> M4

    M2 --> M1
    M3 --> M1
    M4 --> M1

    classDef app fill:#264653,color:#fff,stroke:#1b263b,stroke-width:2px;
    classDef dbmaster fill:#c1121f,color:#fff,stroke:#780000,stroke-width:2px;
    classDef dbslave fill:#e76f51,color:#fff,stroke:#9c6644,stroke-width:2px;
    classDef storage fill:#2a9d8f,color:#fff,stroke:#1d3557,stroke-width:2px;
