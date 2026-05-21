# 🎙️ honyaku — Zoom会議 翻訳補助ツール

Zoom会議での言語の壁を下げるための補助ツールです。  
**ブラウザ完結型・サーバー不要・HTMLファイル1つで動きます。**

---

## 🔗 すぐ使えるURL（Chrome で開くだけ）

| ツール | URL |
|--------|-----|
| 🎙️ スピーキング補助 | https://y-takamatsu.github.io/honyaku/speaking-helper.html |
| 🎧 リスニング補助 | https://y-takamatsu.github.io/honyaku/listening-helper.html |

> **Chrome 専用**です。Edge・Firefox・Safari は未対応。

---

## 📦 ファイル一覧

| ファイル | 機能 | 説明 |
|---------|------|------|
| `speaking-helper.html` | 🎙️ スピーキング補助 | 自分の日本語 → 英語に翻訳・読み上げ |
| `listening-helper.html` | 🎧 リスニング補助 | 相手の英語 → 日本語字幕・読み上げ |

---

## 🎙️ speaking-helper.html（スピーキング補助）

自分が話した日本語をリアルタイムで英語に翻訳・読み上げします。

### 必要なもの
- Chrome ブラウザのみ（APIキー不要・完全無料）

### 使い方
1. 上のURLを Chrome で開く
2. マイクの使用を許可
3. 「🎤 話し始める」をクリックして日本語で話す
4. 英語に翻訳されて画面に表示・読み上げされます

---

## 🎧 listening-helper.html（リスニング補助）

Zoom・YouTube等の英語音声をリアルタイムで日本語字幕に変換します。

### 必要なもの
- Chrome ブラウザ
- **OpenAI APIキー**（[platform.openai.com](https://platform.openai.com) で取得）
  - Whisper API（音声認識）: $0.006/分
  - GPT-4o-mini（翻訳）: 約$0.0001/回
  - 目安：1時間の会議で **約$0.4〜0.6**

### 使い方
1. 上のURLを Chrome で開く
2. 画面下部の「設定」欄に OpenAI APIキー（`sk-...`）を入力
3. 「✅ 準備完了にする」をクリック
4. 「🎧 聞き取り開始」をクリック
5. 画面共有ダイアログが開くので：
   - **「画面全体」タブ**を選択
   - **「音声を共有」にチェック** ← 重要！
   - 「共有」をクリック
6. 英語が話されると数秒後に日本語字幕が表示されます

### 主な機能
- 🤖 OpenAI Whisper API による高精度英語認識
- 🌐 GPT-4o-mini による自然な日本語翻訳
- 🔊 日本語読み上げ（速度 1.5x / 2x / 2.5x）
- 📝 翻訳履歴の表示
- 🛡️ APIキーはブラウザ内のみで管理（外部送信なし）

---

## ⚠️ 注意事項

- **Chrome 専用**（Firefox・Safari は未対応）
- OpenAI APIキーは各自でご用意ください
- APIキーはページを再読込するたびに入力が必要です（セキュリティのため保存しません）

---

## 📁 リポジトリ構成

```
honyaku/
├── README.md              ← このファイル
├── 計画書.md              ← 開発計画・技術詳細
├── speaking-helper.html   ← フェーズ1：スピーキング補助
└── listening-helper.html  ← フェーズ2：リスニング補助
```
