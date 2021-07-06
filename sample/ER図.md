```uml
@startuml
entity "顧客マスタ" as customer <m_customers>
<<M,MASTER_MARK_COLOR>>{
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
@enduml
```
