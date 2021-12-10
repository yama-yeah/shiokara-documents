# ブランチについて
- Git flowというモデルで開発を進めようと考えています。
  - [提唱された記事](https://nvie.com/posts/a-successful-git-branching-model/)
  - [日本語で説明されてる記事](https://cloudsmith.co.jp/blog/efficient/2020/08/1534208.html)
  - 以上の形に沿って、**今回の開発に適した形で**の運用を行います。
  - 以下は今回のブランチモデルで扱う基本的なブランチ３種です
- `main`ブランチは各スプリントの成果をマージしていきます。()
- `develop`ブランチは基本の開発ブランチです。ここからブランチを切って開発してください。
- `feature/hoge(hogeは任意の機能名)`例：feature/login-screen

# コミットについ
- コミットメッセージはわかりやすければ基本なんでもいいです。日本語でも英語でも構いませんが、英語がめちゃくちゃでも意味が通じればいいので、文法などはあまり気にせず。
  - ダメな例: "おやすみコミット", "多分動くと思います"
- 内容は任せますが、そのコミットの方向性がわかるprefixをつけてください。(prefixって何って人は聞いてください)
  - `add:` 機能などの追加を行った時
  - `fix:` バグ修正
  - `refactor:` 仕様に影響がないコード改善(リファクタ)
  - 例：`git commit -m "add: fetch tasks function for api class"`
- 進捗全然ねえ～という場合でも作業ブランチであれば他の人に迷惑かけないので積極的にコミットしましょう。具体的にいうなら2時間に1回程度が望ましいです。(Gitは作業内容を戻せるからどんどんやりましょう)

# Pull Request(以下PR)について
- 基本は各featureブランチからdevelopブランチにマージしたい時、つまりはfeatureブランチで開発していた機能が完成した時などにPRを出してください。
- PRでは、一人以上のコードレビューを必須にします。基本的には下記を見るようにしてください。
  - 変なファイルやコードが無いか
  - 関数名、変数名などが適切か
  - 今後バグをはらみそうな危険なコード（可読性が著しく低い、無駄な処理がある、無駄な変数がある、など）がないか