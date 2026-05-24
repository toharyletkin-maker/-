graph LR
    subgraph "Уровень представления"
        Client["🌐 Браузер<br>(Клиентская часть)"]
    end

    subgraph "Уровень логики"
        Server["⚙️ Сервер на PHP<br>(Серверная логика)"]
    end

    subgraph "Уровень данных"
        DB[("🗄️ База данных MySQL<br>(Хранение данных)")]
    end

    %% Потоки данных
    Client -->|1. HTTP-запрос<br>(данные форм / AJAX)| Server
    Server -->|2. SQL-запрос<br>(SELECT / INSERT)| DB
    DB -.->|3. Ответ БД<br>(строки / статус)| Server
    Server -.->|4. HTTP-ответ<br>(HTML / JSON)| Client

    %% Стилизация
    style Client fill:#e1f5fe,stroke:#039be5,stroke-width:2px
    style Server fill:#f3e5f5,stroke:#8e24aa,stroke-width:2px
    style DB fill:#efebe9,stroke:#5d4037,stroke-width:2px
# -
