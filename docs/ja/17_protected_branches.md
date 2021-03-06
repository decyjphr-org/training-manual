## 保護されたブランチ と `CODEOWNERS`

ワークフローによっては、重要なブランチにマージするコードに、必要な確認やピアレビューを受けさせるため、そのブランチを保護したいという時があると思います。 **Protected Branches** や **Code Owners** など、方法はいくつかあります。

### 保護されたブランチ

リポジトリメンテナは、特定ブランチへの定められた基準に満たないマージを阻止することができます。 その基準は、ピアレビューや、継続的インテグレーションサービスとコードクオリティなどのインテグレーションによるテスト、特定のコード所有者の変更へのレビューと承認などです。

保護されたブランチを有効にしましょう。

1. **Settings** のタブを選択します。
2. 画面の左側のメニューから **Branches** を選択します。
3. ドロップダウンの **Choose a branch...** を選択し、保護したいブランチを選択します。例えば、`main`。
4. **Protect this branch** のオプションにチェックを入れます。

他のオプションにチェックを付けない場合の基本的なブランチ保護は、フォースプッシュとそのブランチの削除を防ぎます。 利用可能なオプションの詳細については、[この機能のドキュメント](https://help.github.com/articles/defining-the-mergeability-of-pull-requests/) を参照してください。

### CODEOWNERS

リポジトリメンテナは、**CODEOWNERS** を作成することで、変更を確認する必要のある人やチームを細かく決めることができます。 例えば、CODEOWNERSは以下のように使用できます。

- チームのJavascriptの専門家には、全ての`.js` 拡張子のファイルを確認させる
- 技術仕様書チームには、全ての`docs/` フォルダの変更を確認させる
- セキュリティチームには、`package.json` に書いてある、新しい依存ファイルを確認させる

CODEOWNERS のファイルを作成しましょう。

1. リポジトリで `CODEOWNERS` という新しいファイルを作成します（拡張子は不要）。 `.github/` ディレクトリに追加することもできます。
2. 最初の一行目 に`*          @YOUR_USERNAME` を入力します。
    - 以降の行に記載された一致する項目が優先されない限り、あなたがリポジトリの全てのデフォルトのオーナーであることを意味します。
3. 次の行に、`*.js       @githubteacher` を入力します。
    - 記載する順番が重要になります。 指定された変更の最後に一致する項目が優先されます。
4. CODEOWNERS のファイルを作成したので、ブランチ保護設定に戻り、**Require pull request reviews before merging** と **Require review from Code Owners** というオプションを選択します。 忘れずに **Save changes** をクリックしましょう。

CODEOWNERS ファイルの書き方の詳細については、[ドキュメント](https://help.github.com/articles/about-codeowners/) を参照してください。
