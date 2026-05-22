# 🎙️ honyaku — Zoom会議 翻訳補助ツール

Zoom会議での言語の壁を下げるための補助ツール集です。  
**ブラウザ完結型・サーバー不要・HTMLファイル1つで動きます。**

---

## 🔗 ツール一覧（Chrome で開くだけ）

| ツール | URL | 特徴 |
|--------|-----|------|
| 🌐 **リアルタイム翻訳** (New!) | [speaking-v2.html](https://y-takamatsu.github.io/honyaku/speaking-v2.html) | GPT-Realtime-2使用・多言語・双方向・Zoom音声対応 |
| 🎙️ スピーキング補助 | [speaking-helper.html](https://y-takamatsu.github.io/honyaku/speaking-helper.html) | 日本語→英語・無料（APIキー不要） |
| 🎧 リスニング補助 | [listening-helper.html](https://y-takamatsu.github.io/honyaku/listening-helper.html) | 英語→日本語字幕・Whisper+GPT-4o |

> **Chrome 専用**です。Edge・Firefox・Safari は未対応。

---

## ⭐ speaking-v2.html（リアルタイム翻訳 ― 推奨）

OpenAI の **GPT-Realtime-2 翻訳API** を使ったリアルタイム音声翻訳ツールです。

### 主な機能

| 機能 | 詳細 |
|------|------|
| 🌍 多言語対応 | 英語・日本語・中国語・韓国語・スペイン語・フランス語・ドイツ語 |
| 🔄 自動言語検出 | 入力言語を自動判定（設定不要） |
| 📝 リアルタイムテキスト | 翻訳テキストがストリーミング表示 |
| 🔊 音声読み上げ | 翻訳音声をリアルタイム再生 |
| 🎤 マイク入力 | 自分の声をリアルタイム翻訳 |
| 🖥 システム音声入力 | **Zoom・会議の音声をそのまま翻訳**（画面共有経由） |
| 📋 コピーボタン | 翻訳テキストをワンクリックでコピー |
| ⌨️ キーボード操作 | `Space` で Start / Stop |

### 必要なもの

- **Chrome ブラウザ**
- **OpenAI API キー**（[platform.openai.com](https://platform.openai.com) で取得）
  - 使用モデル：`gpt-realtime-translate`
  - 目安：30分の会議で **約$0.10〜0.30**

### 使い方

#### 🎤 マイク入力モード（自分の声を翻訳）

1. [ページを開く](https://y-takamatsu.github.io/honyaku/speaking-v2.html)
2. OpenAI API キー（`sk-...`）を入力して **Save**
3. 「Translate to」で翻訳先言語を選択（例：English）
4. 入力ソースは **🎤 Microphone** を選択
5. **▶ Start** → マイクの使用を許可
6. 日本語で話すと → 英語に翻訳されてテキスト表示＋音声読み上げ

#### 🖥 Zoom音声翻訳モード（会議の音声を翻訳）

1. 入力ソースで **🖥 System Audio** を選択
2. **▶ Start** → Chrome の画面共有ダイアログが開く
3. **「画面全体」** または **「ウィンドウ」** を選択
4. 下部の **「システムの音声を共有」にチェック ✓**
5. **「共有」** をクリック
6. Zoom で相手が話すと → リアルタイムで翻訳される

### 画面の見方

```
はじめまして、よろしくお願いします。   ← 元の発話（グレー・小）
Nice to meet you.                        ← 翻訳テキスト（白・大）
```

---

## 🎙️ speaking-helper.html（スピーキング補助）

自分が話した日本語をリアルタイムで英語に翻訳・読み上げします。  
**APIキー不要・完全無料** で使えます。

### 必要なもの
- Chrome ブラウザのみ（Web Speech API + MyMemory 無料翻訳）

### 使い方
1. [ページを開く](https://y-takamatsu.github.io/honyaku/speaking-helper.html)
2. マイクの使用を許可
3. 「🎤 話し始める」をクリックして日本語で話す
4. 英語に翻訳されて画面に表示・読み上げされます

### 制限
- 日本語→英語の一方向のみ
- 認識精度はブラウザ依存（Web Speech API）

---

## 🎧 listening-helper.html（リスニング補助）

Zoom・YouTube等の英語音声をリアルタイムで日本語字幕に変換します。

### 必要なもの
- **OpenAI APIキー**
  - Whisper API（音声認識）: $0.006/分
  - GPT-4o-mini（翻訳）: 約$0.0001/回
  - 目安：1時間の会議で **約$0.4〜0.6**

### 使い方
1. [ページを開く](https://y-takamatsu.github.io/honyaku/listening-helper.html)
2. OpenAI APIキーを入力 → 「✅ 準備完了にする」
3. 「🎧 聞き取り開始」をクリック
4. 画面共有ダイアログで **「画面全体」＋「音声を共有」にチェック** して共有
5. 英語が話されると数秒後に日本語字幕が表示されます

---

## 📊 ツール比較

| 項目 | speaking-v2 | speaking-helper | listening-helper |
|------|:-----------:|:---------------:|:----------------:|
| APIキー | 必要 | **不要** | 必要 |
| 対応言語 | 7言語 | 日→英のみ | 英→日のみ |
| 自分の声を翻訳 | ✅ | ✅ | ❌ |
| Zoom音声を翻訳 | ✅ | ❌ | ✅ |
| テキスト表示 | ✅ リアルタイム | ✅ | ✅ 数秒遅延 |
| 音声読み上げ | ✅ | ✅ | ✅ |
| 翻訳速度 | ⚡ 超高速 | 高速 | 数秒遅延 |

---

## 📁 ファイル構成

```
honyaku/
├── README.md                ← このファイル
├── speaking-v2.html         ← ⭐ リアルタイム翻訳（GPT-Realtime-2）
├── speaking-helper.html     ← スピーキング補助（無料）
├── listening-helper.html    ← リスニング補助
├── 計画書.md                ← フェーズ1・2の設計書
└── 計画書_フェーズ2.md      ← フェーズ2の設計書
```

---

## ⚠️ 注意事項

- **Chrome 専用**（Firefox・Safari は未対応）
- OpenAI APIキーは各自でご用意ください
- APIキーはブラウザの `localStorage` に保存されます（外部送信なし）
- System Audio キャプチャは Chrome 109 以上が必要

---

## 🛠️ 技術スタック

### speaking-v2.html（GPT-Realtime-2）
- WebSocket: `wss://api.openai.com/v1/realtime/translations?model=gpt-realtime-translate`
- 音声入力: `getUserMedia` / `getDisplayMedia` → AudioWorklet → PCM16 @ 24kHz
- テキスト表示: `session.output_transcript.delta` イベント（ストリーミング）
- 音声出力: `session.output_audio.delta` → Web Audio API で再生

### speaking-helper.html（旧版）
- 音声認識: Web Speech API（`SpeechRecognition`）
- 翻訳: MyMemory 無料API

### listening-helper.html
- 音声認識: OpenAI Whisper API
- 翻訳: OpenAI GPT-4o-mini
- 入力: `getDisplayMedia`（システム音声）
