# Windows向け Podman セットアップ & docker-compose ファイル起動ガイド

## 1. Podman のインストール（Windows）

1. [Podman公式サイト](https://podman-desktop.io/downloads) にアクセス
2. 「Windows」の、**installer** をダウンロード
3. ダウンロードした `.exe` ファイルを実行してインストール

> インストール後、スタートメニューから **Podman Desktop** を起動できます。


## 2. Podman マシンの初期化と起動

Podman は Linux 仮想マシン上で動作します。初回は以下のコマンドで仮想マシンを作成・起動します。<br>
**Visual Studio Code**の上メニューのターミナルを選択→新しいターミナルを選択。<br>
表示されたコマンドラインで以下コマンドを実行
```powershell
podman machine init
podman machine start
```

> これにより、Linux 環境がバックグラウンドで動作します。



##  4. コンテナの起動と停止


---

起動
```powershell
podman-compose up
```
停止
```
podman-compose down
```
###  podman compose up の主なパラメーター一覧

| オプション             | 説明                                                                 |
|------------------------|----------------------------------------------------------------------|
| `--build`              | サービスのイメージを起動前にビルドする                                |
| `--detach` または `-d` | バックグラウンドでコンテナを起動する（ログを表示しない）              |
| `--force-recreate`     | 既存のコンテナを強制的に再作成する                                   |
| `--no-build`           | イメージのビルドをスキップする（既存のイメージを使用）                |
| `--no-recreate`        | 既存のコンテナがあれば再作成せずにそのまま使う                        |
| `--remove-orphans`     | compose ファイルに含まれていない不要なコンテナを削除する              |
| `--quiet-pull`         | イメージのプル時に出力を抑える                                       |
| `--wait`               | コンテナが起動完了するまで待機する（秒数指定も可能）                  |

> 例：コンテナを再ビルドし、バックグラウンドで立ち上げる<br>
> `podman compose up -d --build`

## 5. 動作確認
コンテナ起動後、URLで画面が表示されれば動作確認完了！<br>
[→URL](./DevEnv.md#webから編集する際のurl)
