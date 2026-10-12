# Task note / 任務紙條 — BMI Calculator v3: bilingual zh-TW ⇄ English (toggle)

- **Date / 日期**: 2026-10-12
- **From / 發自**: Wailan 洄瀾 (Leader)
- **To / 給**: Taroko 太魯閣 (Member)
- **Requested by / 小隊長需求**: make a "twilingo" version of the BMI app — full bilingual 繁體中文 + English with a language toggle switch. Save as v3, then commit + push to GitHub.

---

## 1. What to do / 做什麼

Take the working v1 app (`workspace/outbox/20261012-bmi-calculator-app.html`) and create a **v3 bilingual version**.

**⚠️ The v1 file must NOT be modified or deleted — it stays exactly as it is.** New files only.

### Required behaviour

1. **Everything v1 does, v3 keeps** — same formula (`BMI = 體重kg ÷ 身高m²`), one decimal place, same 6-level 衛福部 categories, same validation (empty/non-number → number error; ≤0 → greater-than-zero error; height outside 50–250 cm or weight outside 10–300 kg → realistic-range error), 清除 button, Enter key works, responsive on phone + desktop, single self-contained file, no external libraries.
2. **Language toggle switch** (top of the card, e.g. two small buttons `中文 | English`):
   - Default language on load: **中文（繁體，台灣用語）**
   - Clicking switches the **entire interface**: title, subtitle, labels, placeholders, buttons, result title, category names, table title + headers, and error messages.
   - If an error message is on screen when the language is switched, it re-shows in the new language (or clears — your call, just no stale mixed-language text).
   - Also update `document.documentElement.lang` (`zh-TW` ⇄ `en`) when toggling.
   - The calculation itself runs identically in both languages.

### Exact English strings (use these so wording stays consistent)

| 中文 | English |
|---|---|
| BMI 計算器 | BMI Calculator |
| 公式：體重(kg) ÷ 身高(m)² | Formula: weight (kg) ÷ height (m)² |
| 身高（公分） | Height (cm) |
| 體重（公斤） | Weight (kg) |
| 例如：170 / 例如：65 | e.g., 170 / e.g., 65 |
| 計算 | Calculate |
| 清除 | Clear |
| 您的 BMI 是 | Your BMI is |
| 過輕 / 正常 / 過重 | Underweight / Normal / Overweight |
| 輕度肥胖 / 中度肥胖 / 重度肥胖 | Mild Obesity / Moderate Obesity / Severe Obesity |
| 衛福部 BMI 標準對照表 | BMI Standard Table (Taiwan MOHW) |
| BMI 範圍 / 顯示文字 | BMI Range / Category |
| 請輸入數字 | Please enter a number |
| 數值必須大於 0 | The value must be greater than 0 |
| 請輸入合理的身高體重數值 | Please enter a realistic height and weight |

## 2. Format / 什麼格式

- **New file**: `workspace/outbox/20261012-bmi-calculator-app-v3.html` — single file, HTML+CSS+JS inline, no internet needed.
- Handoff comment at the very top of the HTML (like v1), one line.
- Chinese text: 繁體中文（台灣用語）— 軟體／資訊 style, never 软件／信息.
- No personal data, no analytics, nothing leaves the browser.
- **After the app passes its tests**: commit + push to GitHub (repo `411230072-arch/my-team`, already configured with origin):
  - `git add` only the new v3 files (app + report)
  - commit message: `feat: bilingual zh-TW/EN BMI calculator v3 with language toggle`
  - `git push`
- Report: **new file** `workspace/outbox/20261012-bmi-calculator-app-v3.md` with the one-line handoff on top (繁體中文台灣用語).

## 3. Done looks like / 怎樣算做完

1. `20261012-bmi-calculator-app-v3.html` exists in outbox; **v1 file byte-for-byte unchanged**.
2. Manual test in **中文 mode** — all v1 cases still pass:
   - 170/65 → 22.5 正常 · 160/45 → 17.6 過輕 · 170/75 → 26.0 過重 · 170/80 → 27.7 輕度肥胖
   - boundaries: exact 18.5 → 正常, 24.0 → 過重, 27.0 → 輕度肥胖, 30.0 → 中度肥胖, 35.0 → 重度肥胖
   - `abc` → 請輸入數字 · `0` → 數值必須大於 0 · `30cm` → 請輸入合理的身高體重數值
3. Manual test in **English mode**:
   - Same numbers produce the same BMI values and the English category (e.g. 170/65 → 22.5 **Normal**)
   - All labels/placeholders/errors switch to the English strings in the table above
   - `<html lang>` becomes `en`; switching back restores zh-TW everywhere
4. Git: `git status` clean, `git log` shows the new commit, `git ls-remote origin main` matches local HEAD — v3 visible on GitHub.
5. Report file in outbox with handoff line: what you did, anything to watch, ready or not.

When finished, STOP and tell the captain: "Done. Please go back to the leader for a check." 🚫 Do not call the leader directly.
