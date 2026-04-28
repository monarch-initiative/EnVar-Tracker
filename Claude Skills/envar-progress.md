## Step 1 — Determine reporting period

- Use the **previous calendar month** relative to today's date.
- First day = 1st of that month. Last day = last calendar day of that month.
- Example: run on June 1 or June 2, 2026 → period is **May 1 – May 31, 2026**
- YYYY-MM for filenames = the reporting month (e.g. `2026-05`)

---

## Step 2 — Fetch live data

Run both in parallel:

```
gh project item-list 131 --owner monarch-initiative --format json
```

For every issue number found (currently 1–16):
```
gh issue view <number> --repo monarch-initiative/EnVar-Tracker --comments --json number,title,body,comments,milestone,labels,assignees
```

---

## Step 3 — Filter deliverables to include

Include a row if ANY of the following are true:
- Milestone due date falls within the reporting month
- Projected completion date has passed AND status is not Complete or Deprecated
- Status is "In Progress" regardless of date

---

## Step 4 — Extract comment data

From each issue's comments:
- **Progress Update**: any comment containing "Progress Report" — extract full content, note date
- **Plans for Next Month**: any comment containing "Plans for next month" — extract full content, note date
- If multiple matches, include all in chronological order
- If none found, leave blank

---

## Step 5 — Write the markdown report

Save as `YYYY-MM EnVar Progress Report.md` in the current working directory.

Use this exact structure:

```markdown
# EnVar Monthly Progress Report

**Reporting Period:** Month DD – Month DD, YYYY &nbsp;|&nbsp; **Project:** [EnVar](https://github.com/monarch-initiative/EnVar-Tracker) &nbsp;|&nbsp; **Project Board:** [Board View](https://github.com/orgs/monarch-initiative/projects/131/views/1)

---

## Deliverable Status

<table>
<thead>
<tr>
<th width="70">Deliverable ID</th>
<th width="160">Deliverable Title</th>
<th width="380">Description</th>
<th width="160">Milestone</th>
<th width="80">Status</th>
<th width="80">Due Date</th>
<th width="240">Progress Update</th>
</tr>
</thead>
<tbody>
<tr>
<td align="center"><a href="issue-url">D1.1</a></td>
<td>Title</td>
<td>Full issue body verbatim — do not trim or summarize.</td>
<td>Milestone 1 – Foundational Setup &amp; Onboarding</td>
<td align="center">Complete</td>
<td align="center">Apr 8, 2026</td>
<td><strong>Progress Report – Apr 14:</strong><br>Full comment text verbatim.</td>
</tr>
</tbody>
</table>

---

## Summary

Narrative paragraph summarizing the month's activity, any blockers, and overall milestone health. 2–3 sentences. No emojis. No bullet points.

## Plans for Next Month

-
-
-
```

**Status values** — use exactly as shown on the project board: Complete, In Progress, Not Started, Deprecated. Do not invent statuses like "Overdue."

**Description** — use the full issue body text verbatim. Do not trim, summarize, or shorten. Escape `&` as `&amp;` and `"` as `"` inside HTML cells.

**Progress Update** — use the full comment text verbatim. Format bullet points with `<br>–` for line breaks within the cell.

**Due Date** — use `Mon D, YYYY` format (e.g. `Apr 8, 2026`).

**Milestone** — full name from GitHub (e.g. `Milestone 1 – Foundational Setup &amp; Onboarding`).

---

## Step 6 — Push to GitHub and open a PR

### 6a. Get the current main SHA
```
gh api repos/monarch-initiative/EnVar-Tracker/git/refs/heads/main --jq '.object.sha'
```

### 6b. Create a new branch
Branch name: `add-YYYY-MM-progress-report` (e.g. `add-2026-05-progress-report`)
```
gh api repos/monarch-initiative/EnVar-Tracker/git/refs \
  --method POST \
  --field ref="refs/heads/add-YYYY-MM-progress-report" \
  --field sha="<main-sha>"
```

### 6c. Upload the file via API (no clone needed)
```
gh api "repos/monarch-initiative/EnVar-Tracker/contents/Monthly EnVar Progress Reports/YYYY-MM EnVar Progress Report.md" \
  --method PUT \
  --field message="Add YYYY-MM EnVar Monthly Progress Report" \
  --field content="$(base64 < 'YYYY-MM EnVar Progress Report.md')" \
  --field branch="add-YYYY-MM-progress-report"
```

### 6d. Open the PR
```
gh pr create \
  --repo monarch-initiative/EnVar-Tracker \
  --head add-YYYY-MM-progress-report \
  --base main \
  --title "Add YYYY-MM EnVar Monthly Progress Report" \
  --body "..."
```

PR body should include: reporting period, deliverables covered, link to project board.

---

## Step 7 — Report back to user

Confirm:
1. Path of the saved `.md` file
2. PR URL
