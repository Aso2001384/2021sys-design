# データベース詳細

### 商品テーブル
|属性名|型|PK|NN|FK|
|-----|--|--|--|--|
|item_id|int(11)|〇|〇|-|
|item_name|varchar(50)|-|〇|-|
|price|int(11)|-|〇|-|
|brand|varchar(20)|-|-|-|
|category_id|int(11)|-|〇|〇|
|image|varchar(200)|-|〇|-|
|detail|varchar(500)|-|〇|-|
|created_at|date|-|〇|-|
|update_at|timestamp|-|〇|-|
|delete_flg|boolean|-|〇|-|

### カテゴリーテーブル
|属性名|型|PK|NN|FK|
|-----|--|--|--|--|
|category_id|int(11)|〇|〇|-|
|category_name|varchar(50)|-|〇|-|
|brand|varchar(20)|-|-|-|

### 会員情報テーブル
|属性名|型|PK|NN|FK|
|-----|--|--|--|--|
|user_id|int(11)|〇|〇|-|
|user_name|varchar(20)|-|〇|-|
|pass|varchar(50)|-|〇|-|
|email|varchar(100)|-|〇|-|
|tel|varchar(20)|-|〇|-|
|address|varchar(100)|-|〇|-|

### 購入テーブル
|属性名|型|PK|NN|FK|
|-----|--|--|--|--|
|order_id|int(11)|〇|〇|-|
|user_id|int(11)|-|〇|-|
|purchase_date|date|-|〇|-|
|total|int(11)|-|〇|-|

### 購入詳細テーブル
|属性名|型|PK|NN|FK|
|-----|--|--|--|--|
|detail_id|int(11)|〇|〇|-|
|order_id|int(11)|〇|〇|〇|
|item_id|int(11)|-|〇|〇|
|quantity|int(11)|-|〇|-|
