## New resource pages

- [CSV import cleanup workflow](https://trendstackai.com/resources/csv-import-cleanup-workflow.html?utm_source=manual&utm_medium=github&utm_campaign=second_round_links&utm_content=csv-import-cleanup-workflow)
- [CSV column mapping AI guide](https://trendstackai.com/resources/csv-column-mapping-ai.html?utm_source=manual&utm_medium=github&utm_campaign=second_round_links&utm_content=csv-column-mapping-ai)
- [CSV encoding and delimiter fix guide](https://trendstackai.com/resources/csv-encoding-and-delimiter-fix.html?utm_source=manual&utm_medium=github&utm_campaign=second_round_links&utm_content=csv-encoding-and-delimiter-fix)
- [Google Sheets cleanup before and after](https://trendstackai.com/resources/google-sheets-cleanup-before-after.html?utm_source=manual&utm_medium=github&utm_campaign=second_round_links&utm_content=google-sheets-cleanup-before-after)
- [CRM lead source normalization AI](https://trendstackai.com/resources/crm-lead-source-normalization-ai.html?utm_source=manual&utm_medium=github&utm_campaign=second_round_links&utm_content=crm-lead-source-normalization-ai)
- [Excel formula audit checklist](https://trendstackai.com/resources/excel-formula-audit-checklist.html?utm_source=manual&utm_medium=github&utm_campaign=second_round_links&utm_content=excel-formula-audit-checklist)

# AI Spreadsheet Operations Checklists

Practical checklists for cleaning spreadsheet exports, mapping CSV imports, reviewing AI-generated formulas, and checking operational data before it goes into Airtable, Google Sheets, Excel, CRM tools, or dashboards.

This repository is meant for operators, analysts, founders, and no-code teams who need repeatable data cleanup workflows rather than generic AI prompts.

## Quick Links

- Full resource library: [TrendStack AI workflow resources](https://trendstackai.com/resources.html?utm_source=manual&utm_medium=github&utm_campaign=link_retaining_distribution&utm_content=resource-library)
- CSV to Airtable field mapping checklist: [field mapping checklist](https://trendstackai.com/resources/csv-to-airtable-field-mapping-checklist.html?utm_source=manual&utm_medium=github&utm_campaign=link_retaining_distribution&utm_content=csv-to-airtable-field-mapping)
- CSV import error checklist: [CSV import troubleshooting](https://trendstackai.com/resources/csv-import-error-checklist.html?utm_source=manual&utm_medium=github&utm_campaign=link_retaining_distribution&utm_content=csv-import-error-checklist)
- Google Sheets cleanup examples: [before and after examples](https://trendstackai.com/resources/google-sheets-cleanup-examples.html?utm_source=manual&utm_medium=github&utm_campaign=link_retaining_distribution&utm_content=google-sheets-cleanup-examples)

## CSV Import Checklist

Use this before importing a CSV into Airtable, a CRM, a database, or a reporting tool.

- Keep a raw copy of the original CSV.
- Check encoding, delimiter, and line endings.
- Confirm every header has a clear destination field.
- Separate stable IDs from readable names.
- Preserve IDs as text when leading zeros matter.
- Normalize date formats before upload.
- Normalize select values before creating new options.
- Test five representative rows before a full import.
- Create a post-import review view for blanks, invalid values, duplicates, and unmatched links.

## Airtable Linked Record Mapping

Linked records are one of the easiest places for CSV imports to look correct but behave incorrectly.

Before import:

- Confirm the linked table already contains expected records.
- Compare CSV values with the linked table primary field.
- Decide whether new linked records should be created automatically.
- Check whether duplicate linked names already exist.
- Consider importing risky values into a temporary text field first.

Example mapping:

| CSV column | Airtable destination | Field type | Rule |
| --- | --- | --- | --- |
| Company | Company | Linked record | Must match primary field |
| Contact ID | Source ID | Single line text | Preserve exactly |
| Status | Status | Single select | Normalize labels |
| Notes | Notes | Long text | Keep raw text |

## Google Sheets Cleanup Checklist

Use this after exporting data from a form, CRM, ecommerce tool, support desk, or spreadsheet maintained by multiple people.

- Remove empty rows and empty columns.
- Trim leading and trailing spaces.
- Standardize capitalization for categories.
- Convert dates into one format.
- Split mixed fields such as `Name <email@example.com>`.
- Check duplicates by stable ID before checking by name.
- Keep a separate cleanup log for changed values.
- Review formulas after sorting or deleting rows.

## Excel Formula QA Checklist

Use this before trusting AI-generated formulas or spreadsheet formulas copied from another file.

- Test the formula on normal, blank, zero, and error rows.
- Confirm absolute and relative references are intentional.
- Check whether ranges include future rows.
- Verify that lookup keys are unique when uniqueness is assumed.
- Compare totals against a manual sample.
- Add a visible error-handling branch only when it helps review.
- Keep one small before/after example beside the formula.

## CRM Export Cleanup Checklist

CRM exports often contain inconsistent lifecycle stages, duplicate companies, missing IDs, and mixed date formats.

- Preserve record IDs and owner IDs.
- Normalize stage, source, and status labels.
- Split multi-value fields only after checking delimiter conflicts.
- Deduplicate by domain, company ID, or contact ID before name.
- Keep deleted, merged, and archived records separate from active records.
- Review null values before importing back into the CRM.

## AI Prompt Template

Use this prompt with a small sample, not the full private dataset:

```text
You are reviewing a spreadsheet cleanup workflow.

Goal:
[Describe the target import, dashboard, CRM cleanup, or reporting workflow.]

Columns:
[Paste column names only, or 5-10 safe sample rows.]

Please identify:
1. likely ID fields
2. likely linked record fields
3. fields that need normalization
4. date, number, or currency risks
5. duplicate detection rules
6. a safe import test plan

Do not rewrite the data. Return a checklist and mapping table.
```

## Contribution Ideas

Useful additions:

- More before/after cleanup examples.
- Tool-specific import notes for Airtable, HubSpot, Notion, Salesforce, or Google Sheets.
- Formula QA examples.
- Small anonymized sample datasets.

Avoid adding private data, customer exports, API keys, or screenshots containing personal information.
