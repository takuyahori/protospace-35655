# テーブル設計

## usersテーブル

| Column     | Type   | Options     |
| ---------- | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association

- has_many :comments
- has_many :prototypes

## commentsテーブル

| Column    | Type       | Options           |
| --------- | ---------- | ----------------- |
| text      | string     | null: false       |
| user      | references | foreign_key: true |
| prototype | references | foreign_key: true |

### Association

- belongs_to :user
- belongs_to :prototype

## prototypesテーブル

| Column     | Type         | Options           |
| ---------- | ------------ | ----------------- |
| title      | string       | null: false       |
| catch_copy | text         | null: false       |
| concept    | text         | null: false       |
| image      | ActiveStrage |                   |
| user       | references   | foreign_key: true |

### Association

- has_many :comments
- belongs_to :user