## Week 7 — Issue selection

**Issue link:** https://github.com/ascherj/pathreview/issues/146

**Issue title:** PII scrubber fails to redact parenthesized US phone numbers

**Tier:** [X] Tier 1  [ ] Tier 2  [ ] Tier 3

**Problem summary:**
The PII scrubber fails to redact US phone numbers that use the parenthesized format: (123) 456-7890. The phone number pattern in `pii_scrubber.py` is configured to match phone numbers with dashes (e.g., 123-456-7890), but it cannot detect phone numbers with parentheses around the area code. As a result, it leaves parenthesized phone numbers unredacted when `scrub()` is called and incorrectly omitted when `detect()` is called. A successful fix would recognize and redact phone numbers that contain either dashes or parentheses.

**Branch name:** fix/146-pii-scrubber-failing-redact

**Setup confirmation:** [X] App runs locally at localhost:5173

**Cohort ledger:** [X] Issue added to cohort ledger

**Checklist Reasoning**
I chose this issue to fix because I understand it well enough to paraphrase it in my own words, understand the app's relevant codebase, and comprehend the expected result once the app is fixed. Since this is my first open-source contribution, a Tier 1 issue was chosen because it aligns with my current skill level. There are currently nine other people working on the issue. I am confident that I can manage the scope and deliver what is required on time.
