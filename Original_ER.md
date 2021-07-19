package "ECサイト" as target_system {

entity "会員情報テーブル" {
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

entity "購入テーブル" {
  + order_id [PK]
  --
  user_id [FK]
  purchase_date
  total
}

entity "購入詳細テーブル" {
  + detail_id [PK]
  + order_id [PK]
  --
  item_id [FK]
  price
  quantity
}

entity "商品テーブル" {
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

entity "カテゴリーテーブル" {
  + category_id [PK]
  --
  category_name
  bland
}

}
