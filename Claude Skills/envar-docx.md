Generate a formatted .docx version of the current month's EnVar progress report from the existing .md file in the working directory.

---

## Step 1 — Locate the source .md file

- Determine YYYY-MM as the **previous calendar month** relative to today (same logic as `/envar-progress`).
- Look for `YYYY-MM EnVar Progress Report.md` in the current working directory.
- If not found, tell the user to run `/envar-progress` first to generate it.

---

## Step 2 — Parse the .md file

Read the file and extract:
- **Reporting period** string (from the header line)
- **All table rows** — Deliverable ID + issue URL, Deliverable Title, Description, Milestone, Status, Due Date, Progress Update
- **Summary** paragraph
- **Plans for Next Month** bullet points (may be empty — preserve as blank bullets)

---

## Step 3 — Write and run a Python script

Write the script to `/tmp/envar_docx.py` and run it with `python3`.

### Full script spec

```python
from docx import Document
from docx.shared import Pt, RGBColor, Inches
from docx.enum.text import WD_ALIGN_PARAGRAPH
from docx.enum.table import WD_ALIGN_VERTICAL
from docx.oxml.ns import qn
from docx.oxml import OxmlElement

doc = Document()

# --- Page setup: landscape ---
section = doc.sections[0]
section.orientation = 1
section.page_width  = Inches(11)
section.page_height = Inches(8.5)
section.left_margin   = Inches(0.6)
section.right_margin  = Inches(0.6)
section.top_margin    = Inches(0.6)
section.bottom_margin = Inches(0.5)

BLUE       = RGBColor(0x1F, 0x49, 0x7D)
LIGHT_BLUE = RGBColor(0xD6, 0xE4, 0xF0)
WHITE      = RGBColor(0xFF, 0xFF, 0xFF)
BLACK      = RGBColor(0x00, 0x00, 0x00)
```

### Helpers to implement

**`set_font(run, size, bold, color, name="Arial")`**
Sets font name, size (Pt), bold, and color on a run.

**`set_cell_bg(cell, rgb)`**
Applies a solid background fill to a table cell using `w:shd` XML. Hex = `f"{rgb.red:02X}{rgb.green:02X}{rgb.blue:02X}"`.

**`add_hyperlink(paragraph, text, url)`**
Creates a real clickable hyperlink using `paragraph.part.relate_to(url, "http://schemas.openxmlformats.org/officeDocument/2006/relationships/hyperlink", is_external=True)`. Style: Arial 9pt, color `#1F497D`, single underline.

**`cell_para(cell, align)`**
Returns `cell.paragraphs[0]` with alignment set, space_before=1pt, space_after=1pt.

### Document sections

**Title**
`EnVar Monthly Progress Report` — Arial 16pt bold, color `#1F497D`, left-aligned.

**Metadata line** (single paragraph, Arial 9pt)
`Reporting Period: <period>   |   Project: [hyperlink→EnVar repo]   |   Project Board: [hyperlink→board]`
Bold labels, plain values, hyperlinks for EnVar and Board View.

**Section heading: "Deliverable Status"**
Arial 11pt bold, color `#1F497D`, space_before=8pt, space_after=4pt.

**Table**

Column widths (inches): `[0.85, 1.55, 1.90, 1.60, 0.85, 0.85, 2.20]`
Column headers: `Deliverable ID | Deliverable Title | Description | Milestone | Status | Due Date | Progress Update`

- Header row bg: `#1F497D`, text: white Arial 9pt bold, centered
- Row 1, 3, … (0-indexed even): white bg
- Row 2, 4, … (0-indexed odd): `#D6E4F0` bg
- All cells: vertical alignment top, Arial 9pt
- Deliverable ID: hyperlinked, centered
- Status + Due Date: centered
- All others: left-aligned

**Section heading: "Summary"**
Arial 11pt bold, color `#1F497D`, space_before=10pt, space_after=4pt.

**Summary paragraph**
Arial 9pt, extracted from .md.

**Section heading: "Plans for Next Month"**
Arial 11pt bold, color `#1F497D`, space_before=6pt, space_after=4pt.

**Bullet points**
Use `List Bullet` style, Arial 9pt. Preserve any filled-in text; use empty runs for blank bullets. Always output at least 3 bullets.

---

## Step 4 — Save and confirm

Save the file as `YYYY-MM EnVar Progress Report.docx` in the current working directory.
Confirm the full file path to the user.
