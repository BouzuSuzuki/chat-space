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
has_many :groups_users
has_many :groups. through: :groups_users
has-many :chat

## groups_users
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|groups|string|null: false, foreign_key: true|

### Association
belong_to :group
belong_to :user

## chat
|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
belongs_to :group
belongs_to :user

## groups
|Column|Type|Options|
|------|----|-------|
|group id|integer|null: false, foreign_key: true|
|group_name|string|null: false|

### Association
has_many: groups_users
has_many: users through: :groups_users
belongs_to :chat