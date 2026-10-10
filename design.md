# megmeg Design — プロフィールサイト デザイン仕様

確定日：2026-10-10。現在の実装とユーザー確認済みの調整を基準とする。
正本：`/Users/taniyama.m/Documents/GitHub/megmegDesign`。
既存のFapp-Mapp-2026-toolsとは独立したサイト・デザインとして管理する。

## 方針

元資料「261005_portfolio_web用ベース.pdf」のミニマルなエディトリアルデザインを継承する。文字・組版・余白を中心に、中央の名前から細い本文列へつなぐ。背景は淡いグレー、文字は黒を基本とし、Profileの筆記体のみ鮮やかな黄色を使用。名刺のQRから閲覧する公開プロフィールを第一用途とする。

## ページ構成

1. 名前／肩書き：エディトリアルデザイナー、Taniyama Megumi、谷山 愛
2. ページ内ナビ：Profile / Selected Works / Contact
3. Profile：元PDFを基にした経歴・制作分野の3段落
4. Selected Works：元PDFの実績11件（テキスト一覧）
5. Contact：megmeg Design、megmeg.design@gmail.com（mailtoリンク）
6. Footer：著作権表記、Back to top

Works / PortfolioとComing soonは現段階では掲載しない。

## 配色

| 用途 | 色 |
| --- | --- |
| ページ全体・誌面背景 | #f5f5f5 |
| Profileの筆記体 | #E6FF00 |
| 本文・主見出し・Profile罫線 | #242424 |
| 補足文字 | #585858 |
| セクション・フッターの罫線 | #a8a8a8 |
| 肩書きラベルの文字 | #ffffff |

肩書きラベルは黒地に白文字。Profileの罫線は黒。元PDFの黄緑色は使わない。

## レイアウト・余白

中央揃えの1カラム。本文・Profile画像・フッターの最大幅を560pxで統一。Profileの文字と罫線は一体のSVGとして本文幅に合わせて比例縮小する。

| 項目 | PC（601px以上） | スマートフォン（600px以下） |
| --- | --- | --- |
| 外側マージン | 32px | 14px |
| 内側左右パディング | 48px | 35px |
| ヒーロー上部余白 | 90px | 50px |
| ヒーロー下部余白 | 90px | 65px |
| ナビ上部余白 | 48px | 36px |
| ナビ行・列の間隔 | 15px / 25px | 8px / 18px |
| Profile見出し下の余白 | 55px | 35px |
| セクション下部余白 | 92px | 66px |

上部余白は初期版の半分に調整済み。375px幅では本文幅277px。固定幅で横スクロールを発生させない。

## タイポグラフィ

日本語：Hiragino Kaku Gothic ProN → Hiragino Sans → Yu Gothic → Meiryo → sans-serif。本文の基本ウェイト300。
欧文：Avenir Next → Avenir → sans-serif。英語の名前はCentury Gothicもフォールバック。名前・ナビ・屋号・フッターのウェイト400。

| 要素 | PC | スマートフォン |
| --- | --- | --- |
| 肩書き | 13px・500・字間.06em | 11px |
| 英語の名前 | 23px・字間.025em | 20px |
| 日本語の名前 | clamp(38px, 5vw, 54px)・300・字間.22em | 同じ式 |
| ナビ | 12px | 11px |
| Profile本文 | 15px・行高2.1・字間.035em | 14px・行高2 |
| セクション見出し | 24px・400・字間.035em | 22px |
| 実績一覧 | 14px・行高1.9 | 13px・行高1.9 |
| 屋号 | 22px | 22px |
| フッター | 11px | 10px |

本文段落下の余白16px。実績一覧は6px角の黒い四角、左インデント15px、項目下余白12px。セクション見出しは1pxの上罫線・上パディング24px。

## Profileの筆記体

`assets/profile-title.svg`を使用。元PDF内のParlare Regularの字形をSVGパスへ変換したもの。Pの上部の曲線と罫線の交差、文字間隔、筆記体の形を元資料から継承。字形の色は#E6FF00、線は#242424。フォントファイルは配信しない。

別の筆記体フォントに置き換えず、このSVGを維持する。表示は幅100%・高さauto、altはProfile。拡大縮小時も縦横比を保つ。

## 操作・アクセシビリティ

ページ内ナビ、本文へのスキップリンク、キーボードフォーカス表示を保持。Contactはメールアプリを開くリンク。通常のアンカー移動はスムーズスクロール、動きを減らす設定では停止。本文は画像にせずHTMLテキストを維持する。

## 管理・確認

実装：index.html / style.css / assets/profile-title.svg。ビルド・JavaScript・外部フォント取得不要。
公開先想定：megmegdesign.github.io。GitHub公開は未実施。
変更後はPC幅と375px程度のスマートフォン幅で折り返し、SVGの縦横比、文字と線の幅、横はみ出しを確認する。将来の構成変更時は本書も更新する。
