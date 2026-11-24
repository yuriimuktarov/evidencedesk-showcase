# Source Claim Auditor

Exact table-count checks. Semantic mapping still requires review.

| Claim | Predicate | Claimed | Counted | Outcome |
|---|---|---:|---:|---|
| approve_count | Status = Approved | 64 | 59 | REFUTED_TABLE_COUNT |
| pending_count | Status = Pending | 70 | 74 | REFUTED_TABLE_COUNT |
| region_north | Region = North | 65 | 76 | REFUTED_TABLE_COUNT |
| unknown_column | RiskClass = High | 3 | None | ABSTAIN_UNKNOWN_COLUMN |

## Proposed corrections

```json
[
  {
    "id": "approve_count",
    "column": "Status",
    "equals": "Approved",
    "claimed_count": 59
  },
  {
    "id": "pending_count",
    "column": "Status",
    "equals": "Pending",
    "claimed_count": 74
  },
  {
    "id": "region_north",
    "column": "Region",
    "equals": "North",
    "claimed_count": 76
  }
]
```

Different Status/Result columns are flagged for review, never declared semantically equivalent.
