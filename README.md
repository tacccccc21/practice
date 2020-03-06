## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user



## users テーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, foreign_key: true|
|email|string|null: false, foreign_key: true|
|password|string|null: false, foreign_key: true|


### Association
- has_many :groups, through: :groups_users
- has_many :messages
- has_many :groups_users


## messages テーブル

|Column|Type|Options|
|------|----|-------|
|image|text||
|body|text||
|user_id|integer|null: false, foreign_key: true|
|proup_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group


## groups テーブル

|Column|Type|Options|
|------|----|-------|
|name|string||

### Association
- has_many :messages
- has_many :user, through: :groups_users
- has_many :groups_users