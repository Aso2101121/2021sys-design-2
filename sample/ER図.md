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

entity "購入テーブル詳細" as detail <d_purchase_detail><<M,MASTER_MARK_COLOR>>{
  + detail_id [pk]
  order_id [pk]
  --
  detail_id
  order_id
  item_code
  price
  num
}
@enduml
```
