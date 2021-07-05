```
@startuml

!define MASTER_MARK_COLOR Orange
!define TRANSACTION_MARK_COLOR DeepSkyBlue

skinparam class {
    '図の背景
    BackgroundColor Snow
    '図の枠
    BorderColor Black
    'リレーションの色
    ArrowColor Black
}

package "ECサイト" as target_system {

entity "顧客マスタ" as customer <m_customers>{
    + customer_code [PK]
    --
    pass
    name
    address
    tel
    mail
    del_flag
    reg_date
  }
 
 entity "購入テーブル" as order <d_purchase>{
    + order_id[PK]
    --
    customer_code[FK]
    purchase
    total_price
    }
    
entity "購入詳細" as order_ditail <d_purchase_ditail>{
    + order_id[PK]
    + detail_id[PK]
    --
    item_code[FK]
    price
    num
    }

entity "商品マスタ" as items <m_items>{
    + item_code[PK]
    --
    item_name
    price
    category_id[FK]
    image
    detail
    del_flag
    reg_date
    }
    
entity "カテゴリマスタ" as category <m_category>{
    + category_code[PK]
    --
    name
    reg_date
    }

customer       |o-ri-o{     order 
order          ||-ri-|{     order_detail 
order_detail    }-do-||     items 
items          }o-le-||     category 

@enduml
```
