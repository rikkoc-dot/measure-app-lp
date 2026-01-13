# MeasureApp LP - GitHub & Netlify デプロイ手順

## 📦 プロジェクトの準備完了

✅ ランディングページ作成完了
✅ Git リポジトリ初期化済み
✅ 全ファイルコミット済み

## 🚀 デプロイ手順

### ステップ1: GitHubリポジトリの作成

1. GitHubにアクセス: https://github.com/new
2. リポジトリ名を入力: `measure-app-lp` (または任意の名前)
3. 公開設定: **Public** または **Private** を選択
4. **リポジトリの作成時は、README、.gitignore、ライセンスは追加しない**（既に作成済みのため）
5. 「Create repository」をクリック

### ステップ2: ローカルリポジトリとGitHubを連携

作成したGitHubリポジトリのページに表示されるコマンドを使用します：

```bash
# プロジェクトディレクトリに移動
cd measure-app-lp

# GitHubリポジトリをリモートとして追加（YOUR_USERNAMEを実際のユーザー名に変更）
git remote add origin https://github.com/YOUR_USERNAME/measure-app-lp.git

# mainブランチにプッシュ
git push -u origin main
```

💡 **ヒント**: GitHubのユーザー名とパスワード（またはPersonal Access Token）の入力が求められます。

### ステップ3: Netlifyでデプロイ

#### 方法A: Netlify Web UI（推奨）

1. Netlifyにアクセス: https://app.netlify.com
2. 「Add new site」→「Import an existing project」をクリック
3. 「Deploy with GitHub」を選択
4. Netlifyに GitHub アクセスを許可
5. リポジトリリストから「measure-app-lp」を選択
6. ビルド設定（自動検出されるはず）:
   - **Build command**: (空欄のまま)
   - **Publish directory**: `.` (ルートディレクトリ)
7. 「Deploy site」をクリック

#### 方法B: Netlify CLI（オプション）

Netlify CLIをインストール済みの場合：

```bash
# プロジェクトディレクトリで実行
netlify init

# デプロイ
netlify deploy --prod
```

### ステップ4: カスタムドメインの設定（オプション）

1. Netlifyダッシュボードで「Domain settings」に移動
2. 「Add custom domain」をクリック
3. ドメイン名を入力
4. DNS設定を更新:
   - ドメインレジストラで、NetlifyのネームサーバーまたはAレコードを設定

## 📝 デプロイ後の自動更新

GitHubにプッシュすると、Netlifyが自動的に再デプロイします：

```bash
# 変更を加えた後
git add .
git commit -m "Update: 変更内容"
git push origin main
```

## 🎨 プロジェクト構成

```
measure-app-lp/
├── index.html          # メインのランディングページ
├── netlify.toml        # Netlify設定ファイル
├── README.md          # プロジェクト説明
└── .git/              # Gitリポジトリ
```

## 🔧 トラブルシューティング

### 問題: GitHubへのプッシュが失敗する

**解決策**:
- Personal Access Tokenを使用してください
- GitHub設定 → Developer settings → Personal access tokens → Generate new token
- 必要な権限: `repo` (フルアクセス)

### 問題: Netlifyでビルドエラーが出る

**解決策**:
- ビルドコマンドは空欄のままにしてください（静的HTMLサイトのため）
- Publish directoryが `.` になっているか確認

### 問題: サイトが表示されない

**解決策**:
- `index.html` がルートディレクトリにあることを確認
- Netlifyのデプロイログを確認

## 📱 公開されたサイト

デプロイ完了後、Netlifyから以下のようなURLが発行されます：

```
https://your-site-name.netlify.app
```

このURLをシェアして、世界中の人にMeasureAppを紹介できます！

## 🌟 次のステップ

- [ ] カスタムドメインの設定
- [ ] Google Analyticsの追加
- [ ] OGP画像の追加（SNSシェア用）
- [ ] 問い合わせフォームの追加
- [ ] 実際のApp Storeリンクの追加（アプリリリース後）

---

## 💡 参考リンク

- [GitHub公式ドキュメント](https://docs.github.com)
- [Netlify公式ドキュメント](https://docs.netlify.com)
- [開発ストーリー（note記事）](https://note.com/endless_flight/n/n999dc56a2208)

---

質問や問題がある場合は、エンドレスフライトまでお気軽にお問い合わせください！
