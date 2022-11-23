```mermaid
erDiagram
    EVENTS }|--|{ CONTES : plays
    CONTES ||--o{ ITEMS : has
    EVENTS ||--o{ DATES : bookings
    EVENTS ||--o{ STAFFS : works
```
