# Word Cards 單字卡片系統

## 📌 專案簡介

這是一個以 C# Windows Forms 開發的英文單字學習卡片應用程式，支援單字瀏覽、音效播放與自動輪播功能。

---

## 🛠️ 開發環境

- **語言**：C# (.NET Framework)
- **UI 框架**：Windows Forms
- **音效套件**：WMPLib（Windows Media Player）
- **IDE**：Visual Studio

---

## 📁 專案結構
專案資料夾/
├── frmWordCards.cs         # 主視窗邏輯
├── frmWordCards.Designer.cs
├── WordCollection.cs       # 單字清單集合類別
├── WordItem.cs             # 單字資料類別
├── WordCards.txt           # 單字資料檔（需自行準備）
└── 音效資料夾/              # 各單字對應的 .mp3 或 .wav 音效檔
---

## 📄 單字資料檔格式（WordCards.txt）

每行代表一筆單字，欄位以特定分隔符切割，對應 `WordItem` 的欄位：

| 欄位 | 說明 |
|------|------|
| Word | 英文單字 |
| Phonogram | 音標 |
| Explain | 中文解釋 |
| SoundPath | 音效檔路徑 |

> 請確保 `WordCards.txt` 存在於執行檔同目錄下，否則程式將顯示錯誤並關閉。

---

## 🎮 操作說明

| 操作 | 功能 |
|------|------|
| 點擊單字清單 | 顯示並播放選取單字 |
| 按下 `Enter` | 跳到下一個單字並播放 |
| 按下 `Space` | 重複播放目前單字 |
| 點擊 `Play` 按鈕 | 開始自動輪播 |
| 點擊 `Stop` 按鈕 | 停止自動輪播 |

> 自動輪播模式下，點擊清單或按鍵盤將自動停止播放。

---

## ⚙️ 主要功能說明

### `ShowWord(WordItem word)`
顯示單字的英文、音標與中文解釋到對應的文字方塊。

### `PlayWord(WordItem word)`
使用 Windows Media Player 播放單字音效檔，若檔案不存在會顯示提示訊息。

### `NextWordList()`
將清單選項移至下一筆，到底時自動循環回第一筆，並保持選取項目顯示在清單中間位置。

### `UpdateWordList()`
重新載入 ListBox 的單字清單顯示。

---

## ▶️ 執行步驟

1. 以 Visual Studio 開啟專案
2. 確認 `WordCards.txt` 存在於輸出目錄（`bin/Debug/` 或 `bin/Release/`）
3. 確認音效檔路徑正確
4. 按下 `F5` 執行

---

## ⚠️ 注意事項

- 音效播放需要系統已安裝 Windows Media Player
- 音效檔路徑為相對或絕對路徑，需與 `WordCards.txt` 中記錄一致
- 本程式僅支援 Windows 平台
