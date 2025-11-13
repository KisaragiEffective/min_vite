# min_vite

Vue 3、TypeScript、Viteを使用した小さなアプリケーションです。

## 特徴

- ✅ Vue 3 Composition API
- ✅ TypeScript
- ✅ Vite
- ✅ SCSS (変数、ネスト、モダンな関数を使用)
- ✅ Composable (`useCounter`)

## プロジェクト構成

```
src/
├── App.vue                    # メインアプリケーションコンポーネント
├── main.ts                    # エントリーポイント
├── style.scss                 # グローバルスタイル (SCSS変数とネストを使用)
├── components/
│   └── HelloWorld.vue         # カウンターコンポーネント (Composition APIを使用)
└── composables/
    └── useCounter.ts          # カウンターロジックを持つComposable
```

## セットアップ

```bash
# 依存関係のインストール
npm install

# 開発サーバーの起動
npm run dev

# ビルド
npm run build

# プレビュー
npm run preview
```

## 技術スタック

- **Vue 3**: `<script setup>` 構文でComposition APIを使用
- **TypeScript**: 型安全性を提供
- **Vite**: 高速な開発サーバーとビルドツール
- **SCSS**: CSS拡張言語（変数、ネスト、モダンなcolor.adjust関数）

## Composableについて

このプロジェクトには `useCounter` composableが含まれており、以下の機能を提供します：

- `count`: 現在のカウント値 (ref)
- `doubleCount`: カウント値の2倍 (computed)
- `increment()`: カウントを1増やす
- `decrement()`: カウントを1減らす
- `reset()`: カウントを初期値にリセット
