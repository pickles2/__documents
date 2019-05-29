# Pickles 2 Package Information (draft)

Pickles 2 では、composerを通じてさまざまな種類のパッケージを取り込み、拡張できるよう設計されています。 しかし、 composer は Pickles 2 とは直接関係しないパッケージも同時に読み込んでいるはずです。

この仕様は、composerパッケージが Pickles 2 に対してどのように作用するものかを記述するためのものです。

## 概要

composer が読み込む `composer.json` の仕様を拡張し、 `px2package` を追加します。

```json
{
    "name": "your/package-name",
    "description": "-------",
    "require": {
        /* ---------------- */
    },
    "require-dev": {
        /* ---------------- */
    },
    "extra": {
        "px2package": {
            "id": "the-theme-name",
            "name": "The Theme Name",
            "type": "theme",
            "path": "px-files/themes/pickles2/"
        }
    }
}
```

## 仕様

### px2package->extra->id

パッケージのID。

テーマパッケージ(`type` が `theme` の場合)が、初回にインポートされる際に、デフォルトのIDとして参照されます。

テーマパッケージ以外では省略します。

### px2package->extra->name

パッケージの呼称。

### px2package->extra->type

パッケージの種類。
`type` には、次の種類を記述できます。

- `project` - プロジェクト
- `theme` - テーマ (`pickles2/px2-multitheme` 仕様に準拠)
- `processor` - プロセッサ
- `plugin` - その他のプラグイン

※ モジュールは外部のライブラリ `broccoli-html-editor` 依存のため、ここでは定義しません。代わりに、 `broccoli-html-editor` が定義する `broccoli.json` を参照します。

### px2package->extra->path

パッケージデータを格納したパス。
パッケージ自身のルートパスからの相対パスで記述します。

`type` が `project` の場合は、 Entry Script (通常は `.px_execute.php`) のパスを記述します。

### px2package->extra->path_homedir

`type` が `project` の場合に設定可能です。
プロジェクトのホームディレクトリ(通常は `px-files/`) のパスを設定します。
省略時は `px-files/` 、またはクライアントツールに設定されている場合はそのパスが使用されます。


## 複数のパッケージ情報を定義

1つのパッケージに異なる複数の機能が含まれる場合があります。
`px2package` を配列として定義し、この要素として情報を記述してください。

```json
{
    "name": "your/package-name",
    "description": "-------",
    "require": {
        /* ---------------- */
    },
    "require-dev": {
        /* ---------------- */
    },
    "extra": {
        "px2package": [
            {
                "name": "The Sample Site",
                "type": "project",
                "path": ".px_execute.php",
                "path_homedir": "px-files/"
            },
            {
                "id": "the-theme-1",
                "name": "The Theme 1",
                "type": "theme",
                "path": "px-files/themes/theme1/"
            },
            {
                "id": "the-theme-2",
                "name": "The Theme 2",
                "type": "theme",
                "path": "px-files/themes/theme2/"
            }
        ]
    }
}
```
