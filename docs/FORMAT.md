# Record format

The root README describes the company. Each topic README states its current conclusion, evidence, uncertainty, and next action. Supporting Markdown files contain detailed analysis; dated records and original files provide evidence.

## Metadata

Use YAML frontmatter at the beginning of the root and topic summaries. Keep `null` for an unknown value and `[]` for a list with no entries. Empty metadata does not establish a business outcome.

| Root field | Meaning |
| --- | --- |
| `schema_version` | Use `1` for this format. |
| `team_id` | Use a stable identifier that survives a company rename or pivot. Use the studio's assigned ID when available. |
| `cohort` | Use the cohort label supplied by the studio. |
| `verticals` | Use the studio's shared vertical labels. Leave the list empty until the team has assigned them. |
| `stage` | Use `exploring`, `validating`, `building`, or `growing` for the team's main focus. Leave it null until the team chooses. |
| `owner` | Name the person responsible for the current summary. |
| `reviewed_on` | Record the date that person reviewed the summary. |

Each topic summary has `owner`, `reviewed_on`, and `evidence_status`. Use one of these evidence statuses for its main conclusion:

| Value | Meaning |
| --- | --- |
| `unexplored` | The team has not investigated the topic. |
| `hypothesis` | The team has stated a claim that it needs to test. |
| `testing` | The team is collecting evidence about the claim. |
| `supported` | The cited evidence supports the claim within its stated scope. |
| `contradicted` | The cited evidence challenges the claim. |

Describe mixed findings in the summary. A supported conclusion remains open to revision when new evidence arrives. The review date describes the document review; observation dates describe the underlying work.

## Forms and records

Files named `TEMPLATE.md` are forms. Keep the forms available and copy one when creating a record. Change `record_type: template` to the type specified in that form's directory guide, then complete the known fields. Keep unknown values explicit.

Use `YYYY-MM-DD` dates. Name weekly updates and decisions with their date. Add a short suffix when several records share a date. Name experiments with a stable ID, such as `EXP-001.md`; the form itself is not an experiment.

Before a test, record its hypothesis, method, and success criterion. After the test, record the observed result and its effect on the team's next decision. A planned test contributes no result evidence.

## Evidence and assets

Use `evidence/` for dated observations and original source material. Use `assets/` for things the team creates, such as diagrams, financial workbooks, and presentations. An original survey CSV is evidence; a spreadsheet modeling revenue is an asset.

Give each evidence record a title and identify its author, observation date, source, and finding. Include the method, sample, and limitations when relevant. Attribute quotations and separate them from the team's interpretation.

Add a Markdown note beside a binary source file, or link it from an existing evidence record. The note explains what the file contains and what claim it supports. For external material, include the publisher or owner, source title, link, and access date. Record access limits if a reader cannot inspect it.

Each artifact has one home. Other topics link to that home. Use relative links for files within the repository and full URLs for external sources. Add a link only after its target exists. Preserve observations and explain corrections through a dated note and Git history.

## CSV tables

The CSV files start with headers and no data rows. Use UTF-8, keep the header names, and quote values containing commas or newlines. Empty fields mean unknown or unrecorded; enter `0` only for an observed zero. Source paths in CSV files are relative to the repository root.

| File | Columns and rules |
| --- | --- |
| `09-traction/metrics.csv` | `metric_id`, `period_start`, `period_end`, `value`, `unit`, `definition_version`, `source_ref`. Define the metric and its version in `metric-definitions.md`. Append observations for new periods. |
| `09-traction/customers.csv` | `customer_id`, `status`, `status_date`, `owner`, `next_action`, `next_action_due`, `source_ref`. Use `conversation`, `pilot`, `paying`, or `ended`. Record the evidence for each status. |
| `10-fundraising/investor-pipeline.csv` | `investor_id`, `firm`, `owner`, `stage`, `last_contact_on`, `next_action`, `next_action_due`, `source_ref`. Use `identified`, `contacted`, `meeting`, `diligence`, `declined`, `committed`, or `funds_received`. |

The customer and investor tables show current relationship status. Dated evidence records and Git history preserve previous activity. Distinguish investor interest from a documented commitment and a commitment from receipt of funds.

## Progress and maintenance

Keep the current answer in each topic summary and the sequence of work in weekly updates and dated records. Link a weekly update to the evidence and decisions it discusses. Update the root overview when the company description, stage, strongest evidence, or next milestone changes.

Use completed work, new evidence, and changed decisions to describe progress. File counts and recent edits do not establish customer demand or a successful experiment.
