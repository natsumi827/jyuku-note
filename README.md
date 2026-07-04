# 塾講師ノート

通常授業・夏期講習をクラス／生徒単位で分けて、授業記録とテスト成績（苦手・得意分析つき）を管理する1ファイルのWebアプリです。ビルド不要、`index.html` を開くだけで動きます。

## データの保存について
このブラウザの `localStorage` に保存されます（Claude上のプレビューとは別の仕組みです）。**同じ端末・同じブラウザでしか見られません**。複数端末で使いたい場合は、後でSupabase等のクラウド同期を追加できます（前に作られた就活手帳アプリと同じ構成にできます）。

## AI対策提案（任意機能）
苦手な範囲を入力してある科目には「対策をAIに提案」ボタンが出ますが、これを使うには右上の「設定」からご自身のAnthropic APIキーを登録する必要があります。キーはこのブラウザにのみ保存され、他のサーバーには送られません。
**注意：** ブラウザから直接APIを呼ぶ都合上、開発者ツールを見ればキーが読み取れてしまいます。個人利用にとどめ、リポジトリやサイトを公開する場合はキーをコードに書き込まない・登録しないようにしてください。

## GitHub Pagesへの公開手順

1. GitHubで新しいリポジトリを作成（例：`juku-note`）
2. このフォルダの `index.html` をそのリポジトリ直下に追加してコミット・プッシュ
   ```bash
   git init
   git add index.html README.md
   git commit -m "初回コミット：塾講師ノート"
   git branch -M main
   git remote add origin https://github.com/【あなたのユーザー名】/juku-note.git
   git push -u origin main
   ```
3. GitHubのリポジトリ画面で「Settings」→「Pages」を開く
4. 「Source」を `Deploy from a branch` にし、Branch を `main` / `/(root)` に設定して保存
5. 数分後、`https://【あなたのユーザー名】.github.io/juku-note/` でアクセスできるようになります

就活手帳アプリと同じ要領です。PWA化（ホーム画面に追加できるようにする）やSupabaseでの複数端末同期をしたくなったら、いつでも声かけてください。
