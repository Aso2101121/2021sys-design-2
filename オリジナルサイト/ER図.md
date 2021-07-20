```uml
@startuml
!define MASTER_MARK_COLOR Orange 
!define TRANSACTION_MARK_COLOR DeepSkyBlue
!define MAIN_ENTITY #MintCream-MIstyRose
skinparam class {
    '図の背景
    BackgroundColor Snow
    '図の枠
    BorderColor Black
    'リレーションの色
    ArrowColor Black
}

entity "顧客情報マスタ" as customer <m_customers> <<M,MASTER_MARK_COLOR>>{
 + customer id [PK]
 --
 customer_name
 customer_tel
 customer_email
 customer_adress
 item_id [FK]
 f_lreg_date
}

entity "ログインテーブル" as rogin <d_rogin> <<T,TRANSACTION_MARK_COLOR>> MAIN_ENTITY{
 + rogin_id [PK]
 --
 password
 email
}

entity "商品テーブル" as items <M_items> <<M,MASTER_MARK_COLOR>>{
 + item_id [PK]
 --
 item_name
 price
 supplier_id [FK]
 image
 detail
 del_flag
 reg_date
}

entity "仕入先テーブル" as supplier <d_supplier> <<T,TRANSACTION_MARK_COLOR>> MAIN_ENTITY{
 + supplier_id [PK]
 + item_id [PK][FK]
 --
 supplier
 adress
 tel
 email
 reg_date
}

entity "購入テーブル" as order <d_order> <<T,TRANSACTION_MARK_COLOR>> MAIN_ENTITY{
 + order_id [PK]
 --
 customer_id [FK]
 purchase_date
 total_price
}

entity "購入詳細テーブル" as detail <d_purchase_detail> <<T,TRANSACTION_MARK_COLOR>> MAIN_ENTITY{
 + detail_id [PK]
 + order_id [PK][FK]
 --
 item_code [FK]
 price
 num
}

customer   ---ri-o{  items
items      }o-ri-|{  supplier
customer   ---do-o{  order

@enduml
```
