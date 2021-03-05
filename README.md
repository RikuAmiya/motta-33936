# テーブル設計

## usersテーブル

| Column     | Type    | Options     |
|------------|---------|-------------|
| email      | string  | null: false, unique: true|
| password   | string  | null: false |
| name       | string  | null: false |
| text       | text    |             |
| image      | string  |             |
| phone      | string  | null: false |

### Association

- has_many :items
- has_many :comments

## itemsテーブル

| Column      | Type       | Options     |
|-------------|------------|-------------|
| food        | string     | null: false |
| concept     | text       | null: false |
| price       | text       | null: false |
| area_id     | integer    | null: false |
| address     | string     | null: false |
| category_id | integer    | null: false |
| user        | references | null: false foreign_key: true |

### Association

- belongs_to :user
- has_many :comments

## commentsテーブル

| Column      | Type       | Options           |
|-------------|------------|-------------------|
| text        | text       | null: false       |
| food        | references | foreign_key: true |
| customer    | references | foreign_key: true |

### Association

- belongs_to :items
- belongs_to :users