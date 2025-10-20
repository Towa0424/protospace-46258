# テーブル設計

## users テーブル

| Column            | Type   | Options                   |
| ----------------- | ------ | ------------------------- |
| email             | string | null: false, unique: true |
| encypted_password | string | null: fales               |
| name              | string | null: fales               |
| profile           | text   | null: fales               |
| occupation        | text   | null: fales               |
| position          | text   | null: fales               |

### Association

- has_many :prototypes
- has_many :comments

# prototype テーブル

| Column     | Type       | Options                        |
| ---------- | ---------- | ------------------------------ |
| title      | string     | null: false                    |
| catch_copy | text       | null: false                    |
| concept    | text       | null: false                    |
| user       | references | null: fales, foreign_key: true |

### Association

- belong_to :user
- has_many :comments

# comments テーブル

| Column    | Type       | Options                        |
| ----------| ---------- | ------------------------------ |
| content   | test       | null: false                    |
| prototype | references | null: false, foreign_key: true |
| user      | references | null: false, foreign_key: true |

### Association

- belong_to :user
- belong_to :prototype

