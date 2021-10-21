# テーブル設計

## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| name               | string | null: false |
| email              | string | null: false |
| encrypted_password | string | null: false |
| profile            | text   | null: false |
| position           | text   | null: false |    
| occupation         | text   | null: false |

### Association

- has_many :comments
- has_many :prototypes

## comments テーブル

| Column      | Type       | Options                        |
| ----------- | ---------- | ------------------------------ |
| prototype   | references | null: false, foreign_key: true |
| user        | references | null: false, foreign_key: true |
| content     | text       | null: false                    |

### Association

- belongs_to :users
- belongs_to :prototypes

## prototypes テーブル

| Column     | Type       | Options                        |
| ---------- | ---------- | ------------------------------ |
| title      | string     | null: false                    |           |
| catch_copy | text       | null: false,                   |
| user       | references | null: false, foreign_key: true |
| concept    | text       | null: false                    | 

### Association

- has_many   :comments
- belongs_to :user
