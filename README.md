# Fess-test
PoC検証用

Fessのセットアップ
起動ファイルの作成
適当なフォルダーを作成して、 `compose.yaml` と `compose-opensearch2.yaml` をダウンロードします。

curlコマンドで以下のように取得することもできます。
```
curl -o compose.yaml https://raw.githubusercontent.com/codelibs/docker-fess/master/compose/compose.yaml
curl -o compose-opensearch2.yaml https://raw.githubusercontent.com/codelibs/docker-fess/master/compose/compose-opensearch2.yaml
```
Fessの起動
Fessをdocker composeコマンドで起動します。

コマンドプロンプトを開き、compose.yamlファイルがあるフォルダーに移動して、以下のコマンドを実行します。

```
docker compose -f compose.yaml -f compose-opensearch2.yaml up -d
```
動作確認
`http://localhost:8080/ `にアクセスすることによって、起動を確認できます。

管理 UI は `http://localhost:8080/admin/` です。 デフォルトの管理者アカウントのユーザー名/パスワードは、admin/adminになります。 管理者アカウントはアプリケーションサーバーにより管理されています。 Fessの管理 UI では、アプリケーションサーバーで fess ロールで認証されたユーザーを管理者として判断しています。

その他
Fessの停止
Fessの停止は、Fessを起動したフォルダーで、以下のコマンドを実行します。
```
docker compose -f compose.yaml -f compose-opensearch2.yaml down
```
管理者パスワードの変更
管理 UI のユーザー編集画面で変更することができます。
