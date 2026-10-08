# Ai Command Palette 繁體中文版

這個分支為 Ai Command Palette 加入繁體中文介面，以及可複製貼入「新增自訂指令」的 Astute Graphics 中文自訂指令表。

目前內容包括：

- Ai Command Palette 介面字串的繁體中文翻譯。
- 未提供翻譯時自動沿用英文，不會因缺少字串而顯示空白。
- 與上游對應的 134 筆 Astute Graphics 中文自訂指令，並保留原始 Command Action 與 Command Type。
- Illustrator 語系檢查指令碼，可用來確認 `$.locale` 的實際值。

> 目前繁中化範圍為 Ai Command Palette 的操作介面與 Astute Graphics 自訂指令參考表。Illustrator 內建選單與工具，以及 Ai Command Palette 自身的內建／設定指令尚未建立完整的 `zh_TW` 名稱資料；未提供繁中名稱時，會自動顯示英文。

## Astute Graphics 中文自訂指令

`data/custom_commands_zh_TW.csv` 收錄與上游 Astute Graphics 資料相對應的 134 筆中文自訂指令。中文只用於顯示名稱，實際呼叫 Illustrator／Astute Graphics 的 Command Action 與 Command Type 均維持原值。

為避免名稱過長，僅在需要區分濾鏡、即時效果或同名工具時加上「（濾鏡）」或「（即時效果）」標註。

使用方式：

1. 開啟 Ai Command Palette。
2. 執行 `Add Custom Commands...`（新增自訂指令）。
3. 複製 `data/custom_commands_zh_TW.csv` 的內容並貼入文字框。
4. 按下「儲存」，再依需要選擇是否加入啟動畫面。

例如：

```csv
ColliderScribe｜碰撞吸附,Snap To Collisions Tool,tool
Texturino｜材質筆刷,TextureBrushTool,tool
Stipplism｜向量點描,Live ASTGStipple,menu
```

## 語系確認

在 Illustrator 中選擇「檔案 → 指令碼 → 其他指令碼…」，執行 `tests/check_illustrator_locale.jsx`，即可查看目前 Illustrator 回傳的語系值。

繁體中文語系目前使用 Adobe ExtendScript 慣用的 `zh_TW` 代碼。實機測試仍以 Illustrator 顯示的結果為準。

## 來源與授權

本專案以 Josh Duncan 的 [Ai Command Palette](https://github.com/joshbduncan/AiCommandPalette) 為基礎修改，原專案與本修改版本均依 [MIT License](LICENSE) 授權。原作者的授權與版權聲明完整保留。

本版本增加繁體中文在地化與 Astute Graphics 中文自訂指令資料。

Astute Graphics 是 Astute Graphics Limited 的產品與商標。本專案與 Astute Graphics Limited 沒有隸屬、合作或背書關係。
