## マージのテストと`.yml`ファイル

継続的インテグレーションを使用する前に、`.yml`ファイルと、このプロジェクトのために作成したテストを追加する必要があります。

1. 使用しているCI/CDサービスに応じて、適切なブランチから、`base: main`に`<service>-tests`という名前の Pull Request を作成します。
2. Pull Request はマージ**しないでください**。

> `.yml` ファイルを開くと、重要な情報が表示されます。 その情報については、後で詳しく説明します。 それを見てみて、どういう意味だと思いますか？ どんな質問が浮かびますか？
