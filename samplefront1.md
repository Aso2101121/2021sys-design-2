```uml
@startuml
opt 検索
 ユーザー -> WEBサーバー:キーワードで検索
 WEBサーバー -> DBサーバー:キーワードを渡す
 DBサーバー -> DBサーバー:キーワードを基にSQLで検索
 DBサーバー -> WEBサーバー:結果を表示
 alt 成功
  WEBサーバー -> ユーザー:商品を表示
 else 失敗
  WEBサーバー -> ユーザー:エラーを表示
 end
end
@enduml
```
