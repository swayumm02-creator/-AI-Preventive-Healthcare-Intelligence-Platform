```markdown
```mermaid
erDiagram
    PATIENTS {
        int pk_id PK
        string national_health_id
        date registered_date
    }
    SYMPTOM_LOGS {
        int id PK
        int patient_id FK
        string clinical_indicator
        datetime timestamp
    }
    METRICS_TIME_SERIES {
        int record_id PK
        int log_id FK
        float risk_score_index
        string target_day
    }

    PATIENTS ||--o{ SYMPTOM_LOGS : "logs indicators for"
    SYMPTOM_LOGS ||--o{ METRICS_TIME_SERIES : "tracks array vectors"
