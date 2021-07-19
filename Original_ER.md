```
@startuml

skinparam class {
    backgroundColor white
    ArrowColor Black
}


package "ECサイト" as target_system {

entity "会員情報テーブル" as customer <customer>{
    + user_id [PK]
    --
    user_name
    pass
    email
    tel
    address
    created_at
    delete_flag
  }

entity "購入テーブル" as order <order>{
  + order_id [PK]
  --
  user_id [FK]
  purchase_date
  total
}

entity "購入詳細テーブル" as detail <detail>{
  + detail_id [PK]
  + order_id [PK]
  --
  item_id [FK]
  price
  quantity
}

entity "商品テーブル" as item <item>{
  + item_id [PK]
  --
  item_name
  price
  bland
  category_id [FK]
  image
  detail
  created_at
  update_at
  delete_flg
}

entity "カテゴリーテーブル" as category <category>{
  + category_id [PK]
  --
  category_name
  bland
}

customer  |o-ri-o{     order 
order     ||-ri-|{     detail 
detail    }-do-||     item 
item      }o-le-||     category 

}

@enduml
```
