# holiday_shring DB設計
## posts_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|post_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :post
- belongs_to :user

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|mail|string|null: false|
|age|integer||
|sex|string||
|password|string|null: false|

### Association
- has_many :posts_users
- has_many :posts, through: :posts_users
- has_many :comments

## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|post_id|integer|null: false, foreign_key: true|
|text|text|null: false|

### Association
- belongs_to :post
- belongs_to :user

## postsテーブル
|Column|Type|Options|
|------|----|-------|
|title|string|null: false|
|text|text|null: false|
|image|text|null: false|
|age|integer|null: false|
|sex|string|null: false|
|times|string|null: false|
|times|string|null: false|

### Association
- has_many :posts_users
- has_many :users, through: :posts_users
- has_many :comments

