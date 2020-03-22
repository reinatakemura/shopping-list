# DB Design
## users_table
|Column|Type|Options|
|------|----|-------|
|email|string|null: false, unique:true|
|password|string|null: false|
|name|string|null: false, index: true|
### Association
- has_many :users_items
- has_many :items, through: :users_items

## items_table
|Column|Type|Options|
|------|----|-------|
|image|text||
|name|string|null: false, unique:true|
|content|text||
### Association
- has_many :users_items
- has_many :users, through: :users_items
- belongs_to :categories

## users_items_table
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key:true|
|item_id|integer|null: false, foreign_key:true|
### Association
- belongs_to :user
- belongs_to :item

## categories_table
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, unique: true|
### Association
- has_many :items
