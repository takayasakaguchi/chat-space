# README
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|username|string|null: false|
### Association
- has_many :groups
- has_many :message
- has_many  :groups,  through:  :users_groups

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|groupname|text|null: false|
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- has_many :message
- has_many  :users,  through:  :users_groups

## users_groupsテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group

## messageテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string|null: false|
|username_id|integer|null: false, foreign_key: true|
|groupname_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user