# Snowflake-Data-Architecture-for-Insights
Build a scalable Snowflake data pipeline for data files, using a centralized Task engine for Stream-to-table moves.
```mermaid
   graph LR
    subgraph Data_Source
        A[Amazon S3<br><i>Raw Data</i>]
    end
    subgraph Ingestion
        B[SnowPipe<br><i>Auto-Ing</i>]
    end
    subgraph Landing
        C[Schema<br><i>Raw Store</i>]
        D[Layer<br><i>Stream</i>]
    end
    subgraph Process
        E[Curated<br><i>Stream</i>]
    end
    subgraph Consume
        F[Layer<br><i>BI-Ready, Stream</i>]
    end
    subgraph Monitor
        G[Alerts<br><i>Query Logs</i>]
        R[Dash<br><i>Visuals</i>]
    end
    A -->|Event| B
    B --> C
    C --> D
    D --> E
    E --> F
    B --> G
    D --> G
    F --> R
