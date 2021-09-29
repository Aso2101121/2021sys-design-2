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

entity "購入マスタ" as purchase <m_purchase><<M,MASTER_MARKCOLOR>>{
 + order_id [PK]
 + customer_code[PK][FK]
 --
 parcharse_date
 total_price
}

entity "購入テーブル詳細テーブル" as purchase_detail <d_purcharse_detail><<T,TRANSACTION_MARK_COLOR>> MAIN_ENTITY{
 + detail_id [PK]
 + order_id [PK]
 --
 item_code
 price
 num
}

entity "ユーザ（顧客）マスタ" as customer <m_customers><<M,MASTER_MARK_COLOR>>{
 + customer_code [PK]
 --
 


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

/*
customer   ---ri-o{  items
items      }o-ri---  supplier
customer   ---do-o{  order
items      ---do--- detail
order      }o-ri--- detail
rogin     ---ri---customer
*/
@enduml
```
