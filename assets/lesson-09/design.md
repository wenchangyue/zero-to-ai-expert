# Lesson 09 demo design — Fix a Spreadsheet With AI (2026-09-30)

Question: why does an AI-written spreadsheet formula give a wrong total without any error, and how do you catch it?

Practice sheet `orders.xlsx` (built by `make_sheet.py`): 20 orders, columns A date, B region, C product, D amount.
Two planted problems. When the sheet is pasted as plain text the stored-as-text 480 is indistinguishable from a number; the trailing space survives in the text and the model did see it: D7 = "480" stored as text; B10 = "East " (trailing space).
Expected total, summed from the planted row list: East, March 2026 = 7 rows, $4,180.

Arms (Sonnet via `claude -p`, clean harness, 3 fresh runs each; `runs.json`):
- A no data: the question only.
- B shape: headers + column letters + first three rows.
- C paste: whole sheet pasted as plain text with tabs (simulated paste, `paste-all.tsv`).
Method arm (`method-runs.json`, `run_turn.py`, 3 conversations): C + "tell me anything that could make it wrong without an error,
and give me check formulas". Turn 2 reports the values its own checks returned in the sheet (`t2-method-N.txt`), neutral wording.

Every distinct formula the model wrote, own-line or inline (16, `formulas-all.json` via `extract_formulas.py`) was evaluated on the real workbook in LibreOffice Calc 26.2.4.2 (`automation/eval_formulas.py`):
`eval-r1-libreoffice.json`, `eval-r2-libreoffice.json`, `eval-r2-cleaned-libreoffice.json` (D7 retyped as number, B10 trimmed).
Excel for Mac was tried for a second engine and did not respond to automation; not used. Behaviour relied on is documented for
Excel by Microsoft (SUM ignores text values; TRIM does not remove nonbreaking spaces) — see sources.md.

Counting units and categories fixed before scripting: see `scores.json`.
