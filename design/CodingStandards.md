# Pickles 2 プロジェクト コーディング規約

## 目的

- 多様なエンジニアがプロジェクトに参加し、貢献できること。
- 新しい技術を受け入れ、目的達成のために最大限活用すること。
- 様々なパッケージを効率よく開発し、メンテナンスすること。

これらを同時に成立するために必要な最低限のコーディング規則を規定します。

## プロジェクトの構成

大きく、PHP の Pickles 2 プロジェクト と、編集をサポートするデスクトップGUIアプリケーション で構成されています。

Pickles 2 プロジェクトは、 PHP のフレームワークである [pickles2/px-fw-2.x](https://github.com/pickles2/px-fw-2.x) と、いくつかのプラグイン、プロジェクトテンプレートとして [pickles2/preset-get-start-pickles2](https://github.com/pickles2/preset-get-start-pickles2) などで構成されています。

デスクトップアプリケーションには、 [Pickles 2](https://github.com/pickles2/app-pickles2) や [Asazuke](https://github.com/pickles2/electron-asazuke) などがあり、 Node.js と NW.js , Electron などのフレームワーク上に実装されています。

[Pickles2-SeriesDesign.pdf](Pickles2-SeriesDesign.pdf) を参照してください。

## パッケージ管理・命名規則

- Pickles 2 グループ [https://github.com/pickles2](https://github.com/pickles2) に新しいリポジトリを追加する場合、先に開発者個人スペースで開発をし、ある程度稼働できる段階まできた時点で、コミュニティの合意を得てから 移管するようにします。
- 各パッケージの命名規則について [Package Naming Conventions](package_naming_conventions.md) を参照してください。
- 各パッケージは、 特別な理由がない限り [MIT License](https://opensource.org/licenses/MIT) でライセンスし、公共の利益に貢献します。

## ディレクトリの構成

- `README.md` - パッケージの機能、使い方その他の情報を記載します。
- `tests/` - テスト関連のファイルを格納します。
- `submodules/` - Gitのサブモジュールを格納します。
- `node_modules/` - npmパッケージを展開します。
- `vendor/` - composerパッケージを展開します。

## コーディングスタイル・命名規則

特に規則は設けません。
誰でも読みやすく、メンテナンスしやすくなるように配慮してください。

## 禁止事項・制限事項

- PHPのエラーは、Noticeレベルまで表示する設定の環境を前提にし、すべて発生しないようにします。

## 推奨事項

- 使用言語
    - 特に理由がなければ [PHP](http://php.net/) を使用します。
    - デスクトップツールは JavaScript ([Node.js](https://nodejs.org/ja/), [NW.js](https://nwjs.io/) or [Electron](https://electron.atom.io/)) を使用します。
- テスト
    - PHP では `composer test`, Node.js では `npm test` のコマンドでテストコードを実行できるようにします。

## `px2package` と `broccoli.json`

これは、 Pickles 2 や [broccoli-html-editor](https://github.com/broccoli-html-editor) のプラグインなど関連パケージの情報を効率よく記述するための仕様です。

[px2package](px2package.md) および [broccoli-html-editor の README](https://github.com/broccoli-html-editor/broccoli-html-editor) を参照してください。

## その他の重要なこと

エンジニア個別の文化的背景、新しい技術やツール、経験、スキルレベルについて、多様なメンバーの参加を歓迎します。 このため、次の点について配慮します。

- 新しい技術の採用に当たっては、あくまで目的達成のための合理性を考慮して決定します。個人的な趣向に偏った基準による選択は避けます。
- 言語の採用や実装のレビュー等に際して、他のメンバーが読みやすく、理解しやすく、メンテナンスしやすくなるよう、可能な限りの配慮をします。
- 他のメンバーが、ある知識やスキルを持っていることを強要したり、それがないことを理由に排除したりしません。 知識がないメンバーは、あなたのコードや使用した言語、ツールなどについて聞くことがありますが、そのときは、快く説明するようにしてください。
- また、知らないことがあるときは、恥ずかしがらずに聞きましょう。 〜聞くは一時の恥、聞かぬは一生の恥〜
