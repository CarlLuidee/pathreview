## Week 7 — Issue selection

**Issue link:** https://github.com/ascherj/pathreview/issues/146

**Issue title:** PII scrubber fails to redact parenthesized US phone numbers

**Tier:** [X] Tier 1  [ ] Tier 2  [ ] Tier 3

**Problem summary:**
The PII scrubber fails to redact US phone numbers that use the parenthesized format: (123) 456-7890. The phone number pattern in `pii_scrubber.py` is configured to match phone numbers with dashes (e.g., 123-456-7890), but it cannot detect phone numbers with parentheses around the area code. As a result, it leaves parenthesized phone numbers unredacted when `scrub()` is called and incorrectly omitted when `detect()` is called. A successful fix would recognize and redact phone numbers that contain either dashes or parentheses.

**Branch name:** fix/146-pii-scrubber-failing-redact

**Setup confirmation:** [X] App runs locally at localhost:5173

**Cohort ledger:** [X] Issue added to cohort ledger