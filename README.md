# megmeg Design プロフィールサイト

参照：261005_portfolio_web用ベース.pdf。内容と薄いグレーの面、中央の名前、広い余白を引き継ぎ、指定に合わせてアクセントをモノトーン化。

## 構成
- `index.html`：名前・Profile・全11件のSelected Works・Contact
- `style.css`：PC / スマートフォン共通のスタイル
- `assets/favicon.svg`：サイトアイコン
- `.nojekyll`：静的ファイルをそのまま配信

ビルドや外部サービス、JavaScriptは不要。本文・欧文は端末の書体を使用。Profile見出しは元PDFのParlareの字形をSVGパスへ変換し、罫線との重なりを再現。フォントファイルは配信しません。

## GitHub Pages公開
1. `megmegdesign` アカウントに **megmegdesign.github.io** という独立した公開リポジトリを作成。
2. このフォルダのファイルをリポジトリ直下へ配置（既存Toolsリポジトリへは入れない）。
3. Settings → Pages → Deploy from a branch → main / (root) を選択。
4. 公開後に https://megmegdesign.github.io/ の表示・連絡先を確認してから名刺のQRを作成。

Contact：megmeg.design@gmail.com（メールリンク）。

Works / Portfolioは現段階では表示しません。

## 状態
ローカル初期版。リモートリポジトリ作成・アップロード・公開は未実施。
