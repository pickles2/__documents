# Pickles 2 Desktop Tool - Auto Updater

Pickles 2 v2.0.0-beta.23 以降搭載される自動更新機能についてメモします。


## 自動更新の大まかな仕組み

npm パッケージ [`node-webkit-updater`](https://www.npmjs.com/package/node-webkit-updater) を利用した仕組みを組み込んでいます。 詳しくはドキュメントを参照してください。


## manifestUrl

[manifest](https://pickles2.pxt.jp/release/app/Pickles2/package.json) は下記に置かれています。

https://pickles2.pxt.jp/release/app/Pickles2/package.json

```json
{
    "name": "Pickles2",
    "version": "2.0.0-beta.22",
    "manifestUrl": "https://pickles2.pxt.jp/release/app/Pickles2/package.json",
    "packages": {
        "mac": {
            "url": "https://github.com/pickles2/app-pickles2/releases/download/2.0.0-beta.22/Pickles2-2.0.0-beta.22-osx64.zip"
        },
        "win": {
            "url": "https://github.com/pickles2/app-pickles2/releases/download/2.0.0-beta.22/Pickles2-2.0.0-beta.22-win32.zip"
        },
        "linux32": {
            "url": "https://github.com/pickles2/app-pickles2/releases/download/2.0.0-beta.22/Pickles2-2.0.0-beta.22-linux64.zip"
        }
    }
}
```

新しいバージョンが公開されると、このJSONファイルが更新されます。

アプリケーションは、このJSON中の `version` の値を、自身のバージョン番号と比較し、より新しい場合にアップデートを促します。

実際のインストーラー(初めてインストールするときと同じZIPファイル)は、GitHubに置かれています。


## 開発版ビルド

開発版ビルドでは、正式版の manifest とは別の [manifest](https://pickles2.pxt.jp/release/app_dev/Pickles2/package.json) を参照するようにしています。

https://pickles2.pxt.jp/release/app_dev/Pickles2/package.json

インストーラーパッケージが置かれているのも、 同様に https://pickles2.pxt.jp/ のドメイン内です。 次の開発版がアップロードされるときに、前のバージョンのインストーラーは削除される可能性があります。

正式版ビルドと開発版ビルドでは `manifestUrl` が異なるため、 正式版 から 開発版 へのアップデート、 開発版 から 正式版 へのアップデートが 自動では行われることはありません。
