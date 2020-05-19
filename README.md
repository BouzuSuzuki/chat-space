# README

## users
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true, add_index: true|
|name|string|null: false, unique: true|
|mail|string|null: false, unique: true|
|password|integer|null: false|
|password confirmation|integer|null: false|

### Association
has_many :groups
has_many :groups. through: :groups_users
has-many :chat

## groups_users
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|groups|string|null: false, foreign_key: true|

### Association
has-many :groups
has-many :users

## chat
|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
has-many :groups
belongs_to :users

## groups
|Column|Type|Options|
|------|----|-------|
|group id|integer|null: false, foreign_key: true|
|group_name|string|null: false|

### Association
has_many: users
has_many: users through: :groups_users
belongs_to :chat