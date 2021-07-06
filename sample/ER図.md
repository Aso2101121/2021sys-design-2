```uml
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

entity "顧客マスタ" as customer <m_customers><<M,MASTER_MARK_COLOR>>{
  + customer code [PK]
  --
  pass
  name
  address
  tel
  mail
  del_flag
  reg.date
}

entity "購入テーブル" as order <d_purchase><<D,TRANSACTION_MARK_COLOR>>{
  + order_id [PK]
  --
  order_id
  customer_code
  purchase_date
  total_price
}

entity "購入テーブル詳細" as detail <d_purchase_detail><<D,TRANSACTION_MARK_COLOR>>{
  + detail_id [PK]
  + order_id [PK]
  --
  detail_id
  order_id
  item_code
  price
  num
}

entity "カテゴリテーブル" as category <m_category><<D,TRANSACTION_MARK_COLOR>>{
  + category_id [PK]
  --
  category_id
  name
  reg_date
}

@enduml
```
