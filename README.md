## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user



## user テーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, foreign_key: true|
|email|string|null: false, foreign_key: true|
|password|string|null: false, foreign_key: true|


### Association
- has_many :group, through: :groups_users
- has_many :message


## message テーブル

|Column|Type|Options|
|------|----|-------|
|image|text||
|body|text|null: false|
|user_id|integer|null: false, foreign_key: true|


### Association
- belongs_to :group
- belongs_to :user


## group テーブル

|Column|Type|Options|
|------|----|-------|
|menber|string||

### Association
- has_many :message
- has_many :user, through: :groups_users