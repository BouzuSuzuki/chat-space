# README

## users
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, add_index: true|
|mail|string|null: false, unique: true|
|password|integer|null: false|
|password confirmation|integer|null: false|

### Association
has_many :groups_users
has_many :groups. through: :groups_users
has_many :chats

## groups_users
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|string|null: false, foreign_key: true|

### Association
belongs_to :group
belongs_to :user

## chat
|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
belongs_to :group
belongs_to :user

## groups
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
has_many: groups_users
has_many: users through: :groups_users
has_many :chats
