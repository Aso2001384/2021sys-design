# データベース詳細

### 商品テーブル
|属性名|型|PK|NN|FK|
|-----|--|--|--|--|
|item_code|int(11)|〇|〇|-|
|item_name|varchar(50)|-|〇|-|
|price|int(11)|-|〇|-|
|category_id|int(11)|-|〇|〇|
|image|varchar(200)|-|〇|-|
|detail|varchar(500)|-|〇|-|
|created_at|date|-|〇|-|
|update_at|timestamp|-|〇|-|
|delete_flg|boolean|-|〇|-|
