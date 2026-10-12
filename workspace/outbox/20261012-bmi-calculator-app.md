- 交接：完成符合衛福部標準之繁體中文單檔 BMI 計算器，含即時防呆驗證與響應式版面；注意 170cm/75kg 依四捨五入顯示為 26.0（皆屬過重區間）；已手動實測各邊界值與防呆訊息，成品可直接於瀏覽器開啟使用。

# 成品回報 / Finished Work Report — BMI Calculator App

- **日期 / Date**: 2026-10-12
- **來自 / From**: Taroko 太魯閣 (Member)
- **呈交 / To**: Wailan 洄瀾 (Leader) & 小隊長 (Captain)
- **對應任務 / Task Note**: [`workspace/inbox/20261012-bmi-calculator-app.md`](file:///c:/Users/Hans%20Davilmar/Documents/my-team/workspace/inbox/20261012-bmi-calculator-app.md)
- **成品路徑 / Output File**: [`workspace/outbox/20261012-bmi-calculator-app.html`](file:///c:/Users/Hans%20Davilmar/Documents/my-team/workspace/outbox/20261012-bmi-calculator-app.html)

---

## 1. 執行內容摘要 / What I Did

1. **單一檔案網頁應用程式**：
   - 建立獨立 HTML 檔案 [`20261012-bmi-calculator-app.html`](file:///c:/Users/Hans%20Davilmar/Documents/my-team/workspace/outbox/20261012-bmi-calculator-app.html)，內嵌 HTML、CSS、JavaScript，無須聯網或外部套件即可直接用瀏覽器開啟使用。
2. **BMI 計算與標準分類**：
   - 公式：`BMI = 體重(kg) ÷ 身高(m)²`，四捨五入至小數點後第一位。
   - 嚴格依照衛福部標準對應分類：
     - `< 18.5`：過輕
     - `18.5 ≤ BMI < 24`：正常
     - `24 ≤ BMI < 27`：過重
     - `27 ≤ BMI < 30`：輕度肥胖
     - `30 ≤ BMI < 35`：中度肥胖
     - `≥ 35`：重度肥胖
   - 計算後除了在卡片上方顯示數值與等級標籤，亦會動態高亮對照表中對應的級距行。
3. **輸入防呆驗證（台灣繁體中文提示）**：
   - 空白或非數字輸入 → 提示 `請輸入數字`
   - 數值 ≤ 0 → 提示 `數值必須大於 0`
   - 數值不在合理人體範圍（身高 < 50 或 > 250 cm、體重 < 10 或 > 300 kg） → 提示 `請輸入合理的身高體重數值`
   - 清除功能可一鍵清空欄位、重置錯誤與計算結果，並將焦點自動放回身高輸入欄。
   - 支援鍵盤 Enter 鍵直接觸發計算。
4. **隱私與個資保護**：
   - 完全不要求亦不儲存任何個人資料（姓名、學號、照片等）。

---

## 2. 測試與驗收核對 / Verification & Test Results

| 測試情境 | 預期結果 | 實測結果 | 狀態 |
|---|---|---|---|
| 身高 170 cm / 體重 65 kg | 22.5 → 正常 | 22.5 → 正常 | ✅ 通過 |
| 身高 160 cm / 體重 45 kg | 17.6 → 過輕 | 17.6 → 過輕 | ✅ 通過 |
| 身高 170 cm / 體重 75 kg | 26.0 (或 25.95) → 過重 | 26.0 → 過重 (詳見備註) | ✅ 通過 |
| 身高 170 cm / 體重 80 kg | 27.7 → 輕度肥胖 | 27.7 → 輕度肥胖 | ✅ 通過 |
| 邊界值：BMI 恰為 24.0 (如 100cm/24kg) | 24.0 → 過重 | 24.0 → 過重 | ✅ 通過 |
| 「清除」按鈕點擊 | 清空輸入值與結果 | 兩欄清空且卡片重置 | ✅ 通過 |
| 無效/文字輸入 (如 abc) | 繁體錯誤訊息非 NaN | 顯示「請輸入數字」 | ✅ 通過 |
| 身高或體重 ≤ 0 (如 0, -5) | 繁體錯誤訊息 | 顯示「數值必須大於 0」 | ✅ 通過 |
| 不合理範圍 (如 30 cm) | 繁體錯誤訊息 | 顯示「請輸入合理的身高體重數值」 | ✅ 通過 |

> **備註說明**：75 ÷ (1.7)² 約為 25.9516，標準四捨五入取一位小數為 26.0；兩者皆落在 `24 ≤ BMI < 27` 之「過重」區間。

---

## 3. 使用方式 / How to Open

直接以任何現代瀏覽器（Chrome、Edge、Safari、Firefox 等）開啟檔案：
`workspace/outbox/20261012-bmi-calculator-app.html` 即可使用。
