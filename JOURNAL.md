## Week 7 — Issue selection

**Issue link:** https://github.com/ascherj/pathreview/issues/146

**Issue title:** PII scrubber fails to redact parenthesized US phone numbers

**Tier:** [X] Tier 1  [ ] Tier 2  [ ] Tier 3

**Problem summary:**
The PII scrubber fails to redact US phone numbers that use the parenthesized format: (123) 456-7890. The phone number pattern in `pii_scrubber.py` is configured to match phone numbers with dashes (e.g., 123-456-7890), but it cannot detect phone numbers with parentheses around the area code. As a result, it leaves parenthesized phone numbers unredacted when `scrub()` is called and incorrectly omitted when `detect()` is called. A successful fix would recognize and redact phone numbers that contain either dashes or parentheses.

**Branch name:** fix/146-pii-scrubber-failing-redact

**Setup confirmation:** [X] App runs locally at localhost:5173

**Cohort ledger:** [X] Issue added to cohort ledger

## Week 8 — Reproduction & solution planning

**Reproduction commit link:** https://github.com/CarlLuidee/pathreview/blob/fix/146-PII-scrubber-failing-redact/tests/unit/test_pii_scrubber.py

**Reproduction summary:**
`tests/unit/test_pii_scrubber.py` was ran using pytest to reproduce and verify the relevant bugs in the code. `test_us_phone_number_redaction`, `test_us_phone_formats`, `test_detect_phone_pii`, and `test_phone_at_start_of_text` are failing due to a pattern matching error, but additionally `test_mixed_pii_and_text` is also failing due to scrub() over-matching.

**PLAN.md link:** https://github.com/CarlLuidee/pathreview/blob/fix/146-PII-scrubber-failing-redact/PLAN.md

**Walkthrough video (recommended):** [link to your Loom video, ≤2 min — recommended, not graded]

**Blockers or open questions:**
[Anything you're still uncertain about going into Week 9, or leave blank]