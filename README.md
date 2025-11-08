# privacy-policy

https://eteoto.github.io/privacy-policy/

このリポジトリは、各サービス・アプリのプライバシーポリシーを管理・公開するためのものです。

## プライバシーポリシーの追加方法

新しいサービスのプライバシーポリシーを追加する場合は、以下の手順に従ってください。

### 0. 作業ブランチの作成

mainブランチから新しいブランチを切って作業します：

```bash
# mainブランチに切り替え、最新の状態に更新
git checkout main
git pull origin main

# 新しいブランチを作成して切り替え
git checkout -b add-privacy-policy-[service-name]
```

### 1. プライバシーポリシードキュメントの作成

`docs/` ディレクトリに新しいMarkdownファイルを作成します。

```bash
touch docs/[service-name].md
```

### 2. プライバシーポリシーの内容を記述

作成したMarkdownファイルに、以下の基本構造でプライバシーポリシーを記述します：

```markdown
# [サービス名] プライバシーポリシー

最終更新日: YYYY/MM/DD

## 1. はじめに

[サービスの説明とプライバシーポリシーの目的]

## 2. 収集する情報

### 2.1 個人情報
### 2.2 使用情報

## 3. 情報の使用目的

## 4. 第三者への情報提供

## 5. お問い合わせ

## 6. 改定について
```

### 3. インデックスページの更新

`index.html` を編集して、新しいプライバシーポリシーへのリンクを追加します：

```html
<ul>
  <li><a href="docs/audio-aging.md">オーディオエイジング: スピーカー慣らし & 音質向上 プライバシーポリシー</a></li>
  <li><a href="docs/[service-name].md">[新しいサービス名] プライバシーポリシー</a></li>
</ul>
```

### 4. 変更をコミット・プッシュ

```bash
git add .
git commit -m "Add privacy policy for [service-name]"
git push origin add-privacy-policy-[service-name]
```

### 5. プルリクエストの作成

GitHubでプルリクエストを作成します：

1. GitHubのリポジトリページにアクセス
2. 「Compare & pull request」ボタンをクリック
3. プルリクエストのタイトルと説明を記入
   - タイトル例: `Add privacy policy for [service-name]`
   - 説明例: `[service-name]アプリのプライバシーポリシーを追加`
4. 「Create pull request」をクリック

### 6. プルリクエストのレビューとマージ

1. 必要に応じてレビューを受ける
2. 問題がなければ「Squash and merge」でmainブランチにマージ

### 7. GitHub Pages での反映確認

数分後に https://eteoto.github.io/privacy-policy/ にアクセスして、新しいプライバシーポリシーが正しく表示されることを確認します。

## ファイル構成

```
.
├── README.md           # このファイル
├── index.html          # トップページ（プライバシーポリシー一覧）
├── style.css          # スタイルシート
└── docs/
    ├── audio-aging.md  # オーディオエイジングアプリのプライバシーポリシー
    └── [service-name].md # その他のサービスのプライバシーポリシー
```

## 注意事項

- **ブランチ運用**: 変更は必ず作業ブランチで行い、プルリクエストを通してmainブランチにマージしてください
- GitHub Pages の設定で、`docs` フォルダがドキュメントルートに設定されています
- プライバシーポリシーの内容は、各サービスの実際の機能に応じて適切に記述してください
