message　テーブル
text|text|
image|string|
group_id|integer|null:false,foreign_key: true|
user_id|integer|null:false,foreign_key: true|

アソシエーション
belongs_to :group
belongs_to :user

userテーブル
name|string|null:false,add_index:true|
email|string|null:false,unique:true|

アソシエーション
has_many :groups_users
has_many :groups, through: groups_users
has_many :messages

groupsテーブル
group_name|string|null:false|null:false,unique: true|

アソシエーション
has_many :groups_users
has_many :users, through: groups_users
has_many :messages


groups＿userテーブル
user_id|integer|null:false,foreign_key: true|
group_id|integer|null:false, foreign_key: true|

アソシエーション
belongs_to :group
belongs_to :user
