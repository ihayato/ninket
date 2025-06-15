# にんケット 改善アイデア募集サイト

同人即売会イベント「にんケット」の改善提案を集める専用サイトです。

## サイトの目的

次回開催をさらに楽しいものにするため、スタッフ & 参加者の皆さんからのご意見・ご提案を募集しています。小さな気づきでも大歓迎です。

## 技術仕様

- **HTML5** + **CSS3** （バニラJS不使用）
- **レスポンシブデザイン** 対応
- **Google Fonts** (Noto Sans JP) 使用
- **Google Forms** 埋め込み

## セットアップ手順

### 1. Google Form URLの設定

`index.html` ファイル内の以下の部分を実際のGoogle FormのURLに置き換えてください：

```html
<!-- この部分を変更 -->
<iframe 
    src="https://docs.google.com/forms/d/e/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX/viewform?embedded=true"
    ...>
</iframe>

<!-- フォールバックリンクも同様に変更 -->
<a href="https://docs.google.com/forms/d/e/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX/viewform" ...>
```

**Google Form URLの取得方法：**

1. Google Formsで改善提案用フォームを作成
2. 「送信」ボタンをクリック
3. 「< >」（埋め込み）タブを選択
4. 表示されるiframeのsrc属性のURLをコピー
5. 上記コードの `XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX` 部分を置き換え

### 2. ローカルでの確認

```bash
# ファイルをブラウザで開く
open index.html

# または HTTPサーバーで実行（推奨）
python3 -m http.server 8000
# http://localhost:8000 でアクセス
```

### 3. 本番環境へのデプロイ

#### GitHub Pages の場合

1. GitHubリポジトリを作成
2. ファイルをプッシュ
3. Settings > Pages で「Deploy from a branch」を選択
4. ブランチを `main` / `gh-pages` に設定

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/USERNAME/ninket-feedback.git
git push -u origin main
```

#### Netlify の場合

1. [Netlify](https://netlify.com) にサインアップ
2. 「Sites」から「Add new site」
3. 「Deploy manually」を選択
4. ファイルをドラッグ&ドロップ

#### Vercel の場合

```bash
npm install -g vercel
vercel --prod
```

### 4. カスタマイズ

#### ロゴの変更

`index.html` のロゴ部分を実際の画像ファイルに置き換える場合：

```html
<!-- 現在（SVGをbase64エンコード） -->
<img src="data:image/svg+xml;base64,..." alt="にんケットロゴ" class="logo">

<!-- 画像ファイルを使用する場合 -->
<img src="assets/logo.png" alt="にんケットロゴ" class="logo">
```

#### 色の変更

`style.css` でメインカラーを変更：

```css
/* メインカラー（現在：#4CAF50） */
header {
    background-color: #4CAF50; /* ここを変更 */
}

.fallback-link {
    border: 2px dashed #4CAF50; /* ここも変更 */
}
```

## ファイル構成

```
ninket/
├── index.html          # メインページ
├── style.css           # スタイルシート
└── README.md           # このファイル
```

## ブラウザサポート

- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

## ライセンス

MIT License

## お問い合わせ

サイトに関するご質問は、にんケット運営チームまでお願いします。

---

© 2025 NinKET Committee