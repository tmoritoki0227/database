%%{init:{'theme':'default'}}%%
erDiagram

users {
  integer id PK "ユーザーID"
  string email "メールアドレス"
  string password "パスワード"
}

users ||--|| user_profiles : "1:1"
user_profiles {
  integer user_id FK "ユーザーID"
  string name "ユーザー名"
  string tel "電話番号"
  integer gender "性別"
  date birthday "誕生日"
  string postal_code "郵便番号"
  string address "住所詳細"
}

items {
  integer id PK "アイテムID"
  string name "アイテム名"
}

tags {
  integer id PK "タグID"
  string name "タグ名"
}

items ||--|{ item_tags: "1:N"
tags ||--|{ item_tags: "1:N"
item_tags {
  integer item_id FK "アイテムID"
  integer tag_id FK "タグID"
}

orders }|--|| users: "N:1"
orders }|--|| items: "N:1"
orders {
  integer id PK "オーダーID"
  integer user_id FK "ユーザーID"
  integer item_id FK "アイテムID"
}
