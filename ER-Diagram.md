# ER図

```mermaid
erDiagram

users ||--o{ assets: "1 : n"
users ||--|{ user_authorities: ""
authorities ||--|{ user_authorities: ""

assets {
    number id PK ""
    string asset_name "アセット名"
    string file_name  "ファイル名(UK)"
    string description "概要・説明"
    number user_id FK "ユーザーID"
}

users {
    number user_id PK "ユーザーID"
    string user_name "ユーザー名"
    string user_email "メールアドレス"
    string password "パスワード"
    number authority_id FK "権限ID"
}

authorities {
    number authority_id PK "権限ID"
    string authority_name "権限"
    string description "概要・説明"
}

user_authorities {
    number user_id PK 
    number authorities_id PK 
}

```