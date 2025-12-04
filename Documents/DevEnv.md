# 開発環境まとめ（Node-RED + PostgreSQL + pgAdmin）

## 使用技術スタック

| サービス     | イメージ             | ポート       | 備考                         |
|--------------|------------------------|--------------|------------------------------|
| Node-RED     | `nodered/node-red`     | `1880`       | フローエディタ              |
| PostgreSQL   | `postgres:15`          | `5432`       | データベース本体            |
| pgAdmin      | `dpage/pgadmin4`       | `8080`       | WebベースのDB管理ツール     |



## 接続情報まとめ

### PostgreSQL
- Host: `localhost`（ホストからアクセス）または `postgres`（コンテナ間）
- Port: `5432`
- User: `myuser`
- Password: `mypassword`
- Database: `mydb`


pgAdmin で PostgreSQL に接続する際の設定例：

- **Host name/address**: `postgres`
- **Port**: `5432`
- **Username**: `myuser`
- **Password**: `mypassword`

## Webから編集する際のURL
### pgAdmin
- URL: http://localhost:8080
- Email: `admin@example.com`
- Password: `adminpass`
### Node-RED
- URL: http://localhost:1880

## 備考
- Node-RED に PostgreSQL ノードを追加するには、パレットの管理から `node-red-node-postgres` をインストール。
- データ永続化にはボリュームを使用（例：`postgres_data`, `nodered_data`）。
- コンテナの起動・停止は `podman compose up -d` / `podman compose down` で管理。

