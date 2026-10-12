# Task note / 任務紙條 — BMI Calculator App (zh-TW)

- **Date / 日期**: 2026-10-12
- **From / 發自**: Wailan 洄瀾 (Leader)
- **To / 給**: Taroko 太魯閣 (Member)
- **Requested by / 小隊長需求**: make a BMI calculator app, interface in Traditional Chinese (Taiwan usage).

---

## 1. What to do / 做什麼

Build a simple **BMI 計算器** web app.

- Formula / 公式: `BMI = 體重(kg) ÷ 身高(m)²`
- Input / 輸入: 身高（公分）、體重（公斤）— two number fields plus a 計算 button and a 清除 button.
- Output / 輸出: the BMI value rounded to **one decimal place**, plus the category below.

Category table (衛福部標準) — use exactly these words in the UI:

| BMI 範圍 | 顯示文字 |
|---|---|
| < 18.5 | 過輕 |
| 18.5 ≤ BMI < 24 | 正常 |
| 24 ≤ BMI < 27 | 過重 |
| 27 ≤ BMI < 30 | 輕度肥胖 |
| 30 ≤ BMI < 35 | 中度肥胖 |
| ≥ 35 | 重度肥胖 |

## 2. Format / 什麼格式

- **One single file**: `20261012-bmi-calculator-app.html` — HTML + CSS + JavaScript all inside it.
- No external libraries, no CDN, no internet needed. Opens straight in a browser.
- All interface text in **繁體中文（台灣用語）**. Examples: 身高（公分）、體重（公斤）、計算、清除、您的 BMI 是、過輕／正常／過重／輕度肥胖／中度肥胖／重度肥胖.
- Not "軟件／視頻／信息" — use 軟體／影片／資訊 style Taiwan wording if any longer text appears.
- Clean, readable layout; usable on both desktop and phone screens.
- Basic input checking, with friendly zh-TW messages:
  - empty or non-numeric → 請輸入數字
  - height or weight ≤ 0 → 數值必須大於 0
  - implausible values (height outside 50–250 cm, weight outside 10–300 kg) → 請輸入合理的身高體重數值
- Do not store or ask for any personal data (姓名、學號、照片 all off-limits).

## 3. Done looks like / 怎樣算做完

1. File saved as a **new** file in `workspace/outbox/` — do not overwrite anything, do not write into `shared/`.
2. Open it in a browser and check by hand:
   - 170 cm / 65 kg → **22.5 → 正常**
   - 160 cm / 45 kg → **17.6 → 過輕**
   - 170 cm / 75 kg → **25.9 → 過重**
   - 170 cm / 80 kg → **27.7 → 輕度肥胖**
   - Boundary: exactly 24.0 → 過重 (not 正常)
   - 清除 empties both fields
   - Garbage input shows the zh-TW error message, not NaN
3. Leave a one-line handoff note in the outbox: what you did, what to watch, ready to use or not.

When finished, STOP and tell the captain: "Done. Please go back to the leader for a check." 🚫 Do not call the leader directly.
