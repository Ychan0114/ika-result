# README

## usersテーブル
| Column | Type | Options |
|:-----------|------------:|:------------:|
|nickname|string|null:false|
|user_id_name|string|null:false, unique: true|
|password|string|null:false|
|password_confirmation|string|null:false|

### Association
- has_many :groups
- has_many :results

## groupsテーブル
| Column | Type | Options |
|:-----------|------------:|:------------:|
|name|string|null:false|

- belongs_to :user
- has_many :results

## scoresテーブル
| Column | Type | Options |
|:-----------|------------:|:------------:|
|rule|string|null:false, index: true|
|stage|string|null:false, index: true|
|result|string|null:false|
|weapon|string|null:false, index: true|
|kill|integer|null:false|
|death|integer|null:false|
|special|integer|null:false|
|paint_point|integer|null:false|
|user_id|references|null:false, foreign_key:true|
|group_id|references|null:false, foreign_key:true|

### Association
- belongs_to :user
- belongs_to :group
