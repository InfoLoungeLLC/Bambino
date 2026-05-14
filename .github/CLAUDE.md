# CLAUDE.md

このファイルはClaude Code (claude.ai/code) がこのリポジトリで作業する際のガイドです。

## プロジェクト概要

横浜センター南駅近くのイタリアンバル「Bambino」(bambino.yokohama) の静的ウェブサイト。HTML と Sass で構成されており、JavaScriptのアプリケーションロジックやバックエンドはない。GitHub Pagesでホスティング。

## ビルド・テストコマンド

- `npm test` — htmlhintで全HTMLファイルをリント
- `npm run build:css` — Sassをコンパイルし、圧縮CSSとソースマップを生成
- `npm run watch:css` — Sassファイルの変更を監視して自動コンパイル（開発用）

## 構成

3つのページがあり、それぞれ対応するSassエントリポイントを持つ:

- `scss/style.scss` → `css/style.css` (トップページ: `index.html`)
- `scss/style-shop.scss` → `css/style-shop.css` (通販ページ: `shop.html`)
- `scss/style-takeout.scss` → `css/style-takeout.css` (テイクアウトページ: `takeout.html`)

共通Sassパーシャル: `_mixins.scss`(ブレークポイント/レスポンシブ)、`_colors.scss`、`_common.scss`(共通レイアウト)。ページ固有パーシャル: `_index.scss`、`_shop.scss`、`_takeout.scss`。

画像はビューポート別に分離: `images_pc/`(デスクトップ用）と `images_sp/`（モバイル用）。

## 規約

- スタイルの編集は `scss/` で行い、`npm run build:css` で `css/` を再生成する。`css/` 内のファイルを直接編集しない。
- サイトは日本語。文字コードはUTF-8。
- レスポンシブデザインはデスクトップ/モバイルの画像セットとSassミックスインで実現。
