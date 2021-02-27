
## users テーブル

| Column | Type   | Options     |
| ------ | ------ | ----------- |
| email  | string | null: false |
| name   | string | null: false |
|password| string | null: false |
|profile | string | null: false |
|occupation| text | null: false |
|position| text   | null: false |

association
-has_many :prototypes
-has_many :comments


## prototypes テーブル

| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| title   | string    | null: false |
| catch_copy| text    | null: false |
| concept  | text     | null: false |
| user   | references | null: false, foreign_key: true |

association
-belongs_to :users
has_many :comments


## comments テーブル

| Column  | Type       | Options                        |
| ------- | ---------- | ------------------------------ |
| text    | text       | null: false                               |
| user    | references | null: false, foreign_key: true |
| prototype| references | null: false, foreign_key: true |

association
-belongs_to :users
-belongs_to :prototype
