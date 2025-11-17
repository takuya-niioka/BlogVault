# Giscus コメント機能 セットアップガイド

このガイドでは、BlogVaultにgiscusコメント機能を設定する方法を説明します。

## 前提条件

- GitHubアカウント
- giscusアプリをインストールするための公開GitHubリポジトリ
- そのリポジトリでGitHub Discussionsを有効化

## セットアップ手順

### 1. GitHubリポジトリの準備

1. **新しいリポジトリを作成**（または既存のリポジトリを使用）
   - 例: `blog-comments` というリポジトリを作成
   - リポジトリは **公開（Public）** にする必要があります

2. **GitHub Discussionsを有効化**
   - リポジトリの Settings → General
   - Features セクションで "Discussions" にチェック

3. **Discussionカテゴリの設定**
   - Discussions タブを開く
   - デフォルトで "Announcements" カテゴリが存在することを確認
   - 必要に応じて新しいカテゴリを作成

### 2. giscusの設定値を取得

1. **giscus設定サイトにアクセス**
   - https://giscus.app にアクセス

2. **リポジトリを入力**
   - 「リポジトリ」欄に `ユーザー名/リポジトリ名` を入力
   - 例: `takuya-niioka/blog-comments`
   - giscusがリポジトリを検証します

3. **Discussion カテゴリを選択**
   - ページをスクロールして「Discussion カテゴリ」を選択
   - "Announcements" を推奨（または任意のカテゴリ）

4. **設定値をコピー**
   - ページ下部に生成されたスクリプトが表示されます
   - 以下の値をメモ：
     - `data-repo-id`: リポジトリID
     - `data-category-id`: カテゴリID

### 3. config.tomlに設定値を反映

`config.toml` の giscus セクションを編集：

```toml
[params.giscus]
  enable = true
  repo = "あなたのGitHubユーザー名/リポジトリ名"  # 例: "takuya-niioka/blog-comments"
  repoId = "取得したREPO_ID"  # giscus.appから取得
  category = "Announcements"  # 選択したカテゴリ名
  categoryId = "取得したCATEGORY_ID"  # giscus.appから取得
  mapping = "pathname"
  reactionsEnabled = "1"
  emitMetadata = "0"
  inputPosition = "bottom"
  theme = "preferred_color_scheme"
  lang = "en"
```

### 4. 動作確認

1. **Hugoサイトをビルド**
   ```bash
   hugo server -D
   ```

2. **ブラウザで確認**
   - ブログ記事ページの下部にコメントセクションが表示されることを確認
   - コメントを投稿してテスト

3. **GitHubで確認**
   - コメントがGitHub Discussionsに反映されていることを確認

## 設定オプション

### テーマの変更

`theme` パラメータで見た目を変更できます：

- `preferred_color_scheme`: ユーザーのシステム設定に従う（推奨）
- `light`: ライトテーマ
- `dark`: ダークテーマ
- `dark_dimmed`: ダークディムドテーマ
- `transparent_dark`: 透明ダークテーマ
- `noborder_light` / `noborder_dark`: ボーダーなし

### マッピング方法

`mapping` パラメータでコメントとページの関連付け方法を選択：

- `pathname`: URLパスで関連付け（推奨）
- `url`: 完全なURLで関連付け
- `title`: ページタイトルで関連付け
- `og:title`: OGタイトルで関連付け

### 特定の記事でコメントを無効化

記事のFront Matterに以下を追加：

```yaml
disable_comments: true
```

## 多言語対応

現在の設定では、言語に応じて自動的にgiscusの表示言語が切り替わります：

- 英語ページ: 英語でコメント表示
- 日本語ページ: 日本語でコメント表示

## トラブルシューティング

### コメントが表示されない

1. リポジトリが公開されているか確認
2. GitHub Discussionsが有効になっているか確認
3. repoId と categoryId が正しいか確認
4. ブラウザの開発者ツールでエラーを確認

### コメントが GitHub Discussions に反映されない

1. giscus アプリがリポジトリにインストールされているか確認
   - https://github.com/apps/giscus からインストール
2. リポジトリの権限設定を確認

## 参考リンク

- [giscus 公式サイト](https://giscus.app/)
- [giscus GitHub リポジトリ](https://github.com/giscus/giscus)
- [Hugo PaperMod テーマ](https://github.com/adityatelange/hugo-PaperMod)




























