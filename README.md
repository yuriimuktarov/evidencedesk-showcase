# EvidenceDesk
## What is EvidenceDesk?
EvidenceDesk checks numerical claims against Excel records. A reviewer can trace a reported count to a named column, an exact value and the rows that satisfy the rule.

## Business problems it solves
An operations report may overstate approved invoices or undercount pending work. Teams can identify the discrepancy, examine the rule and propose a corrected figure before circulating the report.

## Interactive demonstration
[Open the portfolio demo](https://yuriimuktarov.github.io/evidencedesk-showcase/) or download the repository and open index.html locally. Choose Ukrainian or Russian, select the 200-row example and run the check. The browser counts embedded synthetic records. The larger example displays archived results. All examples work offline.

## Example audit workflow
1. Open the [small workbook](example_200_rows.xlsx) and [claim definitions](claims_200_rows.json).
2. Filter Status to Approved. The claim says 64 and the table contains 59.
3. Compare the [report](verified_report_200_rows.md) with your count. A rule referencing the missing RiskClass column yields an abstention.

## Verified engineering results
Independent counts from the two supplied workbooks match the archived reports.

| Data rows | Status = Approved | Status = Pending | Region = North |
|---:|---:|---:|---:|
| 200 | 59 | 74 | 76 |
| 9,999 | 9,858 | 74 | 9,875 |

The larger workbook has 10,000 rows including its header. The original cloud test was archived. Its duration and service availability were not measured for this showcase.

## Architecture
The browser demonstration bundles synthetic records and count rules in a static page. The private pilot produces reports and verification receipts. Public JSON files summarize those receipts.

## Reproducibility and independent validation
Use Excel COUNTIF on each named column and compare with the reported count. Keep Status and Result distinct. Use SHA256SUMS.txt to check downloaded bytes. Public summaries contain file digests and carry no digital signature.

## Technology stack
The public demonstration uses HTML, CSS and JavaScript. The supplied pilot documentation identifies Python, FastAPI and PostgreSQL in the private product.

## Current product status
EvidenceDesk is a private commercial pilot. Public materials demonstrate its behavior on synthetic records. Production readiness has not been established. The original software remains proprietary. No open-source license is granted.

## Commercial inquiries
For pilot evaluations or engineering inquiries, use the contact details on [Yurii Muktarov’s GitHub profile](https://github.com/yuriimuktarov).
