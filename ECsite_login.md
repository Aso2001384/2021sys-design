```uml
@startuml

ユーザー -> Webサーバー : ログイン
Webサーバー -> DBサーバー : ログイン照会
DBサーバー -> DBサーバー : ログイン処理
DBサーバー -> Webサーバー : 認証結果
Webサーバー -> ユーザー : 認証結果

activate ユーザー

olt 認証成功
Webサーバー -> ユーザー : ユーザー名を表示

else 認証失敗
Webサーバー -> ユーザー : 失敗メッセージを表示

end

opt ログイン中

ユーザー -> Webサーバー : ログアウト
Webサーバー -> DBサーバー : ログアウト照会
DBサーバー -> DBサーバー : ログアウト処理
DBサーバー -> Webサーバー : ログアウト結果

end

deactivate ユーザー
@enduml
```
